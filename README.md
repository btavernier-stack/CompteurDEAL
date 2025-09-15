[README.txt](https://github.com/user-attachments/files/22350923/README.txt)
# Compteur d'attente – Version 100% HTML (sans serveur)

Deux fichiers :
- `admin.html` : contrôle du numéro (−1, +1, aller à…, reset)
- `display.html` : grand affichage pour les clients

## Comment ça marche
- Les deux pages **communiquent via `BroadcastChannel` et `localStorage`**.
- Ouvre `admin.html` dans un onglet, `display.html` dans un autre (même navigateur/PC).
- Chaque action dans l'admin met à jour l'affichage **en temps réel**.

> Astuce : si vous ouvrez les fichiers en `file://`, certains navigateurs limitent les événements inter‑onglets. Le code inclut un **fallback par petit polling** sur `display.html`. Pour un fonctionnement optimal, servez les fichiers via un petit serveur statique (ex. `python -m http.server`).

## Personnaliser
- Couleurs/typo : tout est en `<style>` dans chaque fichier.
- Message sous le numéro : modifiez l'élément `.subtext` dans `display.html`.

## Limites
- Sans backend, la synchro fonctionne **entre onglets du même navigateur/origine**. Pour des écrans sur des machines différentes (ou à distance), utilisez la version Node/Socket.IO ou branchez un backend temps réel (Firebase, Supabase, etc.).
