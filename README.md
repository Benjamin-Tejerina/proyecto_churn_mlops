## Proyecto Churn MLOps

Descripción

Este proyecto implementa un modelo de Machine Learning para la predicción de abandono de clientes (Customer Churn) siguiendo buenas prácticas de ML-Ops.

El objetivo es demostrar el ciclo básico de puesta en producción de un modelo de Machine Learning mediante:

Entrenamiento del modelo.
Serialización del modelo entrenado.
Exposición mediante API REST con FastAPI.
Contenedorización utilizando Docker.
Versionamiento mediante Git y GitHub.
Arquitectura del Proyecto
proyecto_churn_mlops/
│
├── api/
├── models/
├── src/
├── tests/
├── Dockerfile
├── requirements.txt
└── README.md
Requisitos
Python 3.11 o superior
Docker Desktop
Git
Instalación
1. Clonar repositorio
git clone https://github.com/Benjamin-Tejerina/proyecto_churn_mlops.git
cd proyecto_churn_mlops
2. Crear entorno virtual

Windows:

python -m venv .venv
.venv\Scripts\activate

Linux/Mac:

python3 -m venv .venv
source .venv/bin/activate
3. Instalar dependencias
pip install -r requirements.txt
Entrenamiento del Modelo

Ejecutar:

python src/train.py

Al finalizar se generará el modelo entrenado dentro de la carpeta:

models/
Ejecución Local

Levantar la API:

uvicorn api.main:app --reload

Acceder a:

http://localhost:8000

Documentación Swagger:

http://localhost:8000/docs
Ejemplo de Predicción

Solicitud:

{
  "tenure": 12,
  "monthly_charges": 75.5,
  "total_charges": 900.0
}

Respuesta:

{
  "prediction": 1,
  "probability": 0.84
}
Docker
Construcción de Imagen
docker build -t churn-mlops-api:0.1 .
Ejecución del Contenedor
docker run -p 8000:8000 churn-mlops-api:0.1
Pruebas

Ejecutar:

pytest
Buenas Prácticas Implementadas
Separación de código por responsabilidades.
API REST con FastAPI.
Contenedorización con Docker.
Versionamiento mediante Git.
Gestión de dependencias.
Documentación del proyecto.
Posibles Mejoras Futuras
Integración continua (GitHub Actions).
Registro de experimentos con MLflow.
Monitoreo del modelo en producción.
Despliegue en la nube.
Pruebas automatizadas de integración.
Autor

Benjamin Tejerina

Maestría en Ciencia de Datos e Inteligencia Artificial

Módulo: ML-Ops y Puesta en Producción