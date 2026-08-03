# Analiza incydentu bezpieczeństwa – LastPass Security Incident (2022–2023)

## 1. Nazwa incydentu

**LastPass Security Incident (2022–2023)**

---

## 2. Organizacja i rok

| Organizacja | Rok |
|-------------|-----|
| LastPass | 2022 (atak), 2023 (raport) |

---

## 3. Profil atakującego

**Cyberprzestępcy**

Atak został przeprowadzony przez nieznaną grupę cyberprzestępczą. LastPass nie przypisał incydentu żadnej grupie APT.

---

## 4. Wektor wejścia

Atakujący:

- uzyskał dostęp do środowiska deweloperskiego po przejęciu komputera jednego z programistów,
- wykorzystał skradzione informacje do przeprowadzenia kolejnego ataku na pracownika DevOps,
- uzyskał dostęp do magazynu danych w chmurze oraz kopii zapasowych klientów.

---

## 5. Cel działania

Główne cele atakujących:

- kradzież danych klientów,
- uzyskanie zaszyfrowanych sejfów haseł (*password vaults*),
- pozyskanie danych umożliwiających późniejsze łamanie haseł metodą offline.

---

## 6. Naruszone elementy CIA

| Element | Uzasadnienie |
|---------|--------------|
| **Poufność (Confidentiality)** | Wyciek danych klientów oraz zaszyfrowanych vaultów. |
| **Integralność (Integrity)** | Brak informacji o modyfikacji danych. |
| **Dostępność (Availability)** | Brak informacji o niedostępności usługi. |

---

# 7. Cyber Kill Chain

| Etap | Co wydarzyło się w incydencie? |
|------|--------------------------------|
| **Reconnaissance** | Brak danych. |
| **Weaponization** | Przygotowanie ataku z wykorzystaniem wcześniej skradzionych informacji. |
| **Delivery** | Kompromitacja urządzenia pracownika poprzez ukierunkowany atak. |
| **Exploitation** | Uzyskanie dostępu do środowiska LastPass przy użyciu przejętych danych. |
| **Installation** | Brak danych. |
| **Command & Control** | Brak danych. |
| **Actions on Objectives** | Kradzież kodu źródłowego, danych klientów oraz zaszyfrowanych kopii sejfów. |

---

## 8. Co poszło nie tak po stronie obrońców?

- Kompromitacja urządzenia pracownika.
- Zbyt szerokie uprawnienia umożliwiające dostęp do wrażliwych zasobów.
- Możliwość uzyskania dostępu do kopii zapasowych klientów.
- Niewystarczająca segmentacja środowisk.
- Opóźnione wykrycie pełnej skali incydentu.

---

## 9. Gdzie można było przerwać incydent?

Możliwe punkty zatrzymania ataku:

- zabezpieczenie stacji roboczej pracownika,
- wykrycie nietypowych logowań,
- zastosowanie zasady **Least Privilege**,
- lepsza segmentacja infrastruktury,
- dodatkowa ochrona dostępu do kopii zapasowych.

---

## 10. Trzy rekomendacje bezpieczeństwa

1. **Wdrożenie zasady Least Privilege** oraz ograniczenie dostępu do krytycznych zasobów.

2. **Silniejsze uwierzytelnianie pracowników**, w tym MFA odporne na phishing oraz zabezpieczenie urządzeń administratorów.

3. **Lepsza ochrona danych klientów**, np. zwiększenie liczby iteracji PBKDF2 oraz dodatkowe zabezpieczenie metadanych.

---

# MITRE ATT&CK (przykładowe mapowanie)

| Taktyka | Technika |
|----------|----------|
| Initial Access | T1078 – Valid Accounts |
| Credential Access | T1555 – Credentials from Password Stores |
| Collection | T1213 – Data from Information Repositories |
| Exfiltration | T1041 – Exfiltration of Data |

---

## Źródło

- LastPass. *Security Incident Update and Recommended Actions*. 2023.
  https://blog.lastpass.com/posts/security-incident-update-recommended-actions

- MITRE ATT&CK Framework
  https://attack.mitre.org/
