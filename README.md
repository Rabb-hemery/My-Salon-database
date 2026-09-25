# My-Salon-database
Interactive Bash script to manage hair salon appointments with PostgreSQL — freeCodeCamp project

# Salon Appointment Scheduler

An interactive Bash script connected to a PostgreSQL database to manage appointment bookings in a hair salon.

## Description

This project allows a customer to:
- Choose a service from a provided list
- Log in using their phone number (or create a customer account if they are new)
- Choose an appointment time
- Get a booking confirmation

## Database Structure

| Table          | Columns | Description |
|----------------|---------|-------------|
| `customers`    | `customer_id` (PK), `name`, `phone` (UNIQUE) | Salon customers |
| `services`     | `service_id` (PK), `name` | Services offered (cut, color, perm, etc.) |
| `appointments` | `appointment_id` (PK), `customer_id` (FK), `service_id` (FK), `time` | Scheduled appointments |

## Files

- `salon.sql` — full database dump (structure + data)
- `salon.sh` — interactive Bash appointment booking script

## Usage

Rebuild the database:
```bash
psql -U postgres < salon.sql
```

Run the script:
```bash
chmod +x salon.sh
bash salon.sh
```

## Usage Example
```
Welcome to My Salon, how can I help you?

1) cut
2) color
3) perm
4) style
5) trim

I have put you down for a cut at 10:30, Fabio.
```
