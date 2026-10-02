# sysdocs

Skill untuk assessment dokumentasi, evidence, kepatuhan, dan kesiapan operasional software setelah pengembangan.

## Isi repository

- `.agents/skills/software-post-development-assessment/SKILL.md` — skill siap digunakan ulang oleh AI agent.
- `docs/source-assessment-spec.md` — dokumen spesifikasi asli sebagai referensi.
- `LICENSE` — lisensi MIT.

## Cara menggunakan

Salin direktori `.agents/skills/software-post-development-assessment/` ke lokasi yang sama di workspace atau proyek yang mendukung user-created skills.

Contoh permintaan:

> Gunakan skill software-post-development-assessment untuk menilai dokumentasi dan evidence aplikasi ini. Hasilkan laporan HTML siap cetak.

Sediakan profil aplikasi, scope, dokumentasi/evidence, dan kebijakan atau kontrak yang berlaku. Informasi yang tidak tersedia harus ditandai sebagai belum diketahui atau belum terverifikasi.

## Prinsip assessment

- Jangan mengarang regulasi, requirement, pasal, klausul, atau evidence.
- Pisahkan mandatory, conditional, recommended, not applicable, dan not verified.
- Setiap klaim kepatuhan harus didukung sumber dan evidence yang relevan.
- `NOT VERIFIED` tidak sama dengan `NON-COMPLIANT`.
- Telusurkan sumber → requirement → artefak → evidence → assessment → gap → rekomendasi.

## Output

Laporan utama berupa HTML profesional dengan 22 bagian assessment, layout A4, margin 3 cm, Cambria 12 pt, dan aturan cetak/PDF. Dukungan footer dan nomor halaman bergantung pada browser atau engine cetak yang digunakan.

Skill ini membantu assessment berbasis evidence; bukan sertifikasi compliance, opini hukum, atau jaminan keamanan aplikasi.

## Lisensi

MIT. Lihat [LICENSE](LICENSE).
