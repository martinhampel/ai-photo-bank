# Požiadavky na projekt: Fotobanka s AI detekciou objektov (Oracle OCI + Vue.js)

## Újel projektu
- Vytvoriť fotobanku, kde bude možné:
  - Nahrávať fotky vo vysokej kvalite.
  - Automaticky analyzovať obsah fotiek (napr. skautské šatky, voda, úsmev).
  - Pridávať štítky (labels) k fotkám automaticky alebo manuálne.
  - Vyhľadávať fotky podľa zadaných štítkov.

---

## Požiadavky na technológie

### Frontend
- **Vue.js (s Vuetify)**:
  - Vytvorenie UI na nahrávanie fotiek, zobrazovanie galérie a vyhľadávanie fotiek.
  - Použitie axios na komunikáciu s backendom.

### Backend
- **Node.js (Express.js)** alebo **Python (Flask/FastAPI)**:
  - Endpointy na nahrávanie fotiek, získavanie zoznamu fotiek a vyhľadávanie.
  - Prepojenie s Oracle OCI Object Storage na uloženie fotiek.
  - Integrácia OCI Vision na analýzu fotiek.

### Ukladanie a analýza
- **Oracle OCI Object Storage**:
  - Ukladanie fotiek vo vysokej kvalite.
  - Vytvorenie bucketu pre dataset.
- **OCI Vision**:
  - Automatická analýza obsahu fotiek.
  - Tréning modelu na detekciu špecifických objektov (napr. skautské šatky).
- **Elasticsearch**:
  - Indexovanie metadát a štítkov na rýchle vyhľadávanie.

---

## Funkcie aplikácie

### 1. Nahrávanie fotiek
- Používateľ nahrá fotku cez frontend.
- Backend spracuje fotku a uloží ju do OCI Object Storage.

### 2. Automatické označenie fotiek
- Po nahratí backend odošle fotku do OCI Vision.
- OCI Vision vygeneruje zoznam štítkov (napr. "scarf", "water", "smile").
- Štítky sa uložia do databázy alebo Elasticsearch.

### 3. Vyhľadávanie fotiek
- Používateľ zadá štítky (napr. "water") a aplikácia zobrazí relevantné fotky.
- Backend vyhľadá fotky v Elasticsearch alebo databáze.

### 4. Tréning modelu na vlastné objekty
- Použitie OCI Vision Custom Models:
  - Nahrať dataset (fotky + anotácie).
  - Spustiť tréning modelu na detekciu špecifických objektov.
  - Nasadiť model ako endpoint na detekciu.

---

## Príklad architektúry

### Frontend
- **Vue.js (s Vuetify)**:
  - Komponent na nahrávanie fotiek.
  - Galéria na zobrazenie fotiek.
  - Filtrovanie a vyhľadávanie fotiek.

### Backend
- **Node.js** alebo **Python**:
  - API endpointy na nahrávanie, analýzu a vyhľadávanie fotiek.
  - Pripojenie k OCI Object Storage a OCI Vision.

### Ukladanie a analýza
- **OCI Object Storage**: Ukladanie fotiek.
- **OCI Vision**: Analýza a štítky.
- **Elasticsearch**: Indexovanie metadát a štítkov.

---

## Ďalšie kroky
1. Nastaviť Oracle OCI a bucket pre uloženie fotiek.
2. Vyvinúť frontend a backend pre aplikáciu.
3. Implementovať automatické označenie fotiek pomocou OCI Vision.
4. Otestovať a nasadiť aplikáciu.

---
