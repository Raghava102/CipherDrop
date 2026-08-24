# CipherDrop

**Private • Offline • Encrypted**

CipherDrop is an Android privacy-focused application for encrypted note and file exchange. The project uses authenticated encryption, recipient identity verification, signed packages, protected viewing, and optional self-destruct workflows.

## Security architecture

- AES-256-GCM authenticated encryption
- X25519 key agreement
- HKDF-SHA256 key derivation
- Ed25519 digital signatures
- Android Keystore-backed local key protection
- Recipient identity and fingerprint validation
- Tamper detection and authenticated package metadata
- Protected Viewer with Android `FLAG_SECURE` where supported
- Optional self-destruct package lifecycle
- App-private temporary plaintext handling

## Package format

CipherDrop uses the `.cdrop` package format. Package parsing, authentication, signature verification, and decryption are handled by the existing security pipeline.

## Android stack

- Kotlin
- Jetpack Compose
- Material 3
- MVVM / StateFlow
- Room
- CameraX / ML Kit for QR pairing
- Android Keystore

## Project source

The complete Android Studio project was exported from Google AI Studio. A source archive can be kept alongside this repository when the complete project is uploaded through Git or GitHub's web uploader.

## Secrets and release signing

Do not commit API keys, `.env`, `local.properties`, keystores, signing certificates, or passwords. Release signing credentials must be supplied through the local/CI environment.

## Build

Open the project in Android Studio and allow Gradle to synchronize. Then run the normal Android build tasks for the configured toolchain.

## Security claims

CipherDrop is designed to reduce unauthorized access to decrypted content. Android secure-window protection cannot prevent another camera or a compromised/rooted device from capturing screen contents.

## Status

The repository is maintained as a private development repository while the project is being prepared for release and security review.
