# Base serveur mini-jeux Minecraft

# Installation du serveur Minecraft avec mini-jeux

# 1. Création du dossier du serveur
mkdir MinecraftServer
cd MinecraftServer

# 2. Téléchargement de PaperMC (choisir la version souhaitée)
curl -o paper.jar https://papermc.io/api/v2/projects/paper/versions/1.20.1/builds/100/downloads/paper-1.20.1-100.jar

# 3. Accepter l'EULA
echo "eula=true" > eula.txt

# 4. Création du script de démarrage
echo "#!/bin/bash
java -Xms2G -Xmx4G -jar paper.jar nogui" > start.sh
chmod +x start.sh

# 5. Démarrage initial du serveur
./start.sh

# 6. Installation des plugins nécessaires
mkdir plugins
cd plugins

# Plugins pour les mini-jeux
curl -o BedWars.jar https://www.spigotmc.org/resources/bedwars.100/ # Exemple
curl -o SkyWars.jar https://www.spigotmc.org/resources/skywars.99/ # Exemple
curl -o Rush.jar https://www.spigotmc.org/resources/rush.101/ # Exemple

# 7. Installation et configuration des maps
cd ..
mkdir maps
cd maps

# Téléchargement des maps
curl -o BedWarsMap.zip https://example.com/bedwars-map.zip
curl -o SkyWarsMap.zip https://example.com/skywars-map.zip
curl -o RushMap.zip https://example.com/rush-map.zip
curl -o LobbyMap.zip https://example.com/lobby-map.zip

# Extraction des maps
unzip BedWarsMap.zip -d BedWars
unzip SkyWarsMap.zip -d SkyWars
unzip RushMap.zip -d Rush
unzip LobbyMap.zip -d Lobby

cd ..

# 8. Configuration des plugins
mkdir BedWars SkyWars Rush

# Configuration de BedWars
echo "gameMode: bedwars
defaultArena: BedWars
maxPlayers: 16
" > BedWars/config.yml

# Configuration de SkyWars
echo "gameMode: skywars
defaultArena: SkyWars
maxPlayers: 12
" > SkyWars/config.yml

# Configuration de Rush
echo "gameMode: rush
defaultArena: Rush
maxPlayers: 10
" > Rush/config.yml

# Configuration du Lobby
echo "spawnWorld: Lobby" > server.properties


# plus d'info 

tu peut DL le txt 

# Discord https://discord.gg/Myz3jSrNPY

# 9. Relancer le serveur
./start.sh

# Le serveur est maintenant prêt avec BedWars, SkyWars, Rush et un Lobby configuré !
