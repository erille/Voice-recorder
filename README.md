# 🎙️ Voice Training Dataset Recorder

Une application web moderne et élégante pour enregistrer des phrases vocales et créer un dataset d'entraînement pour l'IA vocale.

## ✨ Fonctionnalités

- **🎨 Interface moderne** avec design pastel et animations fluides
- **🎤 Sélection intelligente du microphone** (évite automatiquement le microphone intégré)
- **📱 Design responsive** qui s'adapte aux mobiles et tablettes
- **🔧 Sélection manuelle du microphone** si nécessaire
- **📊 Progression en temps réel** avec indicateur de phrases
- **💾 Téléchargement automatique** des fichiers WAV
- **🎯 Gestion d'erreurs robuste** avec messages informatifs
- **⚡ Performance optimisée** avec nettoyage automatique des ressources

## 🚀 Utilisation

### Démarrage rapide

1. **Ouvrez le fichier** `record-voice-dataset.html` dans votre navigateur
2. **Autorisez l'accès au microphone** quand demandé
3. **Cliquez sur "🎙️ Démarrer"** pour commencer l'enregistrement
4. **Lisez la phrase affichée** à voix haute
5. **Cliquez sur "⏹️ Arrêter"** pour terminer et télécharger le fichier
6. **Cliquez sur "➡️ Suivante"** pour passer à la phrase suivante

### Sélection du microphone

Si l'application n'utilise pas le bon microphone :

1. **Cliquez sur "🎤 Choisir Microphone"**
2. **Sélectionnez le numéro** de votre microphone dans la liste
3. **Confirmez** votre choix

## 📁 Structure des fichiers

```
Voice-training/
├── record-voice-dataset.html    # Application principale
├── metadata_formatted.json      # Métadonnées des phrases
└── README.md                    # Ce fichier
```

## 🎵 Fichiers générés

L'application génère des fichiers WAV avec la nomenclature suivante :
- `1.wav` - Première phrase
- `2.wav` - Deuxième phrase
- `3.wav` - Troisième phrase
- etc.

## 🛠️ Technologies utilisées

- **HTML5** - Structure de l'application
- **CSS3** - Design moderne avec animations
- **JavaScript ES6+** - Logique de l'application
- **Web Audio API** - Gestion de l'audio
- **MediaDevices API** - Accès au microphone
- **Recorder.js** - Enregistrement audio

## 📋 Prérequis

- **Navigateur moderne** (Chrome, Firefox, Safari, Edge)
- **Connexion HTTPS** ou serveur local (requis pour l'accès au microphone)
- **Microphone** connecté et fonctionnel

## 🔧 Installation

### Option 1 : Serveur local (recommandé)

```bash
# Avec Python
python -m http.server 8000

# Avec Node.js
npx serve .

# Avec PHP
php -S localhost:8000
```

Puis ouvrez `http://localhost:8000/record-voice-dataset.html`

### Option 2 : Serveur HTTPS

Déployez le fichier sur un serveur HTTPS pour un accès direct.

## 🎯 Personnalisation

### Modifier les phrases

Éditez le tableau `phrases` dans le fichier HTML :

```javascript
const phrases = [
  { id: 1, phrase: "Votre phrase personnalisée" },
  { id: 2, phrase: "Une autre phrase" },
  // ...
];
```

### Ajuster les paramètres audio

Modifiez les contraintes audio dans la fonction `startRecording()` :

```javascript
const audioConstraints = {
  audio: {
    deviceId: defaultMicrophoneId ? { exact: defaultMicrophoneId } : undefined,
    echoCancellation: true,    // Annulation d'écho
    noiseSuppression: true,    // Suppression du bruit
    autoGainControl: true      // Contrôle automatique du gain
  }
};
```

## 🐛 Dépannage

### Problèmes courants

**❌ "Permission refusée"**
- Cliquez sur l'icône caméra/microphone dans la barre d'adresse
- Autorisez l'accès au microphone
- Actualisez la page

**❌ "Microphone utilisé par une autre application"**
- Fermez Skype, Teams, Discord, etc.
- Vérifiez qu'aucune autre application n'utilise le microphone

**❌ "Recorder.js n'est pas chargé"**
- Vérifiez votre connexion internet
- Actualisez la page (F5)

**❌ "getUserMedia nécessite HTTPS"**
- Utilisez un serveur local ou HTTPS
- Ne pas ouvrir le fichier directement (file://)

### Logs de débogage

Ouvrez la console (F12) pour voir les logs détaillés :
- Détection des microphones
- Sélection du périphérique
- État de l'enregistrement

## 📊 Dataset généré

L'application crée un dataset structuré :
- **Fichiers audio** : `1.wav`, `2.wav`, `3.wav`, etc.
- **Qualité** : 44.1kHz, mono, WAV
- **Métadonnées** : Correspondance phrase ↔ fichier via l'ID

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à :
- Signaler des bugs
- Proposer des améliorations
- Ajouter de nouvelles fonctionnalités

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

## 🙏 Remerciements

- [Recorder.js](https://github.com/mattdiamond/Recorderjs) pour l'enregistrement audio
- La communauté Web Audio API pour les exemples et la documentation

---

**Créé avec ❤️ pour l'entraînement de modèles vocaux**
