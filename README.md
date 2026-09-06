# Cisco Packet Tracer - Wireless Router & DHCP Configuration Lab

Repository ini berisi proyek latihan dan simulasi jaringan menggunakan **Cisco Packet Tracer**. Proyek ini berfokus pada konfigurasi **Wireless Router (Access Point)**, pengamanan Wi-Fi (WPA2 Personal), pengalokasian **IP Address Dinamis (DHCP)**, dan verifikasi konektivitas antar-perangkat client (*wired* dan *wireless*).

---

## 📌 Topologi Jaringan

Topologi terdiri dari beberapa perangkat utama yang saling terhubung:
* **Switch0 (2960-24TT)**: Switch utama yang menghubungkan Server, Router, dan Wireless Router.
* **HomeRouter-PT-AC (Wireless Router)**: Berfungsi sebagai Access Point Wi-Fi sekaligus DHCP Server untuk jaringan lokal.
* **PC0 & Laptop0**: Perangkat client yang menerima IP Address secara otomatis (DHCP) dan berkomunikasi satu sama lain.
* **Router0 (2911) & Server-PT**: Perangkat jaringan pelengkap dalam simulasi.

---

## ⚙️ Spesifikasi Konfigurasi

| Parameter | Keterangan / Nilai Konfigurasi |
| :--- | :--- |
| **SSID (Nama Wi-Fi)** | `Derril Andiv Heri... + LSP2024` |
| **Security Mode** | WPA2 Personal |
| **Password Wi-Fi** | `SuksesKompet3n` |
| **Alokasi IP Client** | Dinamis (DHCP Enabled) |
| **Status Koneksi** | Fully Connected & Reachable |

---

## 🚀 Langkah Kerja & Konfigurasi

1. **Perkabelan & Interface Physical**:
   - Menghubungkan **Switch0** ke **HomeRouter-PT** (*Port 0/0 / WAN*) menggunakan kabel *Straight-Through*.
   - Menghubungkan **HomeRouter-PT** ke **PC0** (*Port 0/1 / LAN*) menggunakan kabel *Straight-Through*.
   - Memasang modul wireless **WPC300N** pada **Laptop0**.
   - Mengaktifkan interface `GigabitEthernet0/0` pada **Router0** (`no shutdown`).

2. **Pengaturan Wireless & DHCP pada HomeRouter-PT**:
   - Menyetel **SSID** pada tab GUI: `Basic Wireless Settings`.
   - Mengkonfigurasi pengamanan pada `Wireless Security` menggunakan WPA2 Personal dan passphrase `SuksesKompet3n`.
   - Mengaktifkan **DHCP Server** pada menu `Setup` > `Basic Setup`.

3. **Koneksi Client & Pengambilan IP**:
   - **Laptop0**: Terhubung via Wi-Fi ke SSID target menggunakan passphrase `SuksesKompet3n`.
   - **PC0**: Diatur ke mode **DHCP** pada opsi *IP Configuration*.

---

## ✅ Hasil Verifikasi (Testing)

### 1. Pengambilan IP Address (DHCP)
- **Laptop0**: Mendapatkan IP Address `192.168.0.100` / `24`
- **PC0**: Mendapatkan IP Address `192.168.0.101` / `24`

### 2. Uji Konektivitas (Ping Test)
Pengujian koneksi dilakukan dari **Laptop0** ke **PC0** via Command Prompt:
```bash
ping 192.168.0.101
