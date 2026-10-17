# Open Quran for iOS

[![Platform](https://img.shields.io/badge/Platform-iOS%2016.0%2B-blue.svg)](https://developer.apple.com/ios/)
[![Swift](https://img.shields.io/badge/Swift-5.9%20%7C%206.0-orange.svg)](https://swift.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Privacy: Zero Tracking](https://img.shields.io/badge/Privacy-100%25%20Offline%20%7C%20No%20Tracking-green.svg)](#privacy-policy)
[![No Ads](https://img.shields.io/badge/Ads-100%25%20Ad--Free-brightgreen.svg)](#about-open-quran)

**Open Quran** is an open-source, lightweight, and completely ad-free Quran reading application built natively for iOS using SwiftUI and SQLite (GRDB). The project is built with an offline-first philosophy, respecting user privacy above all else with zero tracking, zero telemetry, and zero advertisements.

This repository serves as the transparent public source code, data provenance registry, and public privacy documentation for the app published on the Apple App Store.

---

## Table of Contents
1. [About Open Quran](#about-open-quran)
2. [Key Features](#key-features)
3. [Architecture & Technical Highlights](#architecture--technical-highlights)
4. [Data Sources & Provenance (Apple Guideline 5.2)](#data-sources--provenance)
5. [Privacy Policy (Apple Guideline 5.1.1)](#privacy-policy)
6. [Intellectual Property & Licensing](#intellectual-property--licensing)
7. [Contact & Feedback](#contact--feedback)

---

## About Open Quran

Open Quran was designed to provide Muslims and readers worldwide with a peaceful, serene, and distraction-free recitation and reading experience. 

Unlike many modern mobile applications that monetize through disruptive advertisements or harvest behavioral data, **Open Quran is 100% free and private**. It relies entirely on local SQLite storage, on-device computing, and Apple's secure infrastructure for optional voluntary donations and language downloads.

---

## Key Features

- **Three Dedicated Reading Styles**:
  - **Arabic & Translation**: Verse-by-verse view with verified translations and tajweed coloring.
  - **Arabic Only (Mushaf Page View)**: Continuous Uthmani text flowing seamlessly page-by-page, matching the printed Madinah Mushaf.
  - **Translation Only**: Clean, focused translation reading with localized verse indicators.
- **Dynamic Tajweed Recitation Rules**: Color-coded tajweed rules categorized according to standard *Hafs 'an 'Asim* recitation rules.
- **Adaptive Typography**: Built using the authentic `me_quran` Uthmani font with proportionally scaled verse end markers (`\u{FD3F}...\u{FD3E}`).
- **On-Demand Resources (ODR)**: Keep the app binary tiny (~25 MB) while downloading localized language translation packs on-demand directly from Apple’s App Store CDN servers.
- **Intelligent Page-Level Bookmarks & Favorites**: Save verse bookmarks and double-tap to favorite verses effortlessly across both single-verse and full-mushaf view modes.
- **Curated Thematic Verses**: Instant discovery of Quranic verses organized by life themes (e.g., Patience, Gratitude, Trials, Hope).
- **Curated Theme Palettes**: Optimized for eye comfort with three bespoke color modes:
  - *Mushaf Green*: Traditional cream background with deep olive accents.
  - *Sky Blue*: Modern, clean high-contrast reading.
  - *Dark Gold*: OLED true-black with warm gold accents for night reading.
- **Completely Offline**: Every surah, verse, tajweed rule, and bookmark lives in an isolated local database on your device.

---

## Architecture & Technical Highlights

- **Framework**: 100% native SwiftUI lifecycle supporting iOS 16, 17, and 18+.
- **Database Engine**: [GRDB.swift](https://github.com/groue/GRDB.swift) managing high-performance, thread-safe SQLite databases (`quran_core.sqlite` and `user_data_v3.sqlite`).
- **Asset Distribution**: Apple On-Demand Resources (ODR) with `NSBundleResourceRequest` for zero third-party dependency network access.
- **In-App Purchases**: StoreKit 2 for voluntary tip jar donations (`Product.purchase()`).
- **Code Standards**: Strict enforcement of [SwiftLint](https://github.com/realm/SwiftLint) rules and Swift 6 concurrency safety (`@MainActor` data isolation).

---

## Data Sources & Provenance

In compliance with **Apple App Store Review Guideline 5.2 (Intellectual Property)**, all textual assets and databases included in this project are strictly verified against authoritative scholarly repositories:

1. **Arabic Quran Text**:
   - Source: Verified Uthmani text provided by the **[Tanzil Project](https://tanzil.net/)** and verified against the standards of the King Fahd Glorious Quran Printing Complex (KFGQPC).
   - Script: Standard Hafs 'an 'Asim recitation script with complete diacritics (*tashkeel*).
2. **Typography**:
   - Authentic Uthmani calligraphic font (`me_quran.ttf`), developed specifically for digital Quran rendering and correctly mapped to Unicode Quranic markers.
3. **Translations**:
   - Public scholarly translations sourced through verified digital archives, including the widely acclaimed *Sahih International* English translation, Indonesian Ministry of Religious Affairs (Kemenag), and other certified public translation catalogs.
4. **Tajweed Rules**:
   - Categorized rules (Ghunnah, Idgham, Ikhfa, Qalqalah, Iqlab, and Izhar) mapped to exact character unicode indices in `quran_core.sqlite`.

---

## Privacy Policy

**Effective Date:** October 2026  
**Last Updated:** October 2026  

This section serves as the **Official Public Privacy Policy** for Open Quran in full compliance with **Apple App Store Review Guideline 5.1.1 (Data Collection and Storage)**.

### 1. Zero Data Collection
Open Quran does **NOT** collect, transmit, track, monitor, sell, or store any personal information whatsoever. 
- No user accounts or registrations are required.
- No names, email addresses, phone numbers, or IP addresses are logged.
- No tracking technologies, telemetry, analytics SDKs, or third-party diagnostic libraries are integrated into the application.

### 2. 100% Local Device Storage
All user interactions—including bookmarks, favorite verses, last read positions, reading mode selections, font preferences, and theme choices—are stored exclusively on your physical iOS device inside an isolated, local SQLite sandbox (`user_data_v3.sqlite`).
- This data never leaves your device.
- No external cloud servers or databases are maintained by Open Quran.

### 3. Voluntary Tips & Donations (Apple StoreKit 2)
Voluntary tip jar payments are processed directly and securely by Apple Inc. through StoreKit 2 APIs. 
- Open Quran never receives, accesses, or stores your credit card details, banking information, or billing address.
- All transactions are governed entirely under Apple’s standard privacy terms and customer agreements.

### 4. Language Pack Downloads (Apple On-Demand Resources)
When you select an additional translation language, the language pack is downloaded securely from Apple's App Store Content Delivery Network (CDN) using native iOS On-Demand Resources (`NSBundleResourceRequest`).
- Open Quran does not operate third-party download servers.
- Downloads are routed securely through Apple's infrastructure without exposing user identities.

### 5. Children's Privacy
Open Quran does not collect data from any person, including children under the age of 13, in strict adherence to COPPA (Children’s Online Privacy Protection Act) and GDPR-K.

### 6. Privacy Inquiries
If you have any questions or require clarification regarding our privacy practices, please contact the developer directly at:
- **Email**: [rapid.apps.developer@icloud.com](mailto:rapid.apps.developer@icloud.com)
- **Repository**: [https://github.com/rapidappsdeveloper/open-quran](https://github.com/rapidappsdeveloper/open-quran)

---

## Intellectual Property & Licensing

### Software License
The source code of Open Quran is released under the **MIT License**.

```text
MIT License

Copyright (c) 2026 Open Quran Contributors & Rapid Apps Developer

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.