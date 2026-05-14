# 🎵 Generación de Sonidos con IA (AudioLDM2)

Este repositorio contiene un entorno de experimentación para la síntesis de audio impulsada por Inteligencia Artificial, utilizando el modelo **AudioLDM2** de Hugging Face. El proyecto está optimizado para generar música, ritmos lofi y efectos ambientales a partir de descripciones de texto (Text-to-Audio).

## 🚀 Características del Proyecto
* **Modelo:** `cvssp/audioldm2-music`
* **Entorno:** Jupyter Notebook / Python script
* **Aceleración por Hardware:** Soporte para CUDA (GPU) con cálculos en `float32` para evitar colapsos matemáticos en la generación de ondas.
* **Resolución de Bugs:** Incluye un *Monkey Patch* (parche en caliente) para solucionar un error de configuración oficial en los servidores de Hugging Face respecto a la clase `GPT2LMHeadModel`.

---

## 📁 Estructura del Repositorio

```text
├── notebooks/                 # Notebooks de Jupyter para experimentación
├── outputs/                   # Carpeta destino para los archivos .wav generados
├── src/                       # Scripts de Python limpios y ejecutables
├── environment.yml            # Dependencias del entorno de Anaconda
├── requirements.txt           # Dependencias de pip
└── README.md                  # Documentación del proyecto

🛠️ Instalación y Configuración
Para garantizar que el código funcione correctamente y evitar conflictos de compatibilidad (especialmente con las librerías diffusers y transformers), se recomienda replicar el entorno virtual exacto.

Opción 1: Usando Anaconda (Recomendado)
Abre tu Anaconda Prompt y ejecuta el siguiente comando para recrear el entorno a partir del archivo .yml:

Bash
conda env create -f environment.yml
conda activate audioldm2
Opción 2: Usando Pip estándar
Si prefieres usar un entorno virtual estándar de Python:

Bash
python -m venv audioldm2_env
audioldm2_env\Scripts\activate  # En Windows
pip install -r requirements.txt
💻 Uso
Activa tu entorno virtual.

Abre el notebook de experimentación en Jupyter o ejecuta el script de la carpeta src/.

Modifica las variables prompt y negative_prompt dentro del código para describir el audio que deseas generar:

Python
prompt = "Lofi hip hop beat with a smooth saxophone melody, rainy window background ambiance, high quality"
negative_prompt = "low quality, noise, distortion, vocals"
El archivo generado se guardará automáticamente en la carpeta de salidas o directorio de trabajo bajo el nombre musica_generada.wav (formato estándar de 16-bits compatible con cualquier reproductor).

⚠️ Notas Importantes
Aviso de Consola: Durante la carga del pipeline, es normal observar la advertencia Expected types for language_model.... El código maneja esta excepción inyectando la pieza correcta en memoria antes de la inferencia, por lo que la generación no se verá afectada.


¡Felicidades por completar este proyecto y subirlo de nivel! Tu repositorio ahora
