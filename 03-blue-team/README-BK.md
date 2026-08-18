# 🛡️ Cybersecurity Projects — Portfolio (PL)

Portfolio projektów z obszaru **Security Operations (SOC)**, **Detection Engineering**,
**Incident Response** oraz **Governance, Risk & Compliance (GRC)**.

Każdy projekt opiera się na realnych narzędziach i międzynarodowych standardach
(**MITRE ATT&CK**, **ISO/IEC 27001**, **NIST**, **CVSS**). Celem jest udokumentowanie
praktycznych umiejętności analitycznych i technicznych, przydatnych na stanowiskach
Junior SOC Analyst / Security Analyst.

> 🇬🇧 English version: [README.en.md](README.en.md)

---

## 👤 O mnie

Inżynier z ~8-letnim doświadczeniem w utrzymaniu systemów przemysłowych (SCADA),
przechodzący do cyberbezpieczeństwa z ukierunkowaniem na Blue Team / SOC.
Silne kompetencje analityczne, praktyka w analizie logów, detekcji zagrożeń
i reagowaniu na incydenty.

- 📫 Kontakt: bartekkap7@gmail.com
- 🎓 W przygotowaniu: **CompTIA Security+ (SY0-701)**

---

## 📂 Projekty

| # | Projekt | Obszar | Standardy | Narzędzia |
|---|---------|--------|-----------|-----------|
| 1 | [Analiza phishingu](#1--analiza-phishingu) | Incident Response | MITRE ATT&CK, NIST 800-61 | Analiza nagłówków, Python |
| 2 | [Polityki bezpieczeństwa](#2--polityki-bezpieczeństwa) | GRC | ISO/IEC 27001:2022 | — |
| 3 | [Ocena podatności](#3--ocena-podatności) | Vulnerability Mgmt | CVSS, NIST 800-115 | OpenVAS, Nessus |
| 4 | Detekcja Brute Force *(w realizacji)* | Detection Engineering | MITRE ATT&CK T1110 | Sysmon, Event Logs |

---

### 1. 🎣 Analiza phishingu

Analiza wiadomości phishingowej na podstawie surowego artefaktu `.eml`.
Pełen raport incydentu zgodny z cyklem NIST SP 800-61.

**Zakres:**
- Analiza nagłówków (Received chain, SPF/DKIM/DMARC)
- Weryfikacja integralności załącznika (hash liczony, nie przepisywany)
- Wskaźniki kompromitacji (IOC) kopiowane znak w znak ze źródła
- Mapowanie do MITRE ATT&CK (T1566.001)
- Rozdzielenie faktów, przypuszczeń i braków danych

**Kluczowe wnioski:**
- SPF/DKIM/DMARC PASS potwierdza pochodzenie, nie intencję wiadomości
- Timeline oparty wyłącznie na zdarzeniach potwierdzonych nagłówkami

📄 [Raport (PDF)](01-phishing-analysis/Raport_Phishing.pdf)

---

### 2. 📋 Polityki bezpieczeństwa

Zestaw polityk bezpieczeństwa dla fikcyjnej organizacji sektora finansowego,
zmapowany do kontroli **ISO/IEC 27001:2022 (Annex A)**.

**Zakres:**
- Zarządzanie tożsamością (IAM) i kontrola dostępu (RBAC, least privilege)
- Szyfrowanie danych, logowanie i monitoring
- Reagowanie na incydenty, ochrona endpointów, świadomość bezpieczeństwa
- Każda zasada zmapowana do konkretnej kontroli Annex A

📄 [Dokument (PDF)](02-security-policies/Polityki_Bezpieczenstwa.pdf)

---

### 3. 🔍 Ocena podatności

Ocena podatności celowo podatnego systemu (Metasploitable 3) z użyciem
**dwóch niezależnych skanerów** i korelacją wyników.

**Zakres:**
- Skan dwoma narzędziami: OpenVAS + Nessus, korelacja wyników
- Analiza podatności RCE: ProFTPD (CVE-2015-3306), Drupalgeddon2 (CVE-2018-7600)
- Punktacja istotności wg CVSS, mapowanie CVE
- **Weryfikacja i odrzucenie false positive** względem kontekstu celu
- Środki zaradcze z kontrolami kompensacyjnymi + plan retestu

**Kluczowe wnioski:**
- Dwie podatności RCE (CVSS 10.0) potwierdzone przez oba skanery
- Rozbieżność skanerów → konieczność korelacji wielu źródeł
- Skaner dostarcza kandydatów do analizy, nie ostatecznego werdyktu

**Środowisko:** Kali Linux (skaner) + Metasploitable 3, izolowana sieć host-only.

📄 [Raport (PDF)](03-vulnerability-assessment/Raport_Ocena_Podatnosci.pdf)

---

## 🧰 Wykorzystane technologie

`OpenVAS` · `Nessus` · `Sysmon` · `Wireshark` · `Nmap` · `Splunk`
· `MITRE ATT&CK` · `ISO 27001` · `NIST` · `CVSS` · `Python`

---

## 📜 Prawa autorskie / Copyright

© 2026 **Bartłomiej Kapała**. Wszystkie prawa zastrzeżone.

Projekty w tym repozytorium stanowią część mojego portfolio zawodowego.
Możesz je **przeglądać i uczyć się z nich**. Zabronione jest kopiowanie,
redystrybucja oraz przedstawianie tych prac jako własnych.

Licencja: [CC BY-NC-ND 4.0](LICENSE) — Uznanie autorstwa · Użycie niekomercyjne · Bez utworów zależnych.
