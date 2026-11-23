# Déployement des contenneurs avec Docker Compose

## Liste des conteneurs
- Mosquitto
- MySQL/MariaDB
- webapp Frontend : Node.js
- webapp Backend : Python
- Redis (optionnel)

## Configuration Mosquitto

**Fichier config de mosquitto :**
*mosquitto/config/mosquitto.conf*

```ini
# Persistence
persistence true
persistence_location /mosquitto/data/

# Logs
log_dest file /mosquitto/log/mosquitto.log

# MQTT TCP
listener 1883
protocol mqtt

# WebSocket (optionnel)
listener 9001
protocol websockets

# Authentification
allow_anonymous false
password_file /mosquitto/config/password

```

**Création du fichier utilisateurs :**
```
docker run --rm -it \
  -v ./mosquitto/config:/mosquitto/config \
  eclipse-mosquitto:2 \
  mosquitto_passwd -c /mosquitto/config/password mqttuser
  ```

## Lancement de la stack :
```bash
# Démarrer les conteneurs
docker compose up -d

# Vérifier leur état
docker compose ps

# Afficher les logs
docker compose logs -f

# Arrêter la stack
docker compose down
```