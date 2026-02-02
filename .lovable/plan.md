

# Fintutto Hausmeister - Mobile-First App

## Übersicht
Eine professionelle Mobile-First App für Hausmeister und Facility Manager mit Aufgabenverwaltung, Gebäudemanagement, Kalender, Echtzeit-Chat und Zeiterfassung.

---

## 1. Design-System & Grundstruktur

**Farbschema implementieren:**
- Hauptfarbe: Emerald #059669
- Akzentfarbe: #10B981
- Heller/Dunkler Modus mit automatischer Erkennung
- Inter Font von Google Fonts

**Mobile-First Layout:**
- Bottom Navigation mit 5 Tabs
- Große Touch-Targets (min. 44px)
- Swipe-Gesten für Aufgaben
- Pull-to-Refresh für Listen

---

## 2. Authentifizierung

**Login-System:**
- Email/Passwort Anmeldung
- "Passwort vergessen" Funktion
- Geschützte Routen (nur eingeloggte User)
- Automatische Weiterleitung bei nicht-authentifiziert

---

## 3. Datenbank-Erweiterungen (Supabase Migrations)

**Neue Tabellen erstellen:**
- `companies` - Hausverwaltungen (Multi-Mandant)
- `user_company_assignments` - Zuordnung Hausmeister ↔ Verwaltung
- `tasks` - Aufgaben mit Priorität, Status, Zuweisung
- `task_photos` - Fotos zu Aufgaben (Melder + Dokumentation)
- `task_notes` - Notizen zu Aufgaben
- `time_entries` - Zeiterfassung mit Start/Stop
- `calendar_events` - Termine und Begehungen
- `conversations` - Chat-Konversationen
- `messages` - Chat-Nachrichten
- `user_roles` - Rollen (admin, moderator, user)

**RLS-Policies:**
- Hausmeister sehen nur ihre zugewiesenen Aufgaben
- Daten gefiltert nach Hausverwaltung
- Sichere Rollen-Prüfung mit Security Definer Funktion

---

## 4. Aufgaben-Modul

**Aufgabenliste:**
- Filter-Tabs: Alle | Offen | In Arbeit | Erledigt
- Aufgaben-Karten mit Titel, Objekt, Priorität-Badge
- Swipe: Links ablehnen, Rechts annehmen
- Floating Action Button für neue Aufgabe

**Aufgaben-Detail:**
- Status-Änderung per Dropdown
- Foto-Galerie vom Melder
- Notizen hinzufügen
- Eigene Fotos hochladen (Dokumentation)
- Zeiterfassung mit Start/Stop-Timer
- "Als erledigt markieren" Button

---

## 5. Objekte-Modul

**Gebäudeliste:**
- Karten mit Name, Adresse, Einheiten-Anzahl
- Badge mit offenen Aufgaben pro Gebäude

**Gebäude-Detail:**
- Komplette Gebäudeinformationen
- Liste aller Wohnungen mit Status
- Kontakt zur Hausverwaltung
- "Rundgang starten" Button

---

## 6. Kalender-Modul

**Funktionen:**
- Monatsansicht mit farbigen Termin-Punkten
- Tagesansicht bei Auswahl
- Termin erstellen: Titel, Datum, Uhrzeit, Objekt
- Termin-Typen: Wartung, Begehung, Sonstiges

---

## 7. Nachrichten-Modul (Echtzeit-Chat)

**Features:**
- Konversationsliste mit Avataren
- Ungelesene-Nachrichten Badge
- Chat-Bubbles Interface
- Echtzeit-Updates via Supabase Realtime

---

## 8. Profil-Modul

**Inhalte:**
- Avatar und persönliche Daten
- Arbeitszeitübersicht (Woche)
- Statistik: Erledigte Aufgaben (Monat)
- Einstellungen (Dark Mode, Benachrichtigungen)
- Abmelden-Button

---

## Technische Umsetzung

- **Frontend:** React + TypeScript + Tailwind CSS
- **UI-Komponenten:** Shadcn/ui
- **Backend:** Externes Supabase (manuell verbinden)
- **State:** TanStack Query für Server-State
- **Routing:** React Router mit geschützten Routen
- **Sprache:** Komplett Deutsch

