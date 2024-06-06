# ElkCompose 🚀

ElkCompose es un proyecto para configurar y desplegar ELK (Elasticsearch, Logstash, Kibana) usando Docker Compose.

## Descripción 📖

Este proyecto proporciona una manera sencilla de desplegar una pila ELK utilizando Docker Compose. Esto es útil para el análisis de logs, monitoreo y visualización de datos en tiempo real.

## Prerrequisitos 📋

Antes de comenzar, asegúrate de tener Docker y Docker Compose instalados en tu sistema.

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Instalación 🛠️

Sigue estos pasos para clonar el repositorio e iniciar la pila ELK:

1. Clona el repositorio:
    ```bash
    git clone https://github.com/soycarlosherrera/ElkCompose.git
    cd ElkCompose
    ```

2. Inicia los contenedores:
    ```bash
    docker-compose up -d
    ```

## Uso 💻

Una vez que los contenedores están en funcionamiento, puedes acceder a Kibana en tu navegador web:

http://localhost:5601



## Flujo del Proyecto 🔄

El flujo del proyecto al ejecutarse es el siguiente:

1. **Filebeat** recolecta todos los logs que se encuentran en la carpeta `logs`.
2. **Filebeat** envía los logs a **Logstash**.
3. **Logstash** procesa los logs y los envía a **Elasticsearch**.
4. **Elasticsearch** indexa los logs.
5. Puedes visualizar los logs indexados en **Kibana**.

### Visualización en Kibana 📊

Puedes ver cómo se visualizan los datos en Kibana en la carpeta `images`. Aquí hay un ejemplo de cómo se ve la interfaz de Kibana con los datos cargados:

![Kibana Dashboard](images/kibana_dashboard.png)

### Patrón de Índice en Kibana

Para configurar el patrón de índice en Kibana, sigue estos pasos:

1. Abre Kibana en tu navegador: [http://localhost:5601](http://localhost:5601)
2. Ve a **Management** > **Index Patterns**.
3. Crea un nuevo patrón de índice usando `filebeat-*` como el nombre del índice.
4. Selecciona `@timestamp` como el campo de tiempo.

## Configuración Adicional ⚙️

- **Elasticsearch** está disponible en el puerto `9200`.
- **Logstash** puede configurarse editando el archivo `logstash.conf` en el directorio `logstash/config`.
- **Kibana** puede configurarse editando el archivo `kibana.yml` en el directorio `kibana/config`.

## Comandos Útiles 📜

Dentro del proyecto se encuentra un archivo llamado `GuiaComandos.txt`, en el cual pueden encontrar comandos útiles para este proyecto y los relacionados con Docker Compose. Asegúrate de revisarlo para obtener información adicional sobre cómo administrar y utilizar el proyecto.

## Contribuir 🤝

¡Las contribuciones son bienvenidas! Para contribuir, sigue estos pasos:

1. Haz un fork del proyecto
2. Crea una nueva rama (`git checkout -b feature-nueva`)
3. Realiza tus cambios y haz commit de ellos (`git commit -am 'Añadir nueva característica'`)
4. Empuja tus cambios a la rama (`git push origin feature-nueva`)
5. Abre un Pull Request

## Licencia 📄

Este proyecto está licenciado bajo la Licencia MIT. Esto significa que puedes usar, copiar, modificar y distribuir el proyecto, siempre y cuando incluyas una copia de la licencia original. Mira el archivo [LICENSE](LICENSE) para más detalles.

## Contacto ✉️

Para cualquier consulta, puedes contactarme a través de [mi perfil de GitHub](https://github.com/soycarlosherrera).

