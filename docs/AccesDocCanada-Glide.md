# Accès Doc Canada+ with Glide

This document outlines a template for creating the **Accès Doc Canada+** application using Glide and Google Sheets. The goal is to implement the application flow described in the project notes while staying compatible with Glide's free tier.

## 1. Data Structure (Google Sheets)

Create a Google Sheet with the following tables:

- **Users** – stores email, pseudo, password (hashed), language preference, and consent status.
- **Requests** – tracks submitted assistance requests, status, dates, and attached documents.
- **Forms** – list of available government or organizational forms with links and descriptions.
- **Notifications** – optional table for managing reminders and push notifications via Zapier/Make.

These tables will be connected to your Glide app as data sources.

## 2. Screens

1. **Écran Accueil**
   - Display the logo and application name.
   - Button to choose language (French/English) and a button to start the app (links to the user choice screen).

2. **Écran Choix de l'Usager**
   - **Option A – Usager Anonyme**: allow voice input, free text, photo upload with OCR, and PDF upload. Data can be kept in memory or deleted at the user's request.
   - **Option B – Profil Sauvegardé**: sign in with Google or email. Prefill forms with user information stored in Google Sheets.
   - **Option C – Questionnaire Complet**: guided form with optional voice assistance. Sections include personal info, housing, family, employment, financial, health, and goals.

3. **Analyse Complète**
   - Use Glide data actions to filter and present eligible programs based on the questionnaire. Display links to official resources.

4. **Écran Résultats**
   - Search or filter by domain and level (federal/provincial/municipal/organization).
   - Show program name, amount, frequency, and direct link to the form.

5. **Écran Soumettre une Demande**
   - Dynamic fields based on the user's mode (anonymous or profile).
   - Allow file uploads (photos, notes, PDFs). If signed in, prefill user data.

6. **Écran Suivi de Demande**
   - Track status, approved amounts, missing documents, and next steps. Include options for email or push reminders through Zapier/Make.

7. **Écran Formulaires**
   - List available forms with direct links, last update date, and instructions.

8. **Paramètres / Notifications**
   - Filters according to user data (province, income range, preferred language). Enable or disable notifications.

9. **Écran Admin**
   - Restricted to `jimmycouturerenaud@gmail.com`. Manage submitted data, view statistics, or handle user requests.

## 3. Compliance Notes

- Inform users about data handling in accordance with **Loi 25** on personal data protection.
- Provide consent checkboxes and a way to request deletion of personal data.
- Store sensitive data in encrypted form if possible.

## 4. Publishing Checklist

1. Export the Glide app as a Progressive Web App (PWA) or wrap it to create an Android App Bundle (.AAB) for Google Play.
2. Prepare Google Play Console assets:
   - Title: **Accès Doc Canada+**
   - Description: *Application citoyenne pour l'accès aux aides financières, crédits, droits...*
   - Icon: 512x512 PNG
   - Screenshots: 1080x1920
   - Privacy Policy link
3. Ensure the app complies with all Google Play policies and local regulations.

This template should help you build a Glide-based prototype quickly using Google Sheets as the backend.
