# Mini Manual: Cómo monté mi API Robank con Cloudflare Tunnel

## Lo que hice para exponer mi API al mundo

### Antes de empezar
- **Dominio**: tymurkulivar.dev en Porkbun
- **Cuenta**: Cloudflare (gratuita)
- **Local**: Docker y Docker Compose en Windows

### Paso 1: Arrancar la API en Docker
```bash
cd [DIRECTORIO-PROYECTO]
docker-compose up -d
```
API corriendo en localhost:8080

### Paso 2: Instalar Cloudflared
```powershell
# Crear carpeta para cloudflared
New-Item -ItemType Directory -Path "$Env:USERPROFILE\.cloudflared" -Force

# Descargar el ejecutable
Invoke-WebRequest -Uri https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-windows-amd64.exe -OutFile "$Env:USERPROFILE\.cloudflared\cloudflared.exe"

# Añadir carpeta al PATH en Variables de Entorno
```

### Paso 3: Crear y configurar el túnel
```powershell
# Crear archivo de config en ~/.cloudflared/config.yml
```

Mi archivo de configuración:
```yaml
tunnel: [ID-DEL-TUNEL]
credentials-file: C:\Users\tymur\.cloudflared\[ID-DEL-TUNEL].json

ingress:
  - hostname: robank-api.tymurkulivar.dev
    service: http://localhost:8080
    originRequest:
      noTLSVerify: true
      disableChunkedEncoding: true
      connectTimeout: 30s
      http2Origin: false
  - service: http_status:404
```

### Paso 4: Vincular DNS al túnel
```bash
cloudflared.exe tunnel route dns [NOMBRE-TUNEL] [DOMINIO-COMPLETO]
```

### Paso 5: Configurar CORS en Spring Boot
```java
configuration.setAllowedOrigins(List.of(
    "http://localhost:4200",
    "https://robank-api.tymurkulivar.dev",
    "https://robank.tymurkulivar.dev"
));
```

### Paso 6: Iniciar el túnel
```powershell
# Ejecución manual
cloudflared.exe tunnel --config "$env:USERPROFILE\.cloudflared\config.yml" run [NOMBRE-TUNEL]

# Como servicio (permanente), a mi no me funcionó, 
# ya que no pude especificar la configuraciñon
cloudflared.exe service install
```

## Solución de problemas frecuentes

- **Problemas SSL/TLS**: Ajusta la configuración en Cloudflare → SSL/TLS → Visión general, cambiando a modo "Flexible"
- **API no responde**: Verifica funcionamiento local con curl y revisa los logs del túnel
- **Certificados**: Pueden tardar hasta 24h en propagarse
- **Servicio no inicia automáticamente**: 
  1. Abrir el administrador de servicios:
     - Presiona Win+R, escribe services.msc y pulsa Enter
  2. Busca el servicio "cloudflared" en la lista
     - Haz clic derecho sobre él
     - Selecciona "Propiedades"
     - Ve a la pestaña "General"
     - Establece "Tipo de inicio" en "Automático"
     - Haz clic en "Aplicar" y luego en "Aceptar"

_No modificar si funciona correctamente_