# Project Context & Engineering Standards

## 🎯 Project Goal
Sistema de mantenimiento predictivo basado en análisis acústico industrial.

## 💻 Tech Stack & Hardware Constraints
- **Hardware:** Intel i7-7500U, 8GB RAM (Optimizar para CPU, no GPU).
- **OS:** Desarrollo en Windows 10, Producción en Ubuntu.
- **Backend:** FastAPI, RabbitMQ, Celery.
- **ML/DSP:** Librosa, DeepFilterNet, Scikit-learn (Evitar Demucs/UVR5).

## 🛠 Coding Standards (Mandatory)
1. **Async by Default:** Toda comunicación entre servicios debe ser asíncrona vía RabbitMQ.
2. **Modular Workers:** El procesamiento de audio debe encapsularse en tareas de Celery independientes.
3. **DSP Pipeline:** Limpieza (Noise Reduction) -> MFCCs Extraction -> Classification.
4. **Error Handling:** Logs detallados para debugging en entornos headless (Ubuntu).

## 📂 Directory Structure Convention
- `/src/ingestion`: Scripts para ESP32 y FastAPI.
- `/src/workers`: Tareas de Celery para procesamiento de audio.
- `/models`: Pesos de modelos entrenados.