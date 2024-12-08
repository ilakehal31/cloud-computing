# Utiliser une image Python 3.7 légère
FROM python:3.7-slim

# Définir le répertoire de travail
WORKDIR /app

# Copier d'abord les requirements pour profiter du cache Docker
COPY requirements.txt .

# Installer les dépendances
RUN pip install --no-cache-dir -r requirements.txt

# Copier le reste des fichiers de l'application
COPY . .

# Donner les droits d'exécution à app.py ET le rendre exécutable
RUN chmod +x app.py && \
    sed -i '1i#!/usr/bin/env python3' app.py

# Exposer le port utilisé par l'application
EXPOSE 5000

# Commande pour démarrer l'application
CMD ["python", "app.py"]