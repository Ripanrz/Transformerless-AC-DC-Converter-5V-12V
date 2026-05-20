# ⚡🔌 Transformerless AC–DC Power Supply (5V & 12V) using 155J/630V Polyester Capacitor

![Timeline](https://img.shields.io/badge/Timeline-May_--_Jun_2024-8A2BE2)
![Simulation](https://img.shields.io/badge/Simulation-Proteus-blue)
![PCB Design](https://img.shields.io/badge/PCB_Design-Autodesk_Eagle-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

Proyek ini berfokus pada perancangan, simulasi, dan realisasi perangkat keras **Catu Daya Tanpa Transformator (Transformerless Power Supply) AC-DC**. Sistem ini mampu menurunkan tegangan jala-jala AC menjadi output DC ganda sebesar **5V** dan **12V** menggunakan metode *Capacitive Voltage Divider* dengan komponen utama kapasitor poliester 155J/630V. Proyek ini mencakup tiga tahap utama: simulasi, perancangan PCB, dan fabrikasi fisik.

> **Timeline:** May - June 2024

---

## 📸 Project Preview
<!-- Ganti link di bawah dengan foto alat fisik atau hasil layout PCB -->
![Foto Alat Fisik](https://via.placeholder.com/800x400?text=Foto+Alat+Fisik+Catu+Daya)


---

## ✨ Fitur Utama & Tahapan Pengembangan

1. **Simulasi & Verifikasi (Proteus)** 💻
   Melakukan simulasi awal rangkaian menggunakan **Proteus** untuk memverifikasi stabilitas tegangan output, menganalisis kinerja tegangan riak (*ripple voltage*), dan memastikan keamanan sistem sebelum masuk ke tahap perakitan fisik.

2. **Pemilihan Komponen Tepat (Kalkulasi Matematis)** 🧮
   Menentukan nilai komponen kunci berdasarkan perhitungan kebutuhan arus beban, antara lain:
   * **Kapasitor Poliester (X-Rated):** 155J/630V sebagai pembatas arus utama.
   * **Penyearah:** Bridge Rectifier 2W10 (Penyearah gelombang penuh).
   * **Resistor Bleeder & Pembatas:** 1MΩ (Discharge) & 1kΩ.
   * **Filter Kapasitor:** Elektrolit 1000µF/16V untuk meminimalisir *ripple*.
   * **Regulator Tegangan:** IC 7805 (Output 5V) & IC 7812 (Output 12V).

3. **Desain PCB & Fabrikasi (Autodesk Eagle)** 🛠️
   Merancang tata letak jalur (*layout*) PCB menggunakan **Autodesk Eagle**, dilanjutkan dengan proses manufaktur mandiri (pengeboran/*drilling*), penyolderan komponen, serta pengujian pasca-perakitan untuk memvalidasi kesesuaian performa alat dengan data simulasi.

---

## 🛠️ Komponen Utama

### Hardware (Komponen Elektronika)
* Kapasitor Poliester 1.5µF (155J 630V)
* Diode Bridge 2W10
* IC Regulator LM7805 & LM7812
* Kapasitor Elco 1000µF / 16V
* Resistor 1MΩ & 1kΩ

### Software
* **Proteus:** Simulasi skematik & analisis gelombang.
* **Autodesk Eagle:** Desain skematik PCB dan *Layout Traces*.

---

## 🔄 Blok Diagram Sistem

Berikut adalah alur bagaimana tegangan tinggi AC diturunkan dan diregulasi tanpa menggunakan transformator besi:

```mermaid
graph LR
    A[Input AC 220V] --> B("Dropping Capacitor (155J/630V)")
    B --> C[Bridge Rectifier 2W10]
    C --> D[Filter Kapasitor 1000µF]
    D --> E[Regulator IC 7812]
    D --> F[Regulator IC 7805]
    E --> G([Output DC 12V])
    F --> H([Output DC 5V])

    style A fill:#ff4d4d,stroke:#fff,stroke-width:2px,color:#fff
    style G fill:#20beff,stroke:#fff,stroke-width:2px,color:#fff
    style H fill:#20beff,stroke:#fff,stroke-width:2px,color:#fff
