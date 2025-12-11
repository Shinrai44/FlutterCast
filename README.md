# FlutterRun + scrcpy (USB → WiFi)

Ce petit outil permet de lancer :

- **scrcpy** (cast Android)
- **flutter run** sur un téléphone **via Wi-Fi**, automatiquement
- bascule USB → WiFi sans configuration manuelle
- et relance rapide sans re-demander les autorisations

---

## 📦 Installation

1. **Télécharger ce dépôt Git**  
   (ZIP ou `git clone`)

2. **Placer le dossier dans :**

```
C:\
```

Vous devez obtenir quelque chose comme :

```
C:\FlutterCast\flutterrun.bat
C:\FlutterCast\scrcpy-win64-xxxx\
C:\FlutterCast\README.md
```

3. **Ajouter le dossier `C:\FlutterCast` dans le PATH Windows**

### Windows 10/11 :

- Ouvrir **Paramètres**
- Système → Informations système
- Paramètres système avancés → Variables d’environnement
- Sélectionner `Path`
- Cliquer sur **Modifier**
- Ajouter :

```
C:\FlutterCast
```

4. Vérifier dans un nouveau terminal :

```
flutterrun
```

Si la commande est reconnue → c’est bon.

---

## 📱 Préparation du téléphone Android

1. **Activer les options développeur**
2. Activer **Débogage USB**
3. Brancher le téléphone en USB
4. **Accepter la popup "Autoriser le débogage USB"**

---

## 🚀 Utilisation

Dans n’importe quel projet Flutter :

1. Ouvrir un terminal dans le dossier du projet
2. Exécuter :

```
flutterrun
```

3. Le script va :

   - détecter le téléphone en USB
   - récupérer son IP
   - activer le mode TCP/IP
   - demander d’accepter la popup **Débogage Wi-Fi**
   - ouvrir scrcpy
   - lancer `flutter run` via Wi-Fi

4. Quand le script affiche :

```
Flutter is now running over WiFi.
You may disconnect the USB cable.
```

➡️ Vous pouvez **débrancher le câble USB**.

---

## 🔁 Utilisation ultérieure (Wi-Fi déjà configuré)

Si le téléphone a déjà été autorisé :

- `flutterrun` va directement se connecter en Wi-Fi
- **scrcpy ne sera pas relancé si déjà ouvert**
- aucune popup ne sera demandée

---

## 🛠 Dépendances (automatiquement vérifiées)

Le script vérifie automatiquement :

- `adb`
- `flutter`
- `scrcpy.exe`

Si quelque chose manque, un message clair s’affiche.

---

## ❓ Problèmes fréquents

### Le cast ne s’ouvre pas

→ Vérifiez que `SCRCPY_EXE` pointe vers le bon chemin dans `flutterrun.bat`.

### Le Wi-Fi ne se connecte pas

→ Acceptez la popup “Débogage Wi-Fi” sur le téléphone.

### "Device unauthorized"

→ Débranchez/Rebranchez en USB et réacceptez la popup USB.

---

## ✔️ C’est tout !

Le script est maintenant prêt pour un usage quotidien simple, rapide et fiable.

Si vous souhaitez une version améliorée (interface, menu, couleurs, logs, exe portable), demandez-nous !
