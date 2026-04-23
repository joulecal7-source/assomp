# 🏢 Structure du Bâtiment - ASSOMP

## Vue d'Ensemble

Ton centre a **90 lits** répartis sur **2 étages actifs** (Étage 2 et Étage 3).

```
🏢 ÉTAGE 1: Vide (non utilisé)
🏢 ÉTAGE 2: 39 lits (201-2023, sauf 2012 et 2013)
🏢 ÉTAGE 3: 51 lits (301-3027, sauf 3026)
────────────────────────────────
TOTAL: 90 lits ✓
```

---

## 📊 ÉTAGE 2 - 39 Lits

### Composition:

| Type | Numéros | Nombre Lits | Détails |
|:---|:---|:---:|:---|
| **Chambres Simples** | 201-205 | 5 lits | 1 lit par chambre (5 chambres) |
| **Chambres Doubles** | 206-211 | 12 lits | 2 lits par chambre (6 chambres) |
| **Chambres Doubles** | 2014-2023 | 20 lits | 2 lits par chambre (10 chambres) |
| **INEXISTANTS** | 2012-2013 | - | ❌ Ces numéros n'existent pas |
| **TOTAL ÉTAGE 2** | - | **39 lits** | |

### Structure Visuelle:

```
🏢 ÉTAGE 2

Chambres Simples (1 lit):
┌─────────────────────────────────────────┐
│ 201 │ 202 │ 203 │ 204 │ 205            │
│ [1] │ [1] │ [1] │ [1] │ [1]            │
└─────────────────────────────────────────┘

Chambres Doubles (2 lits):
┌──────────────────────┐  ┌──────────────────────┐
│ 206A  │  206B        │  │ 207A  │  207B        │
│ [1]   │  [1]         │  │ [1]   │  [1]         │
└──────────────────────┘  └──────────────────────┘

... (206-211) ...

⚠️ SAUTÉ: 2012, 2013 (N'EXISTENT PAS)

┌──────────────────────┐  ┌──────────────────────┐
│ 2014A │  2014B       │  │ 2015A │  2015B       │
│ [1]   │  [1]         │  │ [1]   │  [1]         │
└──────────────────────┘  └──────────────────────┘

... (2014-2023) ...
```

### Comment C'est Identifié dans ASSOMP:

- **Chambres simples:** `201`, `202`, `203`, `204`, `205`
- **Chambres doubles:** `206A`, `206B`, `207A`, `207B`, ..., `2023A`, `2023B`

**Exemple:**
```
Chambre 208:
├── Lit 208A (Patient 1)
└── Lit 208B (Patient 2)
```

---

## 📊 ÉTAGE 3 - 51 Lits

### Composition:

| Type | Numéros | Nombre Lits | Détails |
|:---|:---|:---:|:---|
| **Chambres Simples** | 301-305 | 5 lits | 1 lit par chambre (5 chambres) |
| **Chambres Doubles** | 306-325 | 40 lits | 2 lits par chambre (20 chambres) |
| **Chambres Doubles** | 3027 | 2 lits | 1 chambre avec 2 lits |
| **INEXISTANT** | 3026 | - | ❌ Ce numéro n'existe pas |
| **TOTAL ÉTAGE 3** | - | **51 lits** | |

### Structure Visuelle:

```
🏢 ÉTAGE 3

Chambres Simples (1 lit):
┌─────────────────────────────────────────┐
│ 301 │ 302 │ 303 │ 304 │ 305            │
│ [1] │ [1] │ [1] │ [1] │ [1]            │
└─────────────────────────────────────────┘

Chambres Doubles (2 lits):
┌──────────────────────┐  ┌──────────────────────┐
│ 306A  │  306B        │  │ 307A  │  307B        │
│ [1]   │  [1]         │  │ [1]   │  [1]         │
└──────────────────────┘  └──────────────────────┘

... (306-325) ...

⚠️ SAUTÉ: 3026 (N'EXISTE PAS)

┌──────────────────────┐
│ 3027A │  3027B       │
│ [1]   │  [1]         │
└──────────────────────┘
```

### Comment C'est Identifié dans ASSOMP:

- **Chambres simples:** `301`, `302`, `303`, `304`, `305`
- **Chambres doubles:** `306A`, `306B`, `307A`, `307B`, ..., `3027A`, `3027B`

---

## 🔑 Système de Numérotation

### Format Standard:

```
[Étage][Numéro Chambre][A ou B pour doubles]
     ↓         ↓                    ↓
   Étage    Chambre         Lit A = Premier lit
                            Lit B = Deuxième lit
```

### Exemples:

| Code | Signification | Type |
|:---|:---|:---|
| **201** | Étage 2, Chambre 201 | Chambre simple |
| **208A** | Étage 2, Chambre 208, Lit A | Chambre double |
| **208B** | Étage 2, Chambre 208, Lit B | Chambre double |
| **301** | Étage 3, Chambre 301 | Chambre simple |
| **3027A** | Étage 3, Chambre 3027, Lit A | Chambre double |

---

## 📱 Utilisation dans ASSOMP

### Pour les Préposés:

1. **Ouvre ASSOMP**
2. **Connecte-toi** (PREP001 / 1234)
3. **Choisis ton quart** (Matin/Midi/Soir)
4. **Filtre par étage** (Étage 2, Étage 3, ou Tous)
   ```
   [📋 Tous les Étages] [🏢 Étage 2] [🏢 Étage 3]
   ```
5. **Tu vois les bénéficiaires de cet étage**
   ```
   Exemple - Étage 2:
   ┌─────────────────────┐
   │ Patient 201         │
   │ ID: B001 | 👤 Simple│
   │ 🛏️ Lit 201 | 🏢 Étage 2│
   ├─────────────────────┤
   │ ☐ 🚽 Besoin...      │
   │ ☐ 🍽️ Besoin...      │
   ```
6. **Enregistre les soins** comme d'habitude

### Pour les Chefs:

- Le **Tableau de Bord** montre **tous les étages**
- Les **Rapports** incluent les informations d'étage
- Les **Données** sont triées par étage

---

## 🔍 Points Importants à Mémoriser

### ⚠️ Numéros Manquants:

- **Étage 2:** Les lits **2012** et **2013** N'EXISTENT PAS
- **Étage 3:** Le lit **3026** N'EXISTE PAS

Ces numéros ne sont pas dans l'app (ils sont sautés).

### 👥 Chambres Doubles vs Simples:

- **Simples:** 1 lit par chambre (ex: 201, 202, 301, 302)
- **Doubles:** 2 lits par chambre (ex: 206A/B, 307A/B)

Dans ASSOMP, chaque **lit** est une ligne séparée, même dans les doubles.

### 🏢 Étage Vide:

- **Étage 1:** N'est pas utilisé actuellement
- L'app ne l'affiche pas (seulement Étages 2 et 3)

---

## 📊 Statistiques

### Par Étage:

| Étage | Chambres | Lits | Simples | Doubles |
|:---|:---:|:---:|:---:|:---:|
| Étage 2 | 23 | 39 | 5 | 18 |
| Étage 3 | 26 | 51 | 5 | 21 |
| **TOTAL** | **49** | **90** | **10** | **39** |

### Capacité:

```
🏢 Total: 90 lits
├── 49 chambres
├── 10 chambres simples (1 lit)
└── 39 chambres doubles (2 lits)
```

---

## 🎯 Cas d'Usage Courants

### Scenario 1: Préposé Étage 2, Quart Matin

```
1. Connecte-toi: PREP001 / 1234
2. Sélectionne: Matin (06h-14h)
3. Filtre: Étage 2
4. Vois les 39 lits de l'Étage 2
5. Enregistre les soins (2-3 min par lit)
6. Termine quand tous sont fait
7. Déconnexion
```

### Scenario 2: Chef Vérification Quotidienne

```
1. Connecte-toi: CHEF001 / 1234
2. Consulte le Tableau de Bord
3. Vois les stats: ✅9/9 ⚠️5/9 ❌0/9
4. Analyse par étage si nécessaire
5. Imprime le rapport PDF
6. Archive le document
```

### Scenario 3: Chercher un Lit Spécifique

```
Cherche: Patient au lit 208B

1. Filtre par Étage 2
2. Cherche "208B" dans la liste
3. Trouve la chambre double 208
   ├── Lit 208A
   └── Lit 208B ← Celui-ci
4. Enregistre les soins
```

---

## 🔧 Configuration (Pour Admin)

Si tu dois ajouter des bénéficiaires, assure-toi de respecter:

```javascript
{
    id: 'BXXX',           // ID unique (B001, B002, etc.)
    name: 'Nom Patient',  // Nom du patient
    bed: '208A',          // Numéro du lit (avec A/B si double)
    floor: 2,             // Étage (2 ou 3)
    roomType: 'double'    // 'simple' ou 'double'
}
```

**Exemple:**
```javascript
{ 
    id: 'B050', 
    name: 'Jean Martin', 
    bed: '208B', 
    floor: 2, 
    roomType: 'double' 
}
```

---

## 📞 Questions Fréquentes

### Q: Où sont les lits 2012 et 2013?
A: Ils n'existent pas physiquement dans ton bâtiment. L'app les saute automatiquement.

### Q: Pourquoi 208A et 208B?
A: Parce que la chambre 208 a 2 lits. Le A = premier lit, B = deuxième lit.

### Q: Est-ce que je dois enregistrer les chambres ou les lits?
A: Les **lits**! Chaque lit est enregistré séparément dans ASSOMP.

### Q: Pourquoi l'Étage 1 n'est pas visible?
A: Parce qu'il n'a pas de patients actuellement. Tu peux l'ajouter plus tard si besoin.

### Q: Comment imprimer un rapport par étage?
A: Les chefs peuvent exporter les données et les filtrer dans Excel.

---

## 📝 Notes Importantes

✅ **Structure mise à jour:** ASSOMP connaît exactement la structure de ton bâtiment  
✅ **Lits manquants saisis:** Les lits 2012, 2013, 3026 sont automatiquement sautés  
✅ **Doublons gérés:** Les chambres doubles (A/B) sont bien distinguées  
✅ **Filtrage par étage:** Les préposés peuvent voir seulement leur étage  

---

## 🎓 Résumé Rapide

```
📊 ÉTAGE 2 (39 lits):
   201-205 (simples, 5 lits)
   206-211 + 2014-2023 (doubles, 34 lits)
   ❌ Pas de 2012, 2013

📊 ÉTAGE 3 (51 lits):
   301-305 (simples, 5 lits)
   306-325 + 3027 (doubles, 46 lits)
   ❌ Pas de 3026

🏢 TOTAL: 90 lits | 49 chambres
```

---

**Version:** 1.0  
**Dernière mise à jour:** Avril 2026
