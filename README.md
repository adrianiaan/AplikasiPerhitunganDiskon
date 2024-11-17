# Aplikasi Perhitungan Diskon  
Tugas 3 - [Nama Anda] ([NPM Anda])

---

## Deskripsi

Aplikasi ini digunakan untuk menghitung harga akhir setelah diskon diterapkan. Pengguna dapat memasukkan harga asli, memilih persentase diskon melalui `JComboBox` atau `JSlider`, serta menambahkan kode kupon untuk diskon tambahan. Hasil perhitungan disertai riwayat akan ditampilkan di antarmuka.

---

## Fitur Aplikasi

1. **Perhitungan Diskon**:  
   - Pengguna memasukkan harga asli di `JTextField` dan memilih persentase diskon melalui `JComboBox` atau `JSlider`.  
   - Hasil berupa harga akhir dan penghematan ditampilkan setelah tombol **Hitung** ditekan.  
   - **Contoh Kode Implementasi**:  
     ```java
     private void btnHitungActionPerformed(java.awt.event.ActionEvent evt) {
         try {
             double hargaAsli = Double.parseDouble(txtHargaAsli.getText().replace("Rp ", "").replace(",", ""));
             int DiskonPersen = sldDiskon.getValue();
             double penghematan = hargaAsli * DiskonPersen / 100;
             double hargaAkhir = hargaAsli - penghematan;
             txtPenghematan.setText("Rp " + String.format("%,.2f", penghematan));
             txtHargaAkhir.setText("Rp " + String.format("%,.2f", hargaAkhir));
         } catch (NumberFormatException e) {
             JOptionPane.showMessageDialog(this, "Masukkan nilai yang valid.", "Error", JOptionPane.ERROR_MESSAGE);
         }
     }
     ```

2. **Validasi Input**:  
   - Input harga asli hanya dapat berupa angka dengan awalan "Rp".  
   - **Contoh Kode Implementasi**:  
     ```java
     private void txtHargaAsliKeyTyped(java.awt.event.KeyEvent evt) {
         if (!txtHargaAsli.getText().startsWith("Rp ")) {
             txtHargaAsli.setText("Rp ");
         }
     }
     ```

3. **Kode Kupon Tambahan**:  
   - Diskon tambahan dapat diterapkan jika kode kupon yang dimasukkan valid.  
   - **Contoh Kode Implementasi**:  
     ```java
     if (kodeKupon.equalsIgnoreCase("DISKON5%")) {
         DiskonPersen += 5;
     } else if (!kodeKupon.isEmpty()) {
         JOptionPane.showMessageDialog(this, "Kode kupon tidak ada.", "Info", JOptionPane.INFORMATION_MESSAGE);
     }
     ```

4. **Riwayat Perhitungan**:  
   - Semua hasil perhitungan disimpan dan ditampilkan di `JTextArea`.  
   - **Contoh Kode Implementasi**:  
     ```java
     String hasilRiwayat = "Harga Asli: Rp " + String.format("%,.2f", hargaAsli) +
                           ", Diskon: " + DiskonPersen + "%" +
                           ", Penghematan: Rp " + String.format("%,.2f", penghematan) +
                           ", Harga Akhir: Rp " + String.format("%,.2f", hargaAkhir) + "\n";
     txtRiwayat.append(hasilRiwayat);
     ```

---

## Komponen GUI

Aplikasi ini menggunakan komponen berikut:
- **JFrame**: Jendela utama aplikasi.  
- **JPanel**: Panel utama untuk menata elemen GUI.  
- **JLabel**: Label untuk input dan hasil.  
- **JTextField**: Untuk input harga asli dan output hasil.  
- **JComboBox**: Memilih persentase diskon.  
- **JSlider**: Alternatif untuk memilih diskon secara dinamis.  
- **JButton**: Tombol untuk memproses perhitungan.  
- **JTextArea**: Menampilkan riwayat perhitungan.  

---

## Struktur Program

### 1. Desain GUI  
   - Komponen ditata menggunakan `GridBagLayout` untuk fleksibilitas tata letak.  

### 2. Logika Program  
   - Melakukan perhitungan harga akhir berdasarkan persentase diskon.
   - 
   - Tambahan logika untuk memproses kode kupon diskon tambahan.  

### 3. Events  
   - **ActionListener**: Menghitung hasil ketika tombol **Hitung** ditekan.  
   - **ItemListener**: Memperbarui nilai diskon pada `JSlider` berdasarkan pilihan `JComboBox`.  
   - **ChangeListener**: Menyesuaikan persentase diskon saat `JSlider` digeser.  

---

## Cara Menjalankan Aplikasi

1. Clone atau unduh repositori ini.  
2. Buka proyek di NetBeans IDE 8.2.  
3. Jalankan file utama `PerhitunganDiskonFrame.java`.  
4. Masukkan harga asli, pilih diskon, tambahkan kode kupon (opsional), dan tekan tombol **Hitung**.

## Tampilan Aplikasi Pada saat Dijalakan
![image](https://github.com/user-attachments/assets/9e39213a-ea83-481a-9760-4a35c108042e)


---

## Indikator Penilaian

| No  | Komponen           | Persentase |
|-----|---------------------|------------|
| 1   | Komponen GUI       | 20%        |
| 2   | Logika Program     | 20%        |
| 3   | Events             | 15%        |
| 4   | Kesesuaian UI      | 15%        |
| 5   | Memenuhi Variasi   | 30%        |
| **TOTAL** |               | **100%**   |

---

## Pembuat

- **Nama**: Adrian Akhmad Firdaus  
- **NPM**: 2210010491
- **Kelas**: 5A Reguler Pagi
- **Tugas**: Tugas 3 - Aplikasi Perhitungan Diskon  
- **Fakultas**: Fakultas Teknologi Informasi (FTI)
- **Universitas**: Universitas Islam Kalimantan Muhammad Arsyad Al Banjari Banjarmasin

--- 
