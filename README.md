# Tourisme Agency Platform - PFE

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js Version](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-6.0+-green)](https://www.mongodb.com/)
[![React](https://img.shields.io/badge/React-18.2.0-blue)](https://reactjs.org/)

## 📋 Table des matières
- [Description du projet](#description-du-projet)
- [Architecture technique](#architecture-technique)
- [Fonctionnalités](#fonctionnalités)
- [Sécurité](#sécurité)
- [Installation](#installation)
- [Structure du projet](#structure-du-projet)
- [API Documentation](#api-documentation)
- [Contributeurs](#contributeurs)
- [Licence](#licence)

## 🎯 Description du projet

Ce projet est mon Projet de Fin d'Études (PFE) qui consiste en le développement d'une plateforme web complète pour une agence touristique. L'objectif est de créer un écosystème digital permettant de gérer l'ensemble des services touristiques et d'interconnecter tous les acteurs du secteur.

La plateforme vise à centraliser et faciliter :
- La réservation de voyages et séjours
- La gestion des partenaires touristiques
- La coordination entre les différents prestataires
- L'expérience client de bout en bout

## 🏗 Architecture technique

### Technologies utilisées

#### Backend
- **Node.js** avec Express.js - Runtime JavaScript et framework web
- **MongoDB** avec Mongoose - Base de données NoSQL
- **JWT** - Gestion des tokens d'authentification
- **OAuth 2.0** - Authentification tierce (Google, Facebook)
- **NodeMailer** - Envoi d'emails transactionnels

#### Frontend
- **React 18** - Bibliothèque UI
- **Redux Toolkit** - Gestion d'état
- **React Router v6** - Routing
- **Axios** - Client HTTP
- **Material-UI/Tailwind** - Framework CSS (à choisir)

### Base de données
MongoDB avec les collections principales :
- Users (avec différents rôles)
- Hotels
- RentalProperties
- CarRentals
- FlightReservations
- Bookings
- Payments
- Reviews

## ✨ Fonctionnalités

### Gestion des utilisateurs et authentification
- ✅ Inscription/Connexion avec email
- ✅ Authentification via OAuth (Google, Facebook)
- ✅ Double authentification (2FA) avec Google Authenticator
- ✅ Gestion de sessions avec JWT
- ✅ Récupération de mot de passe

### Portails par acteur

#### 👤 Client (Touriste)
- Recherche multi-critères (destinations, dates, prix)
- Réservation de vols, hôtels, logements, voitures
- Paiement sécurisé
- Gestion des réservations
- Avis et notations
- Messagerie avec les prestataires

#### 👨‍💼 Manager
- Dashboard analytique
- Gestion des offres et promotions
- Validation des réservations
- Gestion des partenaires
- Statistiques et rapports

#### 👑 Admin
- Gestion complète des utilisateurs
- Configuration système
- Modération des contenus
- Gestion des rôles et permissions
- Logs et monitoring

#### 🏨 Hôtels
- Gestion des chambres et disponibilités
- Mise à jour des tarifs
- Gestion des réservations
- Communication avec les clients

#### 🏠 Propriétaires de logements
- Publication d'annonces
- Calendrier de disponibilité
- Gestion des réservations
- Gestion des avis

#### 🚗 Location de voitures
- Gestion de flotte
- Tarification dynamique
- Réservations
- Suivi des locations

#### ✈️ Agences de réservation aérienne
- Intégration API de vols
- Gestion des itinéraires
- Tarification
- Billetterie

## 🔒 Sécurité

Le projet implémente plusieurs couches de sécurité :

### Authentification et Autorisation
- **JWT (JSON Web Tokens)** : Tokens signés pour l'authentification API
- **OAuth 2.0** : Authentification via fournisseurs tiers
- **2FA (Two-Factor Authentication)** : Double authentification avec TOTP
- **RBAC (Role-Based Access Control)** : Contrôle d'accès basé sur les rôles

### Protection des données
- Hachage des mots de passe avec bcrypt
- Validation et sanitization des entrées
- Protection contre les injections NoSQL
- Headers de sécurité (Helmet.js)
- Rate limiting contre les attaques brute-force
- HTTPS en production

### Bonnes pratiques
- Variables d'environnement pour les secrets
- Sessions sécurisées
- Logs d'audit
- Validation des données côté client et serveur

## 🚀 Installation

### Prérequis
- Node.js (v18 ou supérieur)
- MongoDB (v6 ou supérieur)
- npm ou yarn
- Compte Google/Facebook pour OAuth (optionnel)

### Étapes d'installation

1. **Cloner le repository**
```bash
git clone https://github.com/votre-username/tourisme-agency-platform.git
cd tourisme-agency-platform
