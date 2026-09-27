# API Test Automation & CI/CD Gatekeeper Pipeline
Final Assignment: Postman, Newman, Data-Driven Testing (CSV), Token Handling & GitHub Actions

Project otomatisasi pengujian API untuk platform Script Labs dengan integrasi CI/CD dan pembuktian pipeline sebagai Gatekeeper.

---

## Struktur Folder

```text
final-assignment-api-test/
├── .github/workflows/
│   └── api-test.yml          # GitHub Actions workflow (push & PR ke main)
├── collections/
│   ├── labs-api-collection.json  # Suite regresi utama (Auth + CRUD Labs)
│   ├── labs-ddt-collection.json  # Suite Data-Driven Testing
│   └── labs-gatekeeper-demo.json # Suite intentional failure untuk demo Gatekeeper
├── environments/
│   └── labs-environment.json     # Environment variables (baseUrl, token dinamis, dll.)
├── data/
│   └── ddt-labs-scenario.csv     # Test data CSV (Valid, Invalid, Edge Case)
├── reports/                      # Output laporan HTML Newman (gitignored)
├── .env.example                  # Template konfigurasi environment
├── .gitignore                    # File gitignore
├── package.json                  # Script runner npm
└── README.md                     # Dokumentasi project
```

## Cara Menjalankan Secara Lokal

### Prasyarat
* Node.js v18+

### Perintah Run
```bash
# Install dependensi
npm install

# Jalankan regression test suite (11 request)
npm test

# Jalankan data-driven testing (CSV)
npm run test:ddt

# Jalankan semua test dan generate HTML report di folder reports/
npm run test:report

# Jalankan demo Gatekeeper
npm run test:gatekeeper
```
