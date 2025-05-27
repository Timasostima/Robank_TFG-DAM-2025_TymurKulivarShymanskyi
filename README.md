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
