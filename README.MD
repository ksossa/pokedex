README
Fecha:17  Octubre 2025
 Autores: Kevin Perez - Reynel Castillo - Kendry Llorente- Keiner Bolaño
Repositorio: 
https://github.com/ksossa/pokedex.git 
URL pública del despliegue: https://witty-mushroom-01eb7880f.2.azurestaticapps.net
Descripción general
Pokédex Angular 
Es una aplicación web desarrollada con el framework Angular, que permite explorar los Pokémon de las primeras tres generaciones.  
La app muestra un listado de especies y un detalle individual con información de estadísticas base, habilidades y registros en diferentes versiones del juego, desde Pokémon Green (1996) hasta Emerald (2005).
El proyecto se conecta con la Poké API, una API RESTful gratuita que provee datos actualizados del universo Pokémon.  
El despliegue se realizó exitosamente en Azure Static Web Apps, con integración directa a GitHub mediante GitHub Actions para habilitar un flujo de CI/CD (Integración y Despliegue Continuos).
Tecnologías utilizadas
Angular Framework JavaScript: para construir la interfaz de usuario.
HTML5 / CSS3 / TypeScript:Lenguajes base del desarrollo web moderno.
PokéAPI: API RESTful que provee la información de los Pokémon.
Azure Static Web Apps: Servicio de Microsoft Azure para desplegar aplicaciones estáticas. 
GitHub Actions: Plataforma de automatización usada para el despliegue continuo. 
Font Awesome: Librería de iconos utilizada en la interfaz.
Normalize.css: Librería para estandarizar los estilos CSS entre navegadores.
Requisitos mínimos
Node.js versión LTS (recomendado: 18.x o 20.x)  
npm (viene incluido con Node.js)  
Angular CLI (npm install -g @angular/cli)  
Git  instalado en el sistema  
Visual Studio Code 
Navegador moderno (Chrome, Edge, Firefox)
Instalación y ejecución en entorno local
Clonar el repositorio desde GitHub:  
bash 
git clone https://github.com/ksossa/pokedex.git

Instalar dependencias del proyecto:
bash
Copiar código
npm install
    Para los errores de dependencias:
bash
Copiar código
npm install --legacy-peer-deps

Ejecutar la aplicación en modo desarrollo:
bash
Copiar código
npm start

Generar build para producción
       Para crear la carpeta de despliegue:
bash
Copiar código
npm run build
ng build --configuration production
Esto generará la carpeta:
bash
dist/pokedex-angular 
 Despliegue en Azure Static Web Apps
El proyecto fue desplegado en Azure Static Web Apps siguiendo los pasos:
Crear recurso “Static Web App” en portal.azure.com.
Conectar la cuenta de Azure con el repositorio de GitHub.
Configurar:  App location: /Output location: dist/pokedex-angular
Azure genera automáticamente un archivo de workflow en: .github/workflows/azure-static-web-apps.yml Cada vez que se realiza un git push, GitHub Actions compila y publica la aplicación automáticamente.


Seguridad implementada
Para reforzar la seguridad, se creó el archivo staticwebapp.config.json con los encabezados HTTP recomendados:
json
  "globalHeaders": 
    "Strict-Transport-Security": "max-age=31536000; includeSubDomains",
    "X-Frame-Options": "SAMEORIGIN",
    "X-Content-Type-Options": "nosniff",
    "Referrer-Policy": "no-referrer"
  "navigationFallback":   "rewrite": "/index.html"
Beneficios de seguridad:
Forzar navegación por HTTPS.
Evitar inyección de scripts (XSS).
Prevenir detección de tipos MIME no seguros.
Bloquear visualización en iframes externos.
Proteger información de referencia.
 Verificación de seguridad
Se realizó un escaneo en https://securityheaders.com/ 
Resultado obtenido: Calificación A
 Reflexión técnica
Durante el proceso de despliegue se evidenció la importancia de:
Utilizar CI/CD para automatizar los cambios y reducir errores manuales.
Configurar encabezados HTTP como medida de protección ante vulnerabilidades comunes.
Mantener sincronizados los valores de outputPath y output_location en Angular y el workflow de GitHub.
Comprender el flujo completo de desarrollo → versionamiento → despliegue → verificación.

 Aprendizajes obtenidos
Dominio del flujo GitHub → Azure para aplicaciones Angular.
Configuración de pipelines automáticos con GitHub Actions.
Aplicación de conceptos básicos de DevOps y seguridad web.
Solución de errores de dependencias, build y rutas en entornos reales.

Recursos
Repositorio GitHub: https://github.com/KADEBOLH/-pokedex-proyect 
App desplegada en Azure: https://witty-mushroom-01eb7880f.2.azurestaticapps.net/ 
PokéAPI: https://pokeapi.co/ 
Documentación Angular: https://angular.io/ 
Portal Azure: https://portal.azure.com/ 
Estado final	
Aplicación desplegada - Correctamente en Azure Static Web Apps
CI/CD (GitHub Actions) - Configurado y funcionando
Encabezados de seguridad -  Implementados y verificados
Conectividad con PokéAPI	- Correcta
Calificación en Security Headers	( A )
Versión final del proyecto:  Estable y funcional
Azure for Students
Licencia: Uso académico
