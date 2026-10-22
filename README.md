# Daribati — Moroccan DGI Mobile Application

> ⚠️ **Enterprise project — source code is proprietary and not published here.**
> This repository exists as a portfolio placeholder to document my role and contributions on the Daribati project at **Concepment**.

![Status](https://img.shields.io/badge/status-production-success)
![Type](https://img.shields.io/badge/code-proprietary-lightgrey)
![Platform](https://img.shields.io/badge/platform-Android%20%7C%20iOS-blue)
![Stack](https://img.shields.io/badge/stack-React%20Native%20%2B%20Expo-61dafb)

---

## About the project

**Daribati** is the official mobile application of **Morocco's Direction Générale des Impôts (DGI)** — the Moroccan tax authority. It gives contributors mobile access to their tax obligations, declarations, attestations, payments and other administrative services.

Developed and maintained at **[Concepment](https://www.concepment.com)**, published on Google Play and in the App Store.

---

## My role

**Senior Mobile Engineer / Team Lead** — React Native rebuild, legacy maintenance, architecture decisions.

I lead the full rebuild of Daribati from its legacy Ionic 7 / Capacitor 8 / Angular stack to a modern **React Native + Expo (TypeScript)** stack, while maintaining the legacy application in production in parallel.

---

## Tech stack

### New application (in active development)
- **React Native + Expo (SDK 56)**
- **TypeScript** (strict mode)
- **Expo Router** (typed routes)
- **react-i18next** — French / Arabic internationalization
- **expo-secure-store** — encrypted session storage
- **expo-web-browser + expo-linking** — payment gateway handoff
- **Jest + Testing Library** — ~120 automated unit and screen tests
- **Docker** — reproducible Android build pipeline (JDK 21, Android SDK 34, Gradle 8.5)

### Legacy application (production, maintained)
- **Ionic 7 / Capacitor 8**
- **Angular / TypeScript**
- Google Play production releases

---

## What I built

- **Authentication chain** — login, OTP, auto-login, logout, session expiration handling, secure token storage.
- **Dashboard** — balance card, statistics, services grid, recent activity, pull-to-refresh, animated scroll header, loading / empty / error states.
- **Payments flow** — obligations list, multi-select with running total, DGI payment gateway handoff (CB card payment).
- **Service layer architecture** — typed API client with defensive mappers, unified `ApiError` handling, mock-first strategy to decouple frontend progress from backend availability.
- **Design system** — reusable UI primitives (`BalanceCard`, `StatCard`, `ActivityRow`, `EmptyState`, etc.) with theme tokens, no inline colors.
- **Bilingual UI** — French / Arabic with mirrored translation twins.
- **Security campaign** on the legacy app — 11 tickets covering session management, cert pinning via `network_security_config.xml`, Google Play compliance, dependency hardening.

---

## Architecture highlights

- **Layered separation**: `services/api/` (DGI integration) → `features/` (business hooks) → `components/ui/` (presentational) → `app/` (screens).
- **Defensive mappers** — every DGI wire response is normalized through a typed mapper that absorbs the API's variability (nullable fields, inconsistent shapes).
- **Mock-first development** — allowed frontend delivery to continue despite backend network constraints on the staging environment.
- **Dual-platform build** — Docker-based Android pipeline + iOS build via Expo.

---

## Collaboration

- **Azure DevOps** (`concepment-34` organization) — Git workflows (`develop → feature/* → PR`), code review on every merge, sprint-based Agile delivery.
- Collaboration with design (Template 1 design system), backend (DGI API integration), and product teams.

---

## Links

- 🏢 Company: **[Concepment](https://www.concepment.com)**
- 📱 Product: Daribati mobile app (Google Play — search *Daribati DGI*)
- 🏛️ Partner: **[Direction Générale des Impôts (DGI) — Morocco](https://www.tax.gov.ma)**

---

## Why no code here?

Daribati's source code is the property of Concepment and the DGI. This repository documents my professional contribution without disclosing proprietary code or confidential business logic.

For a technical discussion of the architecture decisions, patterns, or specific features — feel free to reach out.
