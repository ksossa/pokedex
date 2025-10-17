Despliegue Técnico – Pokédex Angular
Plataforma: Azure Static Web Apps
 Repositorio GitHub: pokedex
 URL pública del despliegue: https://witty-mushroom-01eb7880f.2.azurestaticapps.net/  	
 Fecha:17  Octubre 2025
 Autores: Kevin Perez - Reynel Castillo - Kendry Llorente- Keiner Bolaño 
Resumen general
Arrancamos este proyecto con el objetivo de documentar y ejecutar el despliegue de nuestro pokédex angular. El proceso cubrió desde visual studio code hasta azure static web apps, siempre conectado a nuestro repositorio en github. Lo crucial era garantizar un despliegue funcional, totalmente automatizado y seguro, dejando la app accesible al público. 

1. Creación y configuración del repositorio GitHub
Para empezar, creamos el repositorio en github llamado pokedex
 URL:https://github.com/ksossa/pokedex.git
Desde Visual Studio Code, el flujo fue simple. Abrimos nuestra carpeta local llamada: (kevin) copiamos el código fuente , y desde la terminal integrada procedimos a clonar el repositorio usando la URL. Finalmente, comprobamos que la conexión remota fuera correcta con :
 git remote -v
2. Ajustes en el código fuente
Antes de subir la versión final, hicimos ajustes críticos. el más importante fue eliminar el archivo pipeline.yml, ya que interfiere directamente con el flujo de despliegue automático de azure static web apps. También tuvimos que revisar la carpeta environments para asegurarnos que las rutas de las imágenes fueran absolutas , solucionando así el problema de visualización de producción. Por último,confirmos en angular.json que la salida de compilación estuviera correcta: "outputPath": "dist/pokedex-angular"

 
3. Control de versiones y comandos Git utilizados
En la terminal de visual studio code, aseguramos la sincronizacion con estos comandos estandar para subir los cambios: 
git add .
git commit -m "Primer commit del proyecto Pokedex"
git push origin main 
Comandos adicionales que nos ayudaron en la verificacion: 
git status
git branch -M main
git remote -v
Una nota importante: si nos aparece clasico mensaje:  nothing to commit. verificamos que estemos en la carpeta correcta , o forzamos una reiniciazion limpia del repositorio con: 
rmdir .git /s /q
git init
git add .
git commit -m "Inicialización del repositorio desde cero"
git push -u origin main



4. Creación de la App Web Estática en Azure
En el portal de Azure (https://portal.azure.com) se seleccionó la opción Static Web App - Create.


Se configuraron los siguientes campos:


Subscription: Azure for Students


Resource Group: pokedex_group


Name: pokedex


Plan: Standard
Tipo: Aplicación web estática 


Region: East US 2
Source: GitHub


Repository: pokedex
Branch: main


Build Preset: Angular


App location: /





Azure solicitó autorización de GitHub y creó un workflow automático (.github/workflows/azure-static-web-apps.yml).


Una vez configurado, se generó la URL pública del despliegue:
 https://witty-mushroom-01eb7880f.2.azurestaticapps.net/



5. Configuración de seguridad
Se creó el archivo staticwebapp.config.json con encabezados HTTP de seguridad esto garantiza:
Carga segura por HTTPS.


Prevención de ataques XSS, MIME sniffing y clickjacking.


Correcto funcionamiento de las rutas Angular tras el despliegue.


6. Problemas encontrados y soluciones
El Error de build: “The app build failed to produce artifact folder” fue causado por una Ruta output_location incorrecta en el workflow. La solución fue modificar la ruta en el archivo .github/workflows/...yml a dist/pokedex-angular.
El Error de dependencias: npm ERR! ERESOLVE unable to resolve dependency tree se debió a Dependencias Angular no compatibles. Se resolvió añadiendo la configuración NPM_CONFIG_LEGACY_PEER_DEPS: true en el workflow.
El error visual de imágenes fue provocado por Rutas mal referenciadas en el environment. La solución fue actualizar las rutas a absolutas.




7. Verificación de despliegue
Se ingresó a la URL de Azure:
  https://witty-mushroom-01eb7880f.2.azurestaticapps.net/ 
 Resultado: aplicación funcionando correctamente, con imágenes, estilos y consumo de PokéAPI.


Se realizó escaneo de seguridad en securityheaders.com, obteniendo una calificación A, confirmando la correcta aplicación de encabezados HTTP.


Se comprobó el candado SSL activo y sin errores de consola en el navegador.


 8. Resultado final
La Aplicación ha sido desplegada Correctamente en Azure Static Web Apps.
 La Integración GitHub–Azure está Automatizada mediante GitHub Actions, lo que garantiza un proceso de CI/CD Activo.
Además, los Encabezados de seguridad han sido Configurados y verificados.
La URL pública donde se puede acceder a la aplicación es: https://witty-mushroom-01eb7880f.2.azurestaticapps.net/.

Conclusión
El despliegue de la aplicación Pokédex Angular en Azure Static Web Apps fue exitoso.
 Se lograron los objetivos de conectividad, seguridad y automatización, demostrando dominio del flujo GitHub - Azure y buenas prácticas en la gestión de repositorios, control de versiones y configuración CI/CD.
Este proceso permitió reforzar conocimientos en:
Integración continua y despliegue continuo (CI/CD).
Seguridad web mediante encabezados HTTP.
Diagnóstico y solución de errores en entornos de producción.
