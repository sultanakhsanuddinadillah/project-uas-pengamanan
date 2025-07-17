# UAS Keamanan Komputer

## Identitas
- Nama: Sultan Akhsanuddin Adillah
- NIM: 221080200028
- Kelas: Pengamanan Sistem Komputer 6/B4
- Repo GitHub: [https://github.com/sultanakhsanuddinadillah/project-uas-pengamanan/blob/main/template_jawaban.md]

---

## Bagian A – Bug Fixing JWT REST API

### Bug 1: Token tetap aktif setelah logout
**Penjelasan:**  
public function update($id = null)
{
    $data = $this->request->getJSON();
    $this->model->update($id, [
        'username' => $data->username,
        'email' => $data->email,
    ]);

    return $this->respond(['message' => 'Updated']);
}
#token tetep berjalan meski dihenrikan karena perintah tersebut

**Solusi:**  
#perlu ditambahkan syntax
return $this->respondUpdated(['message' => 'Updated']);


## Bagian B – Simulasi Serangan dan Solusi

### Jenis Serangan: Broken Access Control  
**Simulasi Postman:**  
pengamanan kurang terjaga mengakibatkan data banyak bocor

**Solusi Implementasi:**  
adanya himbauan dari crud tambahan

---

## Bagian C – Refleksi Teori & Etika

### 1. CIA Triad dalam Keamanan Informasi  
CIA Triad adalah konsep fundamental dalam keamanan informasi yang terdiri dari tiga elemen utama yaitu kerahasiaan,intergritas,dan ketersediaan

### 2. UU ITE yang relevan  
Pasal 33
“Setiap orang dengan sengaja dan tanpa hak atau melawan hukum melakukan tindakan yang mengakibatkan terganggunya Sistem Elektronik dan/atau mengakibatkan Sistem Elektronik tidak bekerja sebagaimana mestinya.”

### 3. Pandangan Al-Qur'an
Surah Al-Hujurat [49]: 6
"Hai orang-orang yang beriman, jika datang kepadamu orang fasik membawa suatu berita, maka periksalah dengan teliti..."
 Verifikasi informasi sebelum mempercayainya atau menyebarkannya. Sejalan dengan prinsip integritas dan validasi dalam sistem informasi.

### 4. Etika Cyber dan Kejujuran  
Etika cyber adalah panduan berperilaku benar dan jujur dalam dunia maya.
Kejujuran dalam aktivitas digital tidak hanya soal hukum, tapi juga cerminan karakter dan akhlak yang mulia.

