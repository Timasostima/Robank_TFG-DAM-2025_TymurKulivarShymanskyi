# Robank - Sistema de Gestión de Finanzas Personales

<!-- ![Robank Logo](robank_frontend/public/Robank_Logo_Small.png) -->

Sistema multiplataforma para la gestión de finanzas personales, desarrollado como Trabajo de Fin de Grado para el ciclo de Desarrollo de Aplicaciones Multiplataforma.

## Componentes del Sistema

| Componente | Descripción |
|------------|-------------|
| [**Robank Android**](https://github.com/Timasostima/robank_android/) | Aplicación nativa para Android |
| [**Robank Backend**](https://github.com/Timasostima/robank_backend/) | Servidor RESTful con Spring Boot |
| [**Robank Frontend**](https://github.com/Timasostima/robank_frontend/) | Aplicación web SPA con Angular |

> [!NOTE]
> Cada componente puede funcionar de manera independiente, pero se recomienda ejecutar el sistema completo para disfrutar de todas las funcionalidades.

## Funcionalidades Principales

- **Acceso Multiplataforma**: Web y Android
- **Autenticación Segura**: Email/contraseña y Google
- **Categorización Personalizada**: Organización eficiente de gastos
- **Análisis Visual**: Gráficos para el seguimiento financiero
- **Localización**: Soporte para español e inglés
- **Modos de Visualización**: Temas claro y oscuro

## Tecnologías

- **Frontend Web**: Angular 19, TypeScript, Chart.js
- **Backend**: Spring Boot 3.2, JPA/Hibernate, PostgreSQL
- **Android**: Kotlin, Jetpack Compose, Material Design 3

## Instalación Rápida

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

> [!TIP]
> Consulta los README individuales de cada componente para obtener instrucciones detalladas de instalación y configuración.

## Autor

**Tymur Kulivar Shymanskyi**
- GitHub: [Timasostima](https://github.com/Timasostima)
- Email: contact@tymurkulivar.dev

## Licencia

Este proyecto está disponible bajo la Licencia MIT.

---

*Desarrollado como Trabajo de Fin de Grado para el ciclo de Desarrollo de Aplicaciones Multiplataforma.*