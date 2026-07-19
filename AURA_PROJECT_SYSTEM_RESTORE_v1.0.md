# AURA_PROJECT_SYSTEM_RESTORE_v1.0

Status: Canonical Working Restore Date: 2026-07-11

# Cel

Dokument zachowuje kontekst wielogodzinnej analizy architektury projektu
Aura. Jest punktem startowym dla kolejnych sesji i ma zapobiec utracie
wiedzy.

# Analizowane repozytoria

-   aura-poc-a-core
-   aura-guard-v1.3
-   aura-sign-mvp

# Stan początkowy

Rozpoczęliśmy od analizy kodu i zależności pomiędzy repozytoriami. W
toku pracy przeszliśmy od analizy implementacji do analizy architektury,
a następnie do modelowania protokołu.

# Najważniejsze odkrycia

-   Aura jest lepiej opisywana jako protokół niż pojedyncza aplikacja.
-   Python i Rust pełnią rolę implementacji referencyjnych.
-   Konstytucja projektu jest traktowana jako nadrzędna specyfikacja.
-   Największą wartością projektu jest model zaufania oraz
    deterministyczny sposób jego realizacji.

# Model architektoniczny (To-Be)

Mathematical Core → Evidence Model → Decision Engine → Attestation
Engine → Cryptographic Core → Operational Core

Dodatkowe warstwy: - Assurance Core - Conformance Core

# Najważniejsze artefakty

-   ADR -- decyzje architektoniczne
-   ARR -- rejestr ryzyk
-   ADC -- poziom pewności decyzji
-   ACI -- inwentaryzacja kanonu
-   ADM -- macierz zależności decyzji
-   PI -- Protocol Invariants
-   G -- Trust Guarantees
-   CTM -- Conformance Test Matrix
-   CGR -- Conformance Gap Report

# Kluczowe niezmienniki

-   Zero Float Runtime
-   Determinizm
-   Mathematical Core mierzy, nie decyduje
-   Polityki są podpisywane
-   Każda implementacja ma być zgodna z protokołem

# Główne ryzyka

CG-001: evaluator.py zwraca decyzję biznesową. CG-002: globalny stan
HALTED_AGENTS. CG-003: krucha serializacja hash chain. CG-004: brak
wydzielonego Conformance Core.

# Strategia dalszych prac

1.  Zamrozić Aura Protocol Specification.
2.  Zamrozić Protocol Invariants.
3.  Zbudować Conformance Test Matrix.
4.  Zaprojektować Conformance Core.
5.  Wykonać Conformance Restoration.
6.  Certyfikować implementacje.

# Zasady współpracy

-   Najpierw specyfikacja, potem implementacja.
-   Każda zmiana musi mieć uzasadnienie.
-   Oddzielać stan obecny (As-Is) od architektury docelowej (To-Be).
-   Dokumentacja ma być wykonywalną specyfikacją, a nie tylko opisem.

# Długoterminowa dokumentacja

Plan zakłada stworzenie wielotomowej dokumentacji: - Volume I --
Genesis - Volume II -- Aura Protocol Specification - Volume III --
Engineering Analysis - Volume IV -- Certification - Volume V -- Future
Architecture - Architectural DNA - System Restore

# Następny krok

Rozpocząć projektowanie Conformance Core jako niezależnego komponentu, a
następnie przywracać zgodność implementacji z protokołem na podstawie
Conformance Gap Report.
