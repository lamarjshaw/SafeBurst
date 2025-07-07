# SafeBurst
A voice activated emergency escape mobile app

# SafeBurst – Instant Emergency Escape Phrase App

## 📱 What It Does
SafeBurst is a futuristic mobile safety app that allows users to trigger emergency actions using a secret voice command or phone gesture (like shaking the device). The app can:
- Trigger a fake phone call
- Send live GPS location to trusted contacts
- Mute all notifications
- Play a soothing sound for anxiety
- Activate other backup actions for safety

## 🎯 Real-World Problem It Solves
SafeBurst helps users exit dangerous, uncomfortable, or overwhelming situations quickly and discreetly. Use cases include:
- Escaping bad dates or awkward social situations
- Calming panic attacks or overstimulation
- Alerting friends when walking alone at night

## 🛠️ Key Features
- 🎙️ Custom trigger phrase (e.g., "Red Umbrella")
- 📞 Fake call from a chosen contact
- 📍 Sends live GPS to trusted friends
- 🔇 Notification mute or soothing sound
- 🔁 Shake-to-activate backup trigger
- 🧠 Future AI expansion for detecting stress tone

## 💻 Platform and Tools
- **Platform:** Android
- **Builder:** MIT App Inventor
- **Tools Used:**
  - `SpeechRecognizer` – to detect the voice trigger
  - `Notifier`, `PhoneCall`, `Texting` – to perform emergency actions
  - `AccelerometerSensor` – to detect phone shaking
  - `TinyDB` – to store trigger phrases and contacts locally

## 🔧 How It Works – Step-by-Step
1. User sets a secret escape phrase and selects a trusted contact.
2. When the phrase is spoken aloud or the phone is shaken:
   - A fake call is triggered
   - Live location is sent via SMS
   - The app mutes alerts or plays a calming audio
3. Data is saved in TinyDB for quick reuse.
4. Optionally, user enables “Safe Mode” for instant activation.

## 🖼️ App Design Overview
### Main Screen
- Input field for secret phrase
- Contact picker for emergency contact
- Toggle for fake call and GPS alert
- Activation status display

### Settings Screen
- Change or reset phrase
- Choose backup trigger (shake, button, etc.)
- Customize response behavior (call, message, mute, etc.)

## 🧠 Future Ideas
- AI-based tone detection for panic/stress
- Siri/Google Assistant shortcut compatibility
- Emergency mode: flashlight + audio recorder + cloud upload
