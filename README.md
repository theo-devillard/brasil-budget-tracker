# Budget de Léa - Brésil Automne 2025 🇧🇷

Une application web progressive (PWA) de gestion de budget pour l'échange au Brésil. Cette application permet de planifier, suivre et gérer les finances pendant un séjour à l'étranger avec support des devises CAD et BRL.

## 🌟 Fonctionnalités

### 📊 Tableau de Bord Principal
- **Vue d'ensemble financière** : Solde actuel, progression du budget, dépenses totales
- **Cartes récapitulatives** : Affichage en temps réel des métriques clés
- **Graphiques interactifs** : Visualisation des revenus vs dépenses
- **Transactions récentes** : Liste des 10 dernières transactions
- **Actions rapides** : Ajout rapide de dépenses et revenus

### 📅 Gestion Mensuelle
- **Navigation par mois** : Parcourir les différents mois de l'échange
- **Résumé mensuel** : Revenus et dépenses du mois sélectionné
- **Planification vs Réalité** : Comparaison entre budget prévu et dépenses réelles
- **Graphiques détaillés** :
  - Répartition des dépenses par catégories (camembert)
  - Revenus vs Dépenses planifiés vs réels (barres)

### ⚙️ Paramètres et Configuration
- **Dates d'échange** : Configuration des dates de début et fin de séjour
- **Solde initial** : Définition du solde de départ avec date de référence
- **Transactions récurrentes** : 
  - Revenus mensuels (salaire, bourses, etc.)
  - Dépenses mensuelles (loyer, transport, etc.)
- **Catégories personnalisées** : Création et gestion de catégories avec émojis
- **Gestion des données** : Export/import JSON, réinitialisation complète

### 💱 Support Multi-Devises
- **CAD (Dollar Canadien)** et **BRL (Real Brésilien)**
- **Taux de change** : 1 CAD = 3.7 BRL (configurable)
- **Affichage dual** : Montants affichés dans les deux devises
- **Saisie flexible** : Possibilité d'entrer les montants dans l'une ou l'autre devise

### 📱 Progressive Web App (PWA)
- **Installation native** : Ajout à l'écran d'accueil sur mobile
- **Fonctionnement hors-ligne** : Données stockées localement
- **Interface responsive** : Optimisée pour mobile et desktop
- **Support tactile** : Navigation adaptée aux écrans tactiles

## 🚀 Déploiement GitHub Pages

### Accès en ligne
L'application est déployée sur GitHub Pages et accessible à l'adresse :
```
https://[votre-username].github.io/[nom-du-repository]/
```

### Installation comme PWA
1. **Sur mobile** : Ouvrir l'URL dans Safari/Chrome → "Ajouter à l'écran d'accueil"
2. **Sur desktop** : Cliquer sur l'icône d'installation dans la barre d'adresse du navigateur

## 🛠️ Développement Local

### Structure du Projet
```
brasil_budget/
├── index.html              # Application principale
├── manifest.json           # Métadonnées PWA
├── icon-192x192.png        # Icône 192x192
├── icon-512x512.png        # Icône 512x512
├── brasil_real_app_icon.svg # Icône source SVG
└── README.md               # Documentation
```

### Lancement Local
1. Cloner le repository
2. Ouvrir `index.html` dans un navigateur moderne
3. Ou utiliser un serveur local :
```bash
# Python 3
python -m http.server 8000

# Node.js (si http-server est installé)
npx http-server

# PHP
php -S localhost:8000
```

## 🎨 Interface Utilisateur

### Design
- **Thème** : Couleurs du drapeau brésilien (vert, jaune, bleu)
- **Typographie** : Police système Apple/Google pour une meilleure lisibilité
- **Icônes** : Émojis pour une interface universelle et ludique
- **Responsive** : Grid CSS adaptatif pour tous les écrans

### Navigation
- **Onglets principaux** : Accueil, Mensuel, Paramètres
- **Modales** : Ajout/édition de transactions
- **Boutons d'action** : Actions rapides accessibles depuis l'accueil

## 💾 Stockage des Données

### Local Storage
- **Persistance locale** : Toutes les données sont sauvegardées dans le navigateur
- **Sauvegarde automatique** : Enregistrement après chaque modification
- **Pas de serveur requis** : Fonctionnement 100% côté client

### Format des Données
```json
{
  "total": 5000,
  "initialBalance": 2000,
  "currentBalance": 1800,
  "balanceDate": "2025-08-01",
  "balanceHistory": [
    {"date": "2025-08-01", "balance": 1800}
  ],
  "startDate": "2025-08-15",
  "endDate": "2025-12-15",
  "expenses": [...],
  "income": [...],
  "recurringIncome": [...],
  "recurringExpenses": [...],
  "customCategories": [...]
}
```

### Sauvegarde et Restauration
- **Export JSON** : Téléchargement du fichier de données
- **Import JSON** : Restauration depuis un fichier de sauvegarde
- **Réinitialisation** : Suppression complète des données

## 📊 Fonctionnalités Analytiques

### Graphiques
- **Chart.js** : Bibliothèque de graphiques interactive
- **Graphiques en temps réel** : Mise à jour automatique lors des modifications
- **Types supportés** :
  - Barres (revenus vs dépenses)
  - Camembert (répartition par catégories)
  - Lignes (évolution du solde et projections)

### Projections Financières
- **Projection quotidienne** : Calcul du solde futur basé sur les transactions récurrentes
- **Adaptation intelligente** : Ajustement des projections selon les soldes réels enregistrés
- **Visualisation combinée** : Superposition des données réelles et des projections

## 🏗️ Technologies Utilisées

### Frontend
- **HTML5** : Structure sémantique
- **CSS3** : Grid, Flexbox, Variables CSS, Responsive Design
- **JavaScript (ES6+)** : Modules, Async/Await, Classes
- **Chart.js** : Visualisation de données
- **PWA** : Service Worker, Web App Manifest

### Fonctionnalités Modernes
- **LocalStorage API** : Persistance des données
- **Date API** : Gestion des dates et calculs temporels
- **Touch Events** : Support tactile optimisé
- **Responsive Design** : Media queries CSS
- **Web App Manifest** : Installation PWA

## 🔧 Configuration Avancée

### Personnalisation du Taux de Change
Modifier la variable `exchangeRate` dans le code JavaScript :
```javascript
const exchangeRate = 3.7; // 1 CAD = 3.7 BRL
```

### Ajout de Nouvelles Catégories
Les catégories par défaut incluent :
- 🏠 Logement
- 🍽️ Alimentation  
- 🚌 Transport
- 🎭 Divertissement
- 📚 Éducation
- 🏥 Santé
- 👕 Vêtements
- 📋 Autre

### Modification des Couleurs
Les couleurs principales sont définies en CSS :
```css
:root {
  --primary-green: #009739;
  --primary-yellow: #FEDD00;
  --primary-blue: #002776;
}
```

## 🐛 Résolution de Problèmes

### Problèmes Courants

**L'application ne s'installe pas comme PWA**
- Vérifiez que les fichiers `manifest.json` et les icônes sont accessibles
- Utilisez HTTPS (GitHub Pages le fournit automatiquement)

**Les données disparaissent**
- Vérifiez que le LocalStorage n'est pas désactivé
- Évitez le mode navigation privée
- Utilisez la fonction d'export pour créer des sauvegardes

**Les graphiques ne s'affichent pas**
- Assurez-vous que JavaScript est activé
- Vérifiez la console pour d'éventuelles erreurs
- Rechargez la page (Ctrl+F5 / Cmd+R)

**Problèmes de date (1er du mois dans le mauvais mois)**
- Corrigé : Parsing de date amélioré pour éviter les décalages de fuseau horaire

**Interface non tactile sur iPhone**
- Corrigé : Ajout du support des événements tactiles et CSS adaptés

### Debug
Ouvrir les outils de développement (F12) et vérifier :
- Console : Messages d'erreur JavaScript
- Network : Chargement des ressources
- Application : LocalStorage et données PWA

## 📱 Compatibilité

### Navigateurs Supportés
- ✅ Chrome 80+
- ✅ Firefox 75+
- ✅ Safari 13+
- ✅ Edge 80+
- ✅ Chrome Mobile
- ✅ Safari Mobile

### Appareils Testés
- 📱 iPhone (iOS 13+)
- 📱 Android (Chrome)
- 💻 Windows (Chrome, Edge, Firefox)
- 💻 macOS (Safari, Chrome)
- 💻 Linux (Chrome, Firefox)

## 🚦 Statut du Projet

### Version Actuelle : 2.0
- ✅ Interface multi-pages (Accueil, Mensuel, Paramètres)
- ✅ Support complet CAD/BRL
- ✅ Graphiques interactifs
- ✅ PWA avec installation native
- ✅ Gestion avancée des transactions
- ✅ Projections financières intelligentes
- ✅ Support tactile optimisé
- ✅ Corrections de bugs de date et navigation

### Améliorations Futures Possibles
- 🔄 Synchronisation cloud optionnelle
- 📊 Rapports mensuels détaillés
- 🔔 Notifications de budget
- 💱 Taux de change en temps réel
- 📸 Scan de reçus
- 🏦 Catégories de banques
- 🎯 Objectifs d'épargne

## 📄 Licence

Ce projet est sous licence MIT. Vous êtes libre de l'utiliser, le modifier et le distribuer.

## 🤝 Contribution

Les contributions sont les bienvenues ! Pour contribuer :

1. Fork le projet
2. Créer une branche feature (`git checkout -b feature/nouvelle-fonctionnalite`)
3. Commiter les changements (`git commit -am 'Ajout nouvelle fonctionnalité'`)
4. Pusher la branche (`git push origin feature/nouvelle-fonctionnalite`)
5. Ouvrir une Pull Request

## 📞 Support

Pour toute question ou problème :
- 🐛 **Issues GitHub** : Signaler un bug ou demander une fonctionnalité
- 📧 **Contact** : [Votre email]
- 📖 **Documentation** : Ce README contient toutes les informations nécessaires

---

**Bon voyage au Brésil ! 🇧🇷✈️**

*Développé avec ❤️ pour faciliter la gestion financière pendant les échanges étudiants*