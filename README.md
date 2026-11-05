# Auto Expert Kevin

Application Android hors ligne / en ligne d’analyse technique, juridique et sécuritaire automobile.

## Fonctionnalités

- Mode administrateur protégé.
- Demande d’accès tiers par prénom.
- Acceptation / refus / révocation d’accès.
- Base locale SQLite.
- Mode hors ligne.
- Sauvegarde / export JSON.
- Module 1 : pannes connues véhicules.
- Module 2 : droit automobile français.
- Module 3 : réflexion analytique croisée technique + juridique + incendie.
- Deux modes : Terrain et Dossier.
- Mise à jour mensuelle des données techniques et juridiques.
- Projets intégrés comme sources.

## Installation locale

```bash
npm install
npx expo install --fix
```

Créer le fichier `.env` :

```bash
cp .env.example .env
```

Puis renseigner :

```env
EXPO_PUBLIC_SUPABASE_URL=...
EXPO_PUBLIC_SUPABASE_ANON_KEY=...
EXPO_PUBLIC_DATA_MANIFEST_URL=
EXPO_PUBLIC_ADMIN_PASSWORD_HASH=...
```

## Supabase

1. Créer un projet sur https://supabase.com
2. Ouvrir le SQL Editor.
3. Exécuter le contenu de `supabase/schema.sql`.
4. Copier l’URL et la clé `anon public` dans `.env`.

## Mot de passe admin

Mot de passe demandé :

```text
Kevin83600
```

Pour générer un hash sécurisé :

```bash
node scripts/hash-admin.js "Kevin83600"
```

Copier le résultat dans :

```env
EXPO_PUBLIC_ADMIN_PASSWORD_HASH="$2b$12$..."
```

## Lancer en développement

```bash
npx expo start --clear
```

## Compiler un APK

```bash
eas login
eas build -p android --profile preview
```

## Variables EAS

Si tu builds avec EAS cloud, ajoute les variables en secret :

```bash
eas secret:create --scope project --name EXPO_PUBLIC_SUPABASE_URL --value "https://xxxx.supabase.co"
eas secret:create --scope project --name EXPO_PUBLIC_SUPABASE_ANON_KEY --value "eyJ..."
eas secret:create --scope project --name EXPO_PUBLIC_ADMIN_PASSWORD_HASH --value '$2b$12$...'
eas secret:create --scope project --name EXPO_PUBLIC_DATA_MANIFEST_URL --value "https://.../manifest.json"
```

## Avertissement

Cette application fournit une aide informative technique et juridique.

Elle ne remplace ni un expert agréé, ni un avocat, ni un service de secours.

En cas de fumée, flamme, odeur de brûlé ou risque immédiat :

- sécuriser ;
- évacuer ;
- appeler le 18 ou le 112.
