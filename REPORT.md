# Lab 1 Git Race -- Project Report

## Description of Changes

Añadida la funcionalidad de internacionalización (i18n) a la aplicación web utilizando Spring Boot. Se han creado archivos de propiedades para tres idiomas: inglés (por defecto), español y francés. La aplicación ahora permite a los usuarios cambiar el idioma de la interfaz mediante un selector de idioma en la barra de navegación. Se ha configurado un `LocaleResolver` y un `LocaleChangeInterceptor` para gestionar los cambios de idioma basados en un parámetro de solicitud. Además, se han modificado las vistas Thymeleaf para utilizar mensajes internacionalizados.

## Technical Decisions

Se ha utilizado `SessionLocaleResolver` para almacenar la configuración regional del usuario en la sesión, lo que permite mantener el idioma seleccionado durante la sesión del usuario. El `LocaleChangeInterceptor` se ha configurado para interceptar las solicitudes y cambiar el idioma cuando se detecta el parámetro `lang`, el cual guardamos en el link de nuestra aplicación. Los archivos de propiedades (`messages.properties`, `messages_es.properties`, `messages_fr.properties`) contienen las traducciones necesarias para los textos de la aplicación. Thymeleaf se ha integrado con Spring Boot para facilitar la renderización de mensajes internacionalizados en las vistas.

## Learning Outcomes

He aprendido el uso de Spring Boot para internacionalización (i18n) de aplicaciones web, incluyendo la configuración de archivos de propiedades para diferentes idiomas y la integración con Thymeleaf para renderizar contenido dinámico basado en la configuración regional del usuario. También he aprendido mas a fondo sobre el funcionamiento de LocaleResolver y LocaleChangeInterceptor para gestionar cambios de idioma en la aplicación (además de entender ciertos conflictos que surgían al llamar a locale en el controlador y que no se reflejaban en la vista).

## AI Disclosure

### AI Tools Used

- Copilot (GitHub) - Utilizado para completar código principalmente.
- DeepSeek (Modo DeepThink) - Utilizado para consultar dudas mas profundas sobre el funcionamiento de Spring Boot y Locale.

### AI-Assisted Work

- Los 3 ficheros .properties referentes a la traducción de la app. 90% del contenido de los ficheros ha sido generado por IA. Resto del contenido ha sido modificado por mí para adaptarlo al contexto de la aplicación, corrigiendo errores ortográficos/adaptando frases, etc.
- Sustitución automática de los campos de texto en welcome.html, añadiendo las estiquetas correspondientes a los .properties.
- Creacion del archivo LocaleConfig.kt, con la configuración básica para que Spring Boot soporte i18n. Pequeños cambios y ajustes para adaptarlo a las necesidades de la app.

### Original Work

- He realizado el diseño de la solución, la integración de los componentes y la adaptación del código generado por IA a las necesidades específicas de la aplicación.
- He implementado la lógica para gestionar el cambio de idioma mediante un selector en la barra de navegación.
- Comprensión completa del código original, su integración y funcionamiento dentro del contexto de la aplicación.
- Comprensión sobre el funcionamiento de LocaleResolver y LocaleChangeInterceptor, y su correcta implementación en la aplicación, incluyendo la resolución de conflictos que surgían al llamar a locale en el controlador y que no se reflejaban en la vista.
- Corrección de los tests de integración para que verifiquen correctamente la presencia de los nuevos textos internacionalizados.
