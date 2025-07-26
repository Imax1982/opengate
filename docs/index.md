# OpenGate - Documentazione

App mobile per il controllo di cancelli e dispositivi domotici tramite Home Assistant con interfaccia moderna e intuitiva.

## Indice

- [Panoramica](#panoramica)
- [Caratteristiche](#caratteristiche)
- [Requisiti](#requisiti)
- [Installazione](#installazione)
- [Configurazione](#configurazione)
- [Utilizzo](#utilizzo)
- [Integrazione Siri (iOS)](#integrazione-siri-ios)
- [Risoluzione Problemi](#risoluzione-problemi)
- [Sviluppo](#sviluppo)

## Panoramica

OpenGate è un'applicazione React Native/Expo progettata per fornire un controllo semplice e veloce dei tuoi dispositivi Home Assistant, con focus particolare sui cancelli automatici. L'app offre un'interfaccia moderna con animazioni fluide e feedback visivo.

### Funzionalità Principali

- **Controllo Cancello Principale**: Pulsante centrale per apertura rapida
- **Dispositivi Secondari**: Due pulsanti laterali configurabili
- **Interfaccia Moderna**: Design Material con animazioni e feedback tattile
- **Sicurezza**: Archiviazione locale sicura delle credenziali
- **Integrazione iOS**: Supporto Siri e Scorciatoie Apple

## Caratteristiche

### Design e UX
- ✨ **Interfaccia Moderna**: Material Design con gradiente dinamico
- 🎭 **Animazioni Fluide**: Transizioni e feedback visivo professionale
- 📱 **Responsive**: Ottimizzata per iPhone e Android
- 🌙 **Tema Automatico**: Supporto per modalità chiara/scura del sistema
- 🔗 **Feedback Tattile**: Vibrazioni per conferma azioni (iOS)

### Funzionalità Tecniche
- 🔐 **Sicurezza**: Token di accesso sicuri con AsyncStorage
- 🌐 **Connettività Intelligente**: Gestione automatica della connessione
- ⚡ **Performance**: Ottimizzato per velocità e fluidità
- 🛠️ **Configurabile**: Personalizzazione completa di nomi e entity
- 📱 **Integrazione iOS**: Siri Shortcuts e app Comandi

### Compatibilità
- **Piattaforme**: iOS 15.1+, Android
- **Home Assistant**: Tutte le versioni con API REST
- **Dispositivi**: Switch, Light, Script, Automation
- **Rete**: HTTP/HTTPS, connessioni locali e remote

## Requisiti

### Sistema
- **iOS**: 15.1 o superiore
- **Android**: API level 21+ (Android 5.0)
- **Rete**: Connessione WiFi o dati mobili
- **Home Assistant**: Server attivo e raggiungibile

### Home Assistant
- Token di accesso a lunga durata
- Dispositivi configurati come switch/light/script
- API REST abilitata (default)
- Connessione di rete dal dispositivo mobile

## Installazione

### Download
1. **App Store (iOS)**: [Link App Store quando disponibile]
2. **Google Play (Android)**: [Link Play Store quando disponibile]
3. **APK Diretta**: Scarica dall'area release di GitHub

### Primo Avvio
1. Apri OpenGate
2. Inserisci i dati di configurazione
3. Testa la connessione
4. Personalizza i nomi dei dispositivi

## Configurazione

### Dati Richiesti

#### URL Home Assistant
```
Formato: https://tuodominio.com:8123
Esempi:
- https://homeassistant.local:8123
- https://192.168.1.100:8123
- https://tuodominio.duckdns.org:8123
```

#### Token di Accesso
1. Accedi a Home Assistant
2. Vai su **Profilo** (icona utente in basso a sinistra)
3. Scorri fino a **Token di accesso a lunga durata**
4. Clicca **Crea Token**
5. Inserisci un nome (es. "OpenGate App")
6. Copia il token generato

#### Entity ID
```
Formato: domain.entity_name
Esempi:
- switch.cancello_principale
- light.luce_ingresso
- script.apri_cancello
- automation.sicurezza_notturna
```

### Configurazione Avanzata

#### Pulsanti Laterali
- **Sinistra**: Dispositivo secondario (es. luci)
- **Destra**: Terzo dispositivo (es. porta)
- Entrambi opzionali e completamente personalizzabili

#### Personalizzazione
- **Titolo App**: Cambia il nome mostrato in alto
- **Nomi Pulsanti**: Personalizza le etichette
- **Entity ID**: Collega diversi dispositivi

## Utilizzo

### Schermata Principale

#### Pulsante Centrale
- **Tocco**: Attiva il cancello principale
- **Feedback**: Animazione e vibrazione
- **Stato**: Indicatore visivo di attivazione
- **Timeout**: Auto-reset dopo 1 secondo

#### Pulsanti Laterali
- **Sinistra/Destra**: Controllo dispositivi secondari
- **Personalizzabili**: Nome e funzione configurabili
- **Stessi Feedback**: Animazioni e vibrazioni

#### Indicatori di Stato
- 🟢 **Verde**: Dispositivo attivato con successo
- 🔵 **Blu**: Stato normale/in attesa
- 🔴 **Rosso**: Errore di connessione
- ⏳ **Animazione**: Comando in esecuzione

### Messaggi di Sistema
- **Snackbar**: Notifiche in-app per stati e errori
- **Colori**: Verde (successo), Rosso (errore), Giallo (warning)
- **Posizione**: Parte bassa dello schermo

## Integrazione Siri (iOS)

### Attivazione
1. Tocca l'icona impostazioni (⚙️)
2. Seleziona **"Aggiungi a Siri"**
3. Si apre l'app Comandi di Apple
4. Configura secondo le istruzioni

### Configurazione Manuale
1. App **Comandi** → **+** (Nuovo)
2. **Aggiungi Azione** → **App** → **OpenGate**
3. Seleziona l'azione desiderata
4. Imposta frase di attivazione
5. Salva il comando

### Esempi di Frasi
- "Apri il cancello"
- "Accendi le luci dell'ingresso"
- "Attiva la sicurezza"
- "Porta principale"

### Guida Apple
Per supporto dettagliato: **Impostazioni** → **"Guida Comandi"**

## Risoluzione Problemi

### Errori di Connessione

#### "Impossibile connettersi"
**Cause:**
- URL Home Assistant errato
- Server non raggiungibile
- Problemi di rete

**Soluzioni:**
1. Verifica URL (includi `http://` o `https://`)
2. Testa da browser mobile
3. Controlla firewall/port forwarding
4. Verifica connessione WiFi/dati

#### "Token non valido"
**Cause:**
- Token scaduto o revocato
- Token copiato male
- Caratteri speciali non supportati

**Soluzioni:**
1. Genera nuovo token su Home Assistant
2. Copia/incolla senza spazi extra
3. Verifica che il token non sia scaduto

#### "Entity ID non trovato"
**Cause:**
- Entity ID errato
- Dispositivo non esistente
- Permessi insufficienti

**Soluzioni:**
1. Verifica entity ID su Home Assistant (**Strumenti sviluppatore** → **Stati**)
2. Controlla ortografia (case-sensitive)
3. Assicurati che l'entity sia attivo

### Problemi di Performance

#### App Lenta
1. Riavvia l'app
2. Verifica memoria disponibile
3. Aggiorna iOS/Android
4. Reinstalla l'app se necessario

#### Animazioni Stuttering
1. Chiudi app in background
2. Riavvia dispositivo
3. Verifica spazio disponibile

### Problemi iOS Specifici

#### Siri Non Funziona
1. Verifica che Siri sia abilitato
2. Controlla permessi app
3. Ricrea il comando nell'app Comandi
4. Testa la frase di attivazione

#### Notifiche Mancanti
1. Controlla impostazioni notifiche iOS
2. Verifica **Non Disturbare**
3. Abilita notifiche per OpenGate

## Sviluppo

### Stack Tecnologico
- **Framework**: React Native con Expo
- **UI Library**: React Native Paper
- **Storage**: AsyncStorage
- **Networking**: Fetch API
- **Icons**: Ionicons
- **Animations**: React Native Animated

### Struttura Progetto
```
src/
├── App.js                 # Componente principale
├── components/            # Componenti riutilizzabili
├── utils/                # Utility e helpers
├── assets/               # Immagini e risorse
└── styles/               # Stili globali
```

### Setup Sviluppo
```bash
# Clone repository
git clone https://github.com/tuousername/opengate.git
cd opengate

# Installa dipendenze
npm install

# Avvia in sviluppo
expo start
```

### Build Produzione
```bash
# iOS
expo build:ios

# Android
expo build:android
```

### Contribuire
1. Fork del repository
2. Crea branch feature (`git checkout -b feature/nuova-funzionalita`)
3. Commit modifiche (`git commit -am 'Aggiunge nuova funzionalità'`)
4. Push al branch (`git push origin feature/nuova-funzionalita`)
5. Crea Pull Request

### Struttura Codice

#### App.js - Componente Principale
- Gestione stato applicazione
- Logica di connessione Home Assistant
- Rendering interfaccia utente
- Gestione animazioni

#### Configurazioni
- AsyncStorage per persistenza dati
- Validazione input utente
- Gestione errori e feedback

#### Stili
- Material Design
- Responsive layout
- Gradiente dinamico
- Animazioni fluide

---

## Supporto

### Canali di Supporto
- **GitHub Issues**: [Repository Issues](https://github.com/tuousername/opengate/issues)
- **Documentazione**: Questa pagina
- **Home Assistant Community**: [Forum HA](https://community.home-assistant.io)

### Segnalazione Bug
1. Descrivi il problema dettagliatamente
2. Includi versione app e OS
3. Aggiungi screenshot se utili
4. Specifica configurazione Home Assistant

### Richieste Feature
- Usa GitHub Issues con label "enhancement"
- Descrivi il caso d'uso
- Fornisci mockup se possibile

---

*Documentazione aggiornata per OpenGate v1.2 - Luglio 2025*
