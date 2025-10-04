<p align="center">
  <img src="https://i.imgur.com/qNc8JE0.png" alt="Jackett Ygg-API Logo">
</p>

<h1 align="center">Jackett Ygg-API Fork</h1>

<p align="center">
  <a href="#-english">English</a> |
  <a href="#-français">Français</a>
</p>

---

# <img src="https://www.drapeauxdespays.fr/data/flags/emoji/twitter/32x32/us.png"> English

# Jackett Ygg-API Fork

Fork of [Jackett](https://github.com/linuxserver/jackett) integrating **YggTorrent indexer** via **Ygg-API**.

The YggTorrent indexer is configured from this file:  
[Ygg-API Download YAML](https://gist.github.com/Clemv95/8bfded23ef23ec78f6678896f42a2b60#file-ygg-api-download-yml)

---

## Docker Compose Exemple

Make `docker-compose.yml` with following content :

```yaml
services:
  jackett:
    image: mwhax7/jackett-ygg:latest
    container_name: jackett
    environment:
      - PUID=1000        # User ID
      - PGID=1000        # Group ID
    volumes:
      - ./config/jackett:/config   # local path for persitant configuration
    ports:
      - 9117:9117       # WebUI Port
    restart: unless-stopped
```

---

## Adding the YggTorrent Indexer

1. In the Jackett web interface, click **Add Indexer → YggTorrent**.  
2. Enter your YggTorrent Passkey, others preferences and save.  
3. Copy the **Torznab feed URL** for use with Sonarr, Radarr, etc.  

---

## Integration with Sonarr / Radarr

1. Go to **Settings → Indexers → Add → Torznab** in Sonarr or Radarr.  
2. Fill in the fields:  
   - **Name**: YggTorrent-Jackett  
   - **Feed URL**: Paste the URL copied from Jackett  
   - **API Key**: Use the API key displayed in Jackett  
3. Click **Test**, then **Save**.

---

## Credits

[Jackett](https://github.com/Jackett/Jackett)

[Ygg-API](https://yggapi.eu/)

[Clemv95](https://github.com/Clemv95)

---
---

# <img src="https://www.drapeauxdespays.fr/data/flags/emoji/twitter/32x32/fr.png"> Français

# Jackett Ygg-API Fork

Fork de [Jackett](https://github.com/linuxserver/jackett) intégrant l’**indexeur YggTorrent** via **Ygg-API**.

L’indexeur YggTorrent est configuré à partir de ce fichier :  
[Ygg-API Download YAML](https://gist.github.com/Clemv95/8bfded23ef23ec78f6678896f42a2b60#file-ygg-api-download-yml)

---

## Exemple Docker Compose

Créez un fichier `docker-compose.yml` avec le contenu suivant :

```yaml
services:
  jackett:
    image: mwhax7/jackett-ygg:latest
    container_name: jackett
    environment:
      - PUID=1000        # ID utilisateur
      - PGID=1000        # ID groupe
    volumes:
      - ./config/jackett:/config   # chemin local pour la configuration persistante
    ports:
      - 9117:9117       # Port WebUI
    restart: unless-stopped
```

---

## Ajouter l’indexeur YggTorrent

1. Dans l’interface web Jackett, cliquez sur **Add Indexer → YggTorrent**.
2. Entrez votre Passkey YggTorrent, autres paramètres et sauvegardez.
3. Copy the **Torznab feed URL** for use with Sonarr, Radarr, etc.

---

## Intégration avec Sonarr / Radarr

1. Allez dans **Settings → Indexers → Add → Torznab** dans Sonarr ou Radarr.
2. Remplissez les champs:
   - **Name**: YggTorrent-Jackett
   - **Feed URL**: Collez l'URL copiée depuis Jackett
   - **API Key**: Ultilisez la clé API affichée sur Jackett
3. Cliquez sur **Test**, puis **Save**.

---

## Crédits

[Jackett](https://github.com/Jackett/Jackett)

[Ygg-API](https://yggapi.eu/)

[Clemv95](https://github.com/Clemv95)
