# ERA-MAPS · Region 5
**Smart Integrated Erajaya Retail Analytics — Store Mapping Dashboard**

Platform: SIERA · Erajaya Digital

---

## Tentang ERA-MAPS

Dashboard peta interaktif untuk monitoring 193 toko Erajaya Region 5 (Jakarta, Tangerang, Tangsel, Banten).

**Fitur:**
- Peta 3D Mapbox dengan ekstrusi gedung
- 193 pin toko dengan identitas visual per brand (Erafone, iBox, Samsung, Erablue, Huawei, Honor)
- Search & filter tipe toko, area, sales store
- Detail panel: info toko, store leader, alamat lengkap
- Tombol WhatsApp Store Leader & Google Maps
- Koordinat real-time saat hover peta

---

## Stack

| Layer | Tech |
|-------|------|
| Peta | Mapbox GL JS v3.3.0 |
| Style | Mapbox light-v11 + 3D buildings |
| Data | Hardcoded dari Excel UPDATE_STO Region 5 |
| Hosting | Netlify |
| Font | Plus Jakarta Sans (Google Fonts) |

---

## Struktur File

```
era-maps/
├── index.html        ← Semua-dalam-satu (HTML + CSS + JS + Data)
├── netlify.toml      ← Konfigurasi Netlify
├── .gitignore
└── README.md
```

---

## Deploy

### Netlify Drop (Cepat)
1. Buka [netlify.com/drop](https://app.netlify.com/drop)
2. Drag seluruh folder `era-maps/` ke area drop
3. Dapat URL → share ke tim

### GitHub + Netlify (Auto-deploy)
```bash
git init
git add .
git commit -m "ERA-MAPS v1.0 - 193 stores Region 5"
git remote add origin https://github.com/USERNAME/era-maps.git
git push -u origin main
```
Kemudian di Netlify → New site → Import from Git → pilih repo.

---

## Mapbox Token

Token sudah tertanam di `index.html`. Untuk keamanan production:
1. Login ke [account.mapbox.com](https://account.mapbox.com)
2. **Tokens → Edit** token
3. **Allowed URLs** → tambahkan domain Netlify kamu
   - `https://era-maps-reg5.netlify.app`
   - `https://si-era.netlify.app` (jika integrate ke SIERA)

---

## Update Data Toko

Buka `index.html`, cari `const STORES_RAW=` lalu edit array JSON.

Format tiap toko:
```json
{
  "id": "E001",
  "name": "Erafone Grand Indonesia",
  "type": "Erafone",
  "city": "Jakarta Pusat",
  "area": "Jakarta Pusat",
  "mall": "Grand Indonesia",
  "sl": "Nama Store Leader",
  "hp": "628123456789",
  "addr": "Alamat lengkap toko",
  "lat": -6.1952,
  "lng": 106.8213,
  "skor": 88,
  "mtd": "2.4B",
  "target": "3.5B"
}
```

---

## Roadmap

- [ ] Phase 2: Integrasi Google Sheets (live data toko)
- [ ] Phase 3: Sales data real-time dari ERA-SALES
- [ ] Phase 4: Heatmap coverage area
- [ ] Phase 5: Export PDF laporan per area

---

*ERA-MAPS adalah bagian dari platform SIERA (Smart Integrated Erajaya Retail Analytics)*  
*Dikembangkan untuk RMO Region 5 · Erajaya Digital*
