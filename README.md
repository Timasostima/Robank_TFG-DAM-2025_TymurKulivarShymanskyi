# Robank - Sistema de Gestión de Finanzas Personales

Sistema multiplataforma para la gestión de finanzas personales, desarrollado como Trabajo de Fin de Grado para el ciclo de Desarrollo de Aplicaciones Multiplataforma.

## 📱 Componentes del Sistema

| Componente | Descripción | Tecnologías |
|------------|-------------|------------|
| **Robank Android** | Aplicación nativa para Android | Kotlin, Jetpack Compose, Material 3 |
| **Robank Backend** | API RESTful con autenticación | Spring Boot, JPA, PostgreSQL |
| **Robank Frontend** | Aplicación web SPA | Angular 19, TypeScript, Chart.js |

## ✨ Características

- **Multiplataforma**: Acceso desde web y Android
- **Autenticación Firebase**: Inicio de sesión seguro con email y Google
- **Categorización de gastos**: Organización personalizable
- **Análisis visual**: Gráficos interactivos para seguimiento financiero
- **Metas financieras**: Seguimiento de objetivos de ahorro
- **UI/UX moderna**: Temas claro/oscuro y diseño responsive
- **Multiidioma**: Soporte para español e inglés

## 🚀 Instalación Rápida

```bash
# Clonar el repositorio con submódulos
git clone --recurse-submodules https://github.com/Timasostima/Robank.git
cd Robank

# Iniciar backend y base de datos con Docker
cd robank_backend
docker-compose up -d

# Iniciar el servidor de desarrollo frontend
cd ../robank_frontend
npm install
npm start
```

## 📝 Configuración

### Frontend
Para el frontend, configura las variables de entorno en el archivo `environment.ts`:

```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:8080/api',
  firebase: {
    apiKey: "TU_API_KEY",
    authDomain: "TU_AUTH_DOMAIN",
    projectId: "TU_PROJECT_ID",
    appId: "TU_APP_ID"
  }
};
```

### Android
Para la aplicación Android:

1. Crear un proyecto en Firebase Console
2. Añadir la app Android al proyecto
3. Descargar [`google-services.json`](robank_backend/src/main/java/dev/tymurkulivar/robank_backend/config/FirebaseAuthenticationFilter.java ) y colocarlo en `/app`
4. Configurar la URL de la API en `Config.kt`

### Backend
El backend utiliza variables de entorno para la configuración de Firebase:

- `FIREBASE_PROJECT_ID`: ID del proyecto
- `FIREBASE_PRIVATE_KEY_ID`: ID de la clave privada
- `FIREBASE_PRIVATE_KEY`: Clave privada completa
- `FIREBASE_CLIENT_EMAIL`: Email del cliente
- `FIREBASE_CLIENT_ID`: ID del cliente
- `FIREBASE_x509`: URL del certificado x509

## 🏗️ Arquitectura del Sistema

El proyecto sigue una arquitectura modular con tres componentes principales:

1. **Backend (Spring Boot)**:
   - API RESTful con autenticación de Firebase
   - Capa de servicios para lógica de negocio
   - Repositorios para persistencia de datos
   - Controladores para gestionar endpoints HTTP

2. **Frontend Web (Angular)**:
   - Arquitectura basada en componentes
   - Gestión de estado con servicios y observables
   - Comunicación con la API mediante interceptores HTTP
   - Enrutamiento para navegación sin recarga

3. **Aplicación Android (Kotlin)**:
   - Arquitectura MVVM (Model-View-ViewModel)
   - Jetpack Compose para UI declarativa
   - Retrofit para comunicación con API
   - Corrutinas para operaciones asíncronas

## 📱 Funcionalidades Principales

- **Registro y autenticación**: Sistema seguro con Firebase Auth
- **Gestión de perfil**: Personalización de datos y preferencias
- **Dashboard financiero**: Vista general de estado económico
- **Registro de gastos**: Documentación y categorización
- **Informes y estadísticas**: Visualización de tendencias
- **Planificación de metas**: Seguimiento de objetivos financieros
- **Ajustes y personalización**: Temas, idiomas y configuraciones

## 👨‍💻 Autor

**Tymur Kulivar Shymanskyi**
- GitHub: [Timasostima](https://github.com/Timasostima)
- Email: contact@tymurkulivar.dev

---

*Desarrollado como Trabajo de Fin de Grado para el ciclo de Desarrollo de Aplicaciones Multiplataforma.*