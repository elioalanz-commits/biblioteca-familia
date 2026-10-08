# Biblioteca familiar de Steam

Inventario de los juegos del grupo familiar de Steam y votación para decidir qué comprar.

- `index.html`: la página completa (biblioteca, votación e integrantes con sus wishlists).
- Los votos, candidatos e integrantes se guardan en Firebase Firestore. Pega la configuración del proyecto en `FIREBASE_CONFIG`, al principio del script de `index.html`.

## Reglas de Firestore

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /candidates/{id} { allow read, write: if true; }
    match /votes/{id} { allow read, write: if true; }
    match /members/{id} { allow read, write: if true; }
  }
}
```
