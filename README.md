# Open Quran — Data Provenance & Public Privacy Registry

[![Platform](https://img.shields.io/badge/Platform-iOS%2016.0%2B-blue.svg)](https://developer.apple.com/ios/)
[![Database](https://img.shields.io/badge/Database-SQLite%20%7C%20GRDB-informational.svg)](https://github.com/groue/GRDB.swift)
[![Privacy: Zero Tracking](https://img.shields.io/badge/Privacy-100%25%20Offline%20%7C%20No%20Tracking-green.svg)](#privacy-policy)
[![No Ads](https://img.shields.io/badge/Ads-100%25%20Ad--Free-brightgreen.svg)](#about-open-quran)
[![License: Open Database](https://img.shields.io/badge/License-ODbL%20%2F%20MIT-yellow.svg)](#intellectual-property--licensing)

**Open Quran** is an independent, lightweight, offline-first, and completely ad-free Quran reading application designed natively for iOS. Built with a strict privacy-by-design architecture, Open Quran operates without tracking, telemetry, accounts, or analytics.

This public repository serves as the official **Data Provenance Registry, Raw Database Archive, and Public Privacy Documentation** for the Open Quran iOS application published on the Apple App Store.

---

## Table of Contents
1. [About Open Quran](#about-open-quran)
2. [Key Features](#key-features)
3. [Technical Architecture](#technical-architecture)
4. [Data Sources & Provenance (Apple Guideline 5.2)](#data-sources--provenance)
5. [Privacy Policy (Apple Guideline 5.1.1)](#privacy-policy)
6. [Intellectual Property & Licensing](#intellectual-property--licensing)
7. [Developer Contact & Support](#developer-contact--support)

---

## About Open Quran

Open Quran was created to provide Muslims and readers worldwide with a serene, dignified, and distraction-free recitation experience. 

Unlike many commercial applications that display disruptive advertisements or collect device identifiers, **Open Quran is 100% free, ad-free, and private**. All user data (bookmarks, favorites, and reading logs) is isolated strictly on the local device using SQLite.

---

## Key Features

- **Three Purpose-Built Reading Modes**:
  - **Arabic & Translation**: Verse-by-verse presentation with clear translation typography and colored tajweed highlights.
  - **Arabic Only (Mushaf View)**: Continuous Uthmani text flow organized page-by-page, reflecting the standard 604-page Madinah Mushaf layout.
  - **Translation Only**: Focused textual study format with clean verse indicators.
- **Rule-Based Tajweed Highlighting**: High-precision character index matching for standard recitation rules (Ghunnah, Idgham, Ikhfa, Qalqalah, Iqlab, and Izhar).
- **Authentic Typography**: Uses the specialized `me_quran` Uthmani script font with proportional Quranic end-of-ayah markers (`\u{FD3F}...\u{FD3E}`).
- **Apple On-Demand Resources (ODR)**: Core app binary remains compact (~25 MB). Multi-language translation packs are retrieved on-demand directly through Apple's App Store Content Delivery Network.
- **Unified Bookmarks & Favorites**: Fast verse bookmarking and double-tap favorite gestures across all reading modes.
- **Thematic Exploration**: Quick access to verses categorized by life themes (Patience, Gratitude, Trials, Family, Worship, etc.).
- **Bespoke Color Palettes**:
  - *Mushaf Green*: Traditional cream background with deep olive accents.
  - *Sky Blue*: High-contrast, clean modern aesthetic.
  - *Dark Gold*: OLED true-black with warm gold accents for night reading.

---

## Technical Architecture

The iOS client utilizes modern native technologies:
- **UI Framework**: SwiftUI with declarative state management.
- **Local Persistence**: [GRDB.swift](https://github.com/groue/GRDB.swift) managing high-performance SQLite storage (`quran_core.sqlite` and sandbox `user_data_v3.sqlite`).
- **Resource Distribution**: Native `NSBundleResourceRequest` for downloading verified translation databases via Apple ODR.
- **Voluntary Support**: StoreKit 2 (`Product.purchase()`) powering a voluntary tip jar.
- **Data Safety**: Concurrency-checked Swift 6 architecture with `@MainActor` thread safety.

---

## Data Sources & Provenance

In compliance with **Apple App Store Review Guideline 5.2 (Intellectual Property)**, all textual data included in the database files hosted in this repository has been verified against authoritative public scholarly sources:

1. **Arabic Quran Text**:
   - **Source**: Verified Uthmani text sourced directly from the **[Tanzil Project](https://tanzil.net/)** (v1.0.2).
   - **Recitation & Orthography**: Standard *Hafs 'an 'Asim* recitation text adhering to the widely accepted Medina Mushaf orthographic standards.
   - **Integrity**: Full diacritical marks (*tashkeel*), pause marks, and sajda indicators.
2. **Typography**:
   - `me_quran.ttf` (Me Quran Calligraphic Font), designed specifically for accurate digital Uthmani ligature rendering.
3. **Translations**:
   - Scholarly translations sourced through verified public domain and permissive open-access Islamic repositories, including *Sahih International* and certified regional ministries of religious affairs.
4. **Tajweed Indexing**:
   - Pre-computed character boundary offsets (`start_index`, `end_index`) mapped directly to the pristine Arabic text string.

---

## Privacy Policy

**Effective Date:** October 2026  
**Last Updated:** October 2026  

This section constitutes the **Official Public Privacy Policy** for Open Quran in strict compliance with **Apple App Store Review Guideline 5.1.1 (Data Collection and Storage)**.

### 1. Zero Personal Data Collection
Open Quran does **NOT** collect, track, transmit, harvest, or sell any personal information.
- No user accounts, logins, email addresses, phone numbers, or profile creations are required.
- No diagnostic analytics SDKs, advertising frameworks, or third-party behavioral trackers are embedded in the app.

### 2. 100% Local Device Storage
All user-generated activity—such as bookmarks, favorite verses, last read positions, active reading styles, font sizes, and color themes—is stored exclusively on your physical iOS device inside an isolated local SQLite file (`user_data_v3.sqlite`).
- This data never leaves your device.
- The developer maintains no external servers, user databases, or cloud sync backends.

### 3. Voluntary In-App Donations (Apple StoreKit 2)
Optional donations made via the in-app tip jar are handled entirely and securely by Apple through StoreKit 2 APIs.
- The developer never receives, processes, or stores your credit card numbers, bank details, or billing addresses.
- All financial transactions are governed under Apple’s standard App Store Terms and Privacy Policy.

### 4. Language Pack Downloads (Apple On-Demand Resources)
When downloading additional language packs, the request is executed via iOS native `NSBundleResourceRequest` directly from Apple’s App Store CDN servers. No third-party network connections are initiated.

### 5. Children's Online Privacy Protection
Open Quran does not collect any personal information from any user, including children under 13 years of age, complying fully with COPPA and global privacy regulations.

### 6. Privacy Contact
For inquiries regarding this privacy policy or data provenance verification:
- **Email**: [rapid.apps.developer@icloud.com](mailto:rapid.apps.developer@icloud.com)
- **Public Registry**: [https://github.com/rapidappsdeveloper/open-quran](https://github.com/rapidappsdeveloper/open-quran)

---

## Intellectual Property & Licensing

- **Quran Text & Database**: The raw Quranic text files provided in this repository are sourced from Tanzil.net under its public usage terms (free for non-commercial and scholarly use with attribution).
- **Application & Documentation**: The curation scripts, database schema designs, and documentation in this repository are published for public transparency and verification.

---

## Developer Contact & Support

If you encounter issues, notice any typographical errors in translations, or wish to offer suggestions:
- **Developer**: Rapid Apps Developer
- **Support & Inquiries**: [rapid.apps.developer@icloud.com](mailto:rapid.apps.developer@icloud.com)
- **Issue Tracker & Data Repository**: [https://github.com/rapidappsdeveloper/open-quran](https://github.com/rapidappsdeveloper/open-quran)