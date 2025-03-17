# Airflow-guide


# 🚀 Apache Airflow en Docker

Este repositorio contiene una guía para instalar y ejecutar **Apache Airflow** utilizando Docker. Se recomienda usar Docker en lugar de una instalación local para evitar problemas de dependencias y conflictos con otras bibliotecas de Python.

## **📌 ¿Por qué usar Docker para Airflow?**
Apache Airflow tiene múltiples dependencias que pueden entrar en conflicto con otros entornos de Python si se instala de forma local. Usar Docker permite:
- **Evitar conflictos** con otras bibliotecas instaladas en el sistema.
- **Tener un entorno aislado y reproducible** en cualquier máquina.
- **Fácil configuración y despliegue** en distintos entornos.

---

## **⚙️ Instalación y configuración en Docker**
### **1️⃣ Clonar este repositorio**
```bash
git clone <URL_DEL_REPO>
cd <NOMBRE_DEL_REPO>
```

### **2️⃣ Descargar e instalar Docker**
Si no tienes Docker instalado, descárgalo desde [Docker](https://www.docker.com/get-started) e instálalo en tu sistema.

### **3️⃣ Crear archivos y directorios necesarios**
Airflow necesita algunos volúmenes y configuraciones iniciales. Ejecuta:
```bash
mkdir -p ./dags ./logs ./plugins
echo -e "AIRFLOW_UID=$(id -u)" > .env
```

### **4️⃣ Descargar la imagen de Apache Airflow**
```bash
docker pull apache/airflow:2.7.3
```
*(Verifica que la versión más reciente esté disponible en el [repositorio oficial](https://hub.docker.com/r/apache/airflow)).*

### **5️⃣ Iniciar Apache Airflow**
Ejecuta el siguiente comando para inicializar la base de datos y correr los servicios:
```bash
docker-compose up airflow-init
docker-compose up
```

### **6️⃣ Acceder a la interfaz web**
Una vez que Airflow esté corriendo, accede a la UI en:
📌 **http://localhost:8080**  
Usuario: `airflow`  
Contraseña: `airflow`

---
