# My-Salon-database
Script bash interactif pour gérer les rendez-vous d'un salon de coiffure avec PostgreSQL — projet freeCodeCamp
# Salon Appointment Scheduler

Script bash interactif connecté à une base de données PostgreSQL pour gérer la prise de rendez-vous dans un salon de coiffure.

## Description

Ce projet permet à un client de :
- choisir un service parmi une liste proposée
- s'identifier via son numéro de téléphone (ou créer un compte client s'il est nouveau)
- choisir une heure de rendez-vous
- obtenir une confirmation de réservation

## Structure de la base de données

| Table          | Colonnes | Description |
|----------------|----------|--------------|
| `customers`    | `customer_id` (PK), `name`, `phone` (UNIQUE) | Clients du salon |
| `services`     | `service_id` (PK), `name` | Services proposés (coupe, couleur, permanente, etc.) |
| `appointments` | `appointment_id` (PK), `customer_id` (FK), `service_id` (FK), `time` | Rendez-vous pris |

## Fichiers

- `salon.sql` — dump complet de la base (structure + données)
- `salon.sh` — script bash interactif de prise de rendez-vous

## Utilisation

Reconstruire la base de données :
```bash
psql -U postgres < salon.sql
```

Lancer le script :
```bash
chmod +x salon.sh
bash salon.sh
```

## Exemple d'utilisation
