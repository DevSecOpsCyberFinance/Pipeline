DevSecOps - Cocina 2.0

🚀 Pipeline de seguridad continua que integra análisis SAST, SCA, DAST, construcción de imágenes, firma digital y despliegue seguro.
Ideal para proyectos que buscan incorporar seguridad desde la etapa de desarrollo hasta producción.

📝 Descripción General

Este pipeline automatiza todo el ciclo DevSecOps, combinando herramientas de análisis de seguridad, construcción y despliegue seguro de imágenes, y firma criptográfica para garantizar la integridad del software.

🧰 Tecnologías Utilizadas

🔐 Herramientas de Seguridad

--- Tipo	Herramienta	Descripción ---

🧠 SAST	Semgrep (Docker)	Análisis estático del código

🧱 SCA	Snyk CLI	Escaneo de dependencias

🌐 DAST	OWASP ZAP (Docker)	Análisis dinámico

✍️ Firma Digital	Cosign	Firma y verificación de imágenes



🏗️ Infraestructura

🐳 Container Runtime: Docker + Docker Compose
🧭 Registry: Docker Registry privado
⚙️ CI/CD: Jenkins Pipeline

🧩 Plugins Requeridos en Jenkins


--- Plugin	Descripción ---

workflow-aggregator	Pipeline como código

credentials-binding	Manejo de secrets

docker-workflow	Integración con Docker

docker-plugin	Builds de containers

copyartifact	Copia entre jobs

ansicolor	Salida colorizada

artifact-archiver	Archivo de artefactos


🔑 Credenciales Necesarias

🪙 API Tokens
--- Credential ID	Tipo	Uso ---

Synk-DevSecOps-cli	Secret Text	Token Snyk API

devsecops-registry-cred	Username/Password	Registry Docker


🔐 Claves Criptográficas

Credential ID	Tipo	Uso
cosign-private-key	Secret File	Firma de imágenes

cosign-public-key	Secret File	Verificación

cosign-key-passphrase	Secret Text	Passphrase


🧠 Estructura de Jobs en Jenkins

🌍 Pipeline Principal

Función: Orquestación general de todo el proceso


🧪 Jobs Especializados
--- Job	Herramienta	Función ---


Ingredientes/SAST	Semgrep	Análisis estático

Ingredientes/SCA	Snyk	Escaneo de dependencias

Ingredientes/DAST	OWASP ZAP	Escaneo dinámico

Ingredientes/Firmador/Build-and-Push-Image	Docker	Construcción y push de imagen

Ingredientes/Firmador/Firmar	Cosign	Firma digital

Ingredientes/Firmador/Desplegar-Imagen	Docker	Despliegue seguro


🧰 Requisitos del Sistema
🧭 Software

🧱 Jenkins 2.346+ con los plugins listados

🐳 Docker 20.10+ y Docker Compose 2.0+

📝 Cosign 2.0+ instalado en agentes

🧠 Snyk CLI disponible en PATH o vía tool installer

📦 Registry Docker accesible (por defecto localhost:5000)

🌍 Conexión a internet para descargas de dependencias

🛰️ Network host habilitado para escaneos ZAP


