---
name: software-post-development-assessment
description: Menilai kelengkapan dokumentasi, evidence, kepatuhan, dan kesiapan operasional aplikasi setelah pengembangan. Gunakan saat pengguna meminta post-development assessment, audit dokumentasi software, compliance/readiness review, gap analysis, atau laporan serah-terima aplikasi. Hasil laporan utama harus HTML profesional yang siap dibuka, dicetak, dan diekspor ke PDF.
---

# Software Post-Development Documentation & Compliance Assessment

## Tujuan

Lakukan assessment yang objektif, berbasis sumber, dan dapat ditelusuri terhadap dokumentasi, artefak, evidence, dan kesiapan operasional aplikasi pascapengembangan. Bedakan dengan tegas:

- kewajiban yang memiliki dasar berlaku;
- rekomendasi yang bukan kewajiban;
- requirement bersyarat;
- hal yang tidak berlaku; dan
- hal yang belum dapat diverifikasi.

Jangan memberi opini hukum atau menyatakan aplikasi “aman”, “100% compliant”, atau memenuhi suatu standar secara menyeluruh. Batasi kesimpulan pada scope dan evidence yang benar-benar diperiksa.

## Prinsip utama

### Jangan mengarang requirement

- Jangan mengarang regulasi, standar, versi, pasal, klausul, kewajiban, atau evidence.
- Jangan menyebut dokumen sebagai wajib hanya karena lazim dipakai atau direkomendasikan.
- Jangan menyamakan standar internasional, framework, guidance, atau praktik industri dengan hukum.
- Jangan mengubah rekomendasi menjadi kewajiban.
- Jangan menyimpulkan compliance tanpa evidence yang relevan.
- Jika dasar kewajiban belum ditemukan, tulis **“Dasar normatif belum terverifikasi.”**
- Jika bukti belum tersedia, tulis **“Belum dapat diverifikasi berdasarkan evidence yang tersedia.”**
- `NOT VERIFIED` tidak sama dengan `NON-COMPLIANT`.

Telusurkan setiap finding melalui rantai:

`SOURCE → REQUIREMENT → EXPECTED ARTEFACT → EVIDENCE → ASSESSMENT → GAP → RECOMMENDATION`

## Kapan digunakan

- Pengguna meminta penilaian dokumentasi atau compliance software setelah development.
- Pengguna ingin mengetahui dokumen/evidence yang dibutuhkan sebelum go-live atau handover.
- Pengguna meminta gap analysis, readiness assessment, atau laporan audit aplikasi.

## Alur kerja

### 1. Tetapkan scope dan profil aplikasi

Kumpulkan dari materi yang diberikan atau sumber yang tersedia. Jangan mengarang; untuk informasi yang tidak ada, tandai `UNKNOWN` atau `NOT PROVIDED`.

Catat sejauh tersedia:

- nama, tujuan, versi, owner, developer/vendor, pengguna, dan jenis aplikasi;
- criticality, status lifecycle, serta production/non-production;
- deployment model, hosting/environment, dan apakah internet-facing;
- jenis data, termasuk apakah memproses data pribadi;
- integrasi/API dan layanan pihak ketiga;
- cloud/on-premise, authentication, authorization/RBAC, database, dan technology stack;
- scope assessment, assessor, tanggal assessment, serta klasifikasi kerahasiaan.

Jika scope belum cukup untuk menentukan applicability, nyatakan keterbatasannya dan minta hanya informasi yang benar-benar diperlukan. Jangan menerapkan domain bersyarat tanpa dasar bahwa kondisinya terpenuhi.

### 2. Tetapkan baseline sumber

Gunakan urutan otoritas berikut, sejauh relevan:

1. Regulasi yang berlaku dan keputusan/peraturan internal organisasi.
2. Requirement organisasi atau kontraktual: kebijakan, SOP, security/IT/architecture policy, development standard, kontrak/SLA, TOR/SOW, dan requirement proyek resmi.
3. Standar internasional yang relevan dengan scope, misalnya ISO/IEC/IEEE 12207, 15289, 29148, ISO/IEC 25010, NIST SP 800-218, OWASP ASVS, atau OWASP SAMM.
4. Guidance dan praktik industri.

Jangan menyebut standar/framework sebagai hukum. Labeli jenis sumber secara eksplisit: `REGULATION`, `MANDATORY ORGANIZATIONAL REQUIREMENT`, `INTERNATIONAL STANDARD`, `FRAMEWORK`, `GUIDANCE`, atau `INDUSTRY PRACTICE`.

Untuk setiap sumber, catat:

- nama sumber dan organisasi penerbit;
- versi/tahun dan klausul/pasal/section bila dapat diverifikasi;
- URL resmi atau rujukan resmi;
- status: `VERIFIED`, `PARTIALLY VERIFIED`, `NOT VERIFIED`, `DRAFT`, atau `RETIRED/SUPERSEDED`;
- kutipan singkat atau parafrasa yang dapat ditelusuri.

Utamakan publikasi resmi penerbit/regulator. Jangan memakai blog, forum, artikel vendor, atau konten AI sebagai dasar utama kewajiban. Labeli sumber sekunder dengan jelas. Jika diperlukan verifikasi sumber terkini, gunakan skill `web-search` dan cari sumber resmi; jangan menebak URL atau status versi. Jangan memakai draft sebagai dasar kewajiban tanpa menjelaskan statusnya.

### 3. Klasifikasikan setiap requirement

Pilih satu klasifikasi:

- `MANDATORY` — ada dasar regulasi, kontrak, requirement, atau kebijakan organisasi yang jelas dan berlaku.
- `CONDITIONAL` — hanya berlaku bila kondisi tertentu terpenuhi; sebutkan kondisi dan evidence pemicunya.
- `RECOMMENDED` — didukung standar/framework/guidance/praktik profesional, tetapi tidak terbukti sebagai kewajiban yang berlaku.
- `NOT APPLICABLE` — tidak relevan berdasarkan karakteristik aplikasi; berikan alasan.
- `NOT VERIFIED` — mungkin relevan, tetapi sumber, applicability, atau evidence belum cukup untuk menilai.

Jangan menyebut SBOM atau artefak lain wajib untuk semua aplikasi. Terapkan klasifikasi yang sama dan verifikasi dasar kewajibannya untuk konteks yang sedang dinilai.

### 4. Periksa artefak dan evidence

Evidence dapat mencakup dokumen, source code, repository/commit/tag, konfigurasi, schema database, spesifikasi API, hasil dan bukti pengujian, security scan, penetration test, vulnerability assessment, deployment/release record, approval, UAT, log, screenshot, backup/restore test, dan operational record.

Nilai evidence sebagai `SUFFICIENT`, `PARTIALLY SUFFICIENT`, `INSUFFICIENT`, `NOT AVAILABLE`, atau `NOT VERIFIED`. Catat nama/lokasi evidence dan keterbatasannya bila diketahui. Jangan mengklaim sudah memeriksa file, repository, atau system yang tidak benar-benar tersedia.

Nilai substansi, bukan nama dokumen. Bedakan `DOCUMENT EXISTS` dari `REQUIREMENT SATISFIED`: keberadaan suatu file saja belum membuktikan isinya memenuhi requirement.

Periksa domain berikut jika relevan:

1. Requirements
2. Architecture & Design
3. Development
4. Testing
5. Security
6. Release & Deployment
7. Operations & Maintenance
8. Data
9. Third Party
10. Handover

Untuk security, pisahkan `TEST PERFORMED`, `FINDING IDENTIFIED`, `FINDING REMEDIATED`, `RETEST PERFORMED`, dan `RISK ACCEPTED`. Scan atau penetration test tanpa temuan tidak membuktikan bahwa aplikasi aman.

### 5. Tentukan status dan gap

Untuk setiap requirement, gunakan status:

- `COMPLIANT`
- `PARTIALLY COMPLIANT`
- `NON-COMPLIANT`
- `NOT APPLICABLE`
- `NOT VERIFIED`

Status harus didukung oleh basis dan evidence. Ketiadaan evidence tidak otomatis membuktikan ketidakpatuhan; gunakan `NOT VERIFIED` kecuali ada bukti positif yang mendukung `NON-COMPLIANT`.

Tulis rekomendasi yang proporsional dan dapat ditindaklanjuti. Tandai prioritas dan prasyarat bila sumber mendukungnya. Jangan menciptakan tenggat, pemilik, atau kewajiban baru. Jelaskan bila keputusan kesiapan go-live memerlukan penerimaan risiko atau persetujuan pihak berwenang yang belum tersedia.

## Format matriks

Requirement Matrix minimal memuat:

| Requirement | Basis | Classification | Applicability/Condition | Evidence | Evidence Assessment | Status |
|---|---|---|---|---|---|---|

Traceability Matrix minimal menghubungkan:

| Source | Requirement | Expected Artefact | Evidence | Assessment | Gap | Recommendation |
|---|---|---|---|---|---|---|

## Struktur laporan akhir

Berikan semua laporan utama sebagai satu file HTML mandiri, bukan Markdown, DOCX, atau PDF sebagai format utama. Sertakan bagian berikut; untuk bagian yang tidak relevan atau tidak memiliki data, nyatakan alasannya atau `NOT PROVIDED`/`NOT VERIFIED`, bukan mengarang:

1. Executive Summary
2. Application Profile
3. Assessment Scope
4. Assessment Methodology
5. Regulatory & Standards Baseline
6. Source Verification
7. Requirement Matrix
8. Documentation Assessment
9. Evidence Assessment
10. Requirements & Architecture Assessment
11. Development & Configuration Assessment
12. Testing Assessment
13. Security Assessment
14. Deployment & Release Assessment
15. Operations & Maintenance Assessment
16. Data & Third-Party Assessment
17. Handover & Acceptance Assessment
18. Gap Analysis
19. Remediation Recommendation
20. Traceability Matrix
21. Conclusion
22. References

Halaman awal memuat nama aplikasi, versi, tanggal assessment, assessor, owner, developer/vendor, environment, scope, status assessment, standar yang berlaku, dan klasifikasi kerahasiaan sejauh tersedia. Gunakan `NOT PROVIDED` untuk metadata yang tidak tersedia.

References mencantumkan nama sumber, penerbit, versi/tahun, status, URL resmi bila terverifikasi, serta tanggal akses jika dilakukan web verification. Jika URL resmi tidak dapat diverifikasi, tulis `Official URL: NOT VERIFIED`.

## Persyaratan HTML dan cetak

Buat HTML valid yang dapat dibuka di browser dan dicetak/diekspor ke PDF. Gunakan dokumen bernuansa profesional/audit—bukan dashboard—dengan warna secukupnya dan tetap terbaca dalam cetak hitam-putih.

Gunakan konfigurasi cetak berikut sebagai baseline:

```css
@page {
  size: A4;
  margin: 3cm;
}

html,
body {
  margin: 0;
  padding: 0;
}

body {
  font-family: Cambria, Georgia, serif;
  font-size: 12pt;
  line-height: 1.3;
  text-align: justify;
}
```

Gunakan Cambria untuk teks utama; H1 sekitar 16–18 pt, H2 14–16 pt, H3 12–14 pt, dan tabel sekitar 9–11 pt. Hindari terlalu banyak font, warna neon, gradient berlebihan, atau dekorasi tanpa fungsi.

Gunakan label teks selain warna untuk status: `COMPLIANT` hijau, `PARTIALLY COMPLIANT` kuning/oranye, `NON-COMPLIANT` merah, `NOT VERIFIED` abu-abu, dan `NOT APPLICABLE` abu-abu muda. Warna tidak boleh menjadi satu-satunya penanda.

Sertakan identitas laporan yang konsisten dan footer pada halaman cetak dengan nama aplikasi, “Software Post-Development Assessment”, dan nomor halaman bila engine mendukungnya. Gunakan CSS paged-media page counter jika tersedia; bila tidak, gunakan fallback print-friendly dan jangan mengklaim nomor halaman otomatis jika memang tidak didukung.

Gunakan aturan print berikut agar konten tidak hilang atau terpotong:

```css
h1, h2, h3 {
  break-after: avoid;
  page-break-after: avoid;
}

table {
  width: 100%;
  border-collapse: collapse;
}

tr, img, pre, blockquote, .card, .evidence-block {
  break-inside: avoid;
  page-break-inside: avoid;
}

thead {
  display: table-header-group;
}

.section {
  break-inside: auto;
}

.page-break {
  break-before: page;
  page-break-before: always;
}
```

Untuk tabel panjang, biarkan tabel berlanjut ke halaman berikutnya dan ulangi header bila engine mendukungnya. Jangan mengecilkan font secara ekstrem hanya agar tabel muat satu halaman. Pastikan isi tabel membungkus teks dan tidak menyebabkan horizontal overflow. Hindari fixed-height container dan `overflow: hidden` untuk konten laporan; gunakan tinggi otomatis dan `overflow: visible`.

Gunakan struktur semantik `header`, `main`, dan `footer`, serta `<!DOCTYPE html>`, `<html lang="id">`, charset UTF-8, viewport, title, dan CSS inline agar berkas mudah dibuka sebagai satu dokumen.

## Pemeriksaan sebelum menyerahkan laporan

- Setiap klaim mandatory memiliki sumber, status, dan basis yang dapat diverifikasi.
- Nama versi, tahun, pasal, klausul, dan URL tidak ditebak.
- Rekomendasi tidak disajikan sebagai kewajiban.
- Applicability conditional dijelaskan; domain N/A diberi alasan.
- Setiap klaim compliance punya evidence yang relevan.
- Keberadaan dokumen dibedakan dari pemenuhan requirement.
- `NOT VERIFIED` dibedakan dari `NON-COMPLIANT`.
- Temuan dapat ditelusuri dari sumber sampai rekomendasi.
- Kesimpulan keamanan dan kesiapan dibatasi oleh scope serta evidence.
- HTML memakai A4, margin 3 cm, Cambria 12 pt, line-height 1.3, alignment justify, dan layout cetak yang wajar.
- Tidak ada konten terpotong, overflow horizontal, atau elemen panjang yang disembunyikan.
- Metadata dan referensi yang tidak tersedia ditandai, bukan diisi dengan asumsi.