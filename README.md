# 🏥 ASSOMP - Système de Suivi des Soins

**ASSOMP** (Assistance et Suivi Systématique des Opérations Médicales et Paramédicales) est une **application web moderne** pour la gestion efficace des soins dans les centres de personnes âgées.

## 📋 Vue d'ensemble

ASSOMP permet aux **préposés aux bénéficiaires** de documenter rapidement et précisément les soins fournis, et aux **chefs de quart** d'avoir une **vue complète** de la situation du centre avec rapports et analyses.

### 🏢 Structure du Bâtiment

Ton centre a **90 lits** répartis sur **2 étages actifs:**

```
🏢 ÉTAGE 2: 39 lits (Chambres 201-2023, sauf 2012 & 2013)
   ├── Simples: 201-205 (5 lits)
   └── Doubles: 206-211 + 2014-2023 (34 lits avec A/B)

🏢 ÉTAGE 3: 51 lits (Chambres 301-3027, sauf 3026)
   ├── Simples: 301-305 (5 lits)
   └── Doubles: 306-325 + 3027 (46 lits avec A/B)
```

**📘 Documentation complète:** [BUILDING_STRUCTURE.md](./BUILDING_STRUCTURE.md)

---

#### Pour les Préposés
- ✅ Interface intuitive avec cases à cocher rapides
- ✅ Suivi par **quart de travail** (Matin/Midi/Soir)
- ✅ **9 types de soins** prédéfinis
- ✅ Espace pour notes, observations et incidents
- ✅ **Horodatage automatique** de chaque action
- ✅ Authentification sécurisée par ID + mot de passe
- ✅ **Sauvegarde instantanée** des données
- ✅ Compatible mobile et tablette

#### Pour les Chefs de Quart
- 📊 **Tableau de bord** avec statistiques en temps réel
- 📈 **Rapports détaillés** par date, bénéficiaire ou quart
- 🖨️ **Impression PDF** pour documentation journalière/hebdomadaire
- 📥 **Export CSV** pour archivage ou analyse
- ⚙️ **Administration** - gestion des préposés
- 🔍 **Vue d'ensemble** de tous les dossiers de bénéficiaires

---

## 🎯 Les 9 Types de Soins Suivis

1. 🚽 **Besoin d'élimination**
2. 🍽️ **Besoin de manger**
3. 🚿 **Bain partiel**
4. 🛁 **Bain complet**
5. 👕 **Changement de culotte quand mouillée**
6. ♻️ **Lavage des fauteuils roulants (nuit)**
7. 🍎 **Distribution de collations**
8. 💧 **Hydratation des patients**
9. 🛏️ **Vérification barrières lit/position baissée**

---

## 🚀 Démarrage Rapide

### Option 1: Utiliser Directement (Recommandé pour commencer)

1. **Télécharge le fichier** `index.html`
2. **Ouvre-le dans ton navigateur** (Chrome, Firefox, Safari, Edge)
3. **C'est prêt!** Aucune installation requise

### Identifiants de Test

**Préposé:**
```
ID: PREP001
Mot de passe: 1234
```

**Chef:**
```
ID: CHEF001
Mot de passe: 1234
```

### Option 2: Héberger sur GitHub Pages (Gratuit)

1. Crée un compte GitHub (https://github.com/signup)
2. Crée un nouveau repository appelé `assomp`
3. Upload le fichier et renomme-le en `index.html`
4. Va dans **Settings** → **Pages** → Sélectionne `main` branch
5. **Ton app sera accessible à:** `https://tonusername.github.io/assomp/`

---

## 📚 Documentation

### [Guide d'Utilisation pour les Préposés](./docs/PREPOSE_GUIDE.md)
Comment enregistrer les soins, ajouter des notes et utiliser l'application au quotidien.

### [Guide d'Utilisation pour les Chefs](./docs/CHEF_GUIDE.md)
Comment accéder au tableau de bord, générer des rapports et gérer les préposés.

### [Guide d'Administration](./docs/ADMIN_GUIDE.md)
Configuration initiale, gestion des utilisateurs et des bénéficiaires.

---

## 🔧 Caractéristiques Techniques

- **Frontend:** HTML5, CSS3, JavaScript vanilla
- **Stockage:** LocalStorage du navigateur (prototype)
- **Compatibilité:** Chrome, Firefox, Safari, Edge
- **Mobile:** Responsive design - fonctionne sur téléphone et tablette
- **Performance:** Rapide et léger (< 50KB)
- **Accessibilité:** Conforme aux standards WCAG

---

## 📊 Structure de l'Application

```
ASSOMP/
│
├── index.html              # Application principale
├── README.md               # Ce fichier
├── LICENSE                 # Licence MIT
│
├── docs/                   # Documentation
│   ├── PREPOSE_GUIDE.md   # Guide utilisateur - Préposés
│   ├── CHEF_GUIDE.md      # Guide utilisateur - Chefs
│   ├── ADMIN_GUIDE.md     # Guide administration
│   └── FEATURES.md        # Liste complète des fonctionnalités
│
└── examples/               # Exemples de données
    └── sample_data.json    # Données d'exemple
```

---

## 💾 Gestion des Données

### Actuellement
- Les données sont **stockées localement** dans le navigateur
- **Aucun serveur requis** - fonctionne 100% hors ligne
- Les données persistent jusqu'à suppression du cache

### Futures Améliorations (Optionnel)
- ☁️ Base de données cloud (Firebase, PostgreSQL)
- 🔐 Backend sécurisé avec hash de mots de passe
- 📱 Application mobile native
- 🔄 Synchronisation multi-appareils
- 📊 Analyses avancées et statistiques

---

## 🔐 Sécurité

### Actuellement
- ✅ Authentification par ID + mot de passe
- ✅ Sessions isolées par utilisateur
- ✅ Pas de données sensibles en cache

### Recommandations pour Production
- 🔒 Ajouter HTTPS (obligatoire)
- 🗝️ Implémenter OAuth ou JWT
- 🛡️ Chiffrer les données sensibles
- 📋 Audit trail complet des actions
- 🔐 Backup régulier des données

---

## 📋 Flux de Travail Typique

### Matin (Quart 06h-14h)

1. **Préposé se connecte** → ID PREP001 + mot de passe
2. **Sélectionne le quart** "Matin"
3. **Pour chaque bénéficiaire:**
   - ✅ Coche les soins fournis
   - 📝 Ajoute des notes si nécessaire
   - 💾 Données sauvegardées automatiquement
4. **Chef accède au tableau de bord:**
   - 📊 Voit le résumé de la journée
   - 🖨️ Imprime le rapport PDF
   - 📁 Archive la documentation

---

## 🎓 Exemples d'Utilisation

### Exemple 1: Enregistrement Simple
> Marie Dupont (PREP001) se connecte, sélectionne le matin, coche "Besoin de manger" et "Hydratation" pour M. Beaumont (Lit 101), ajoute une note "Patient en bonne santé", et la sauvegarde est automatique.

### Exemple 2: Rapport Quotidien
> Pierre Rousseau (CHEF001) ouvre le tableau de bord, voit que 85% des soins ont été enregistrés, imprime le rapport PDF pour les archives, et exporte un CSV pour analyse.

---

## 🤝 Contribution

Tu veux améliorer ASSOMP? 
- 💡 Signale les bugs
- 💬 Propose des améliorations
- 🔄 Crée une fork et fais des pull requests

---

## 📞 Support

### Questions Fréquemment Posées (FAQ)
[Voir la FAQ complète](./docs/FAQ.md)

### Besoin d'aide?
- 📧 Email: [Ton email]
- 💬 GitHub Issues: Ouvre une issue
- 📱 WhatsApp: [Ton numéro]

---

## 📄 Licence

Ce projet est sous **Licence MIT** - Tu es libre de l'utiliser, le modifier et le distribuer.

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, and/or sell
copies of the Software.
```

---

## 🎯 Feuille de Route Future

- [ ] Backend Node.js avec base de données
- [ ] Authentification Firebase
- [ ] Application mobile React Native
- [ ] Notifications en temps réel
- [ ] Statistiques avancées et dashboards
- [ ] Intégration avec dossiers patients
- [ ] SMS/Email automatiques
- [ ] API REST publique

---

## 👨‍💼 À Propos

**ASSOMP** a été créé pour **simplifier la documentation des soins** et **améliorer la qualité de service** dans les centres de personnes âgées.

**Visez:** Pas de paperasse, juste de bons soins documentés.

---

**Version:** 1.0.0  
**Dernière mise à jour:** Avril 2026  
**Statut:** ✅ Production-Ready (prototype)

---

⭐ **Si tu trouves ASSOMP utile, n'oublie pas de donner une star sur GitHub!** ⭐
