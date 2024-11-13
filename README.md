# KonversiSuhu
 Latihan 2 - (Muhammad Fajar Fitrianto_2210010748) 
# Aplikasi Konversi Suhu
`Deskripsi`

KonversiSuhuForm adalah aplikasi berbasis Java Swing yang dirancang untuk mengonversi suhu dari satu skala ke skala lainnya, seperti Celsius ke Fahrenheit dan sebaliknya. 

Aplikasi ini memiliki antarmuka yang ramah pengguna dengan komponen seperti tombol, label, dan bidang input untuk memudahkan penggunaan.

# Fitur
-Input suhu dalam skala Celsius atau Fahrenheit Dan sebaliknya

-Konversi suhu antar skala dengan satu klik.

-Antarmuka grafis menggunakan JFrame untuk kemudahan interaksi.

# Penjelasan Koding
 
 Struktur Kode

1.import Library

`import javax.swing.*;`

`import java.awt.event.KeyAdapter;`

`import java.awt.event.KeyEvent;`

2.Deklarasi dan Inisialisasi Kelas:

public class KonversiSuhuForm extends javax.swing.JFrame {
   
    public KonversiSuhuForm() {
        initComponents();
         txtSuhu.addKeyListener(new KeyAdapter() {
        public void keyTyped(KeyEvent evt) {
            // Memeriksa apakah karakter yang dimasukkan adalah angka atau titik
            if (!Character.isDigit(evt.getKeyChar()) && evt.getKeyChar() != '.') {
                evt.consume(); // Menolak input jika bukan angka atau titik
            }
        }
    });
    }
    
    
"Kelas ini memperluas `JFrame`, yang berarti aplikasi menggunakan antarmuka pengguna berbasis Java Swing Dan meninisiasi apakah karakter yang di input adalah angka atau titik,Serta menolak input jika bukan angka maupun titik"

3.Metode `initComponents():`

Metode ini mengatur semua komponen GUI seperti `JLabel`, `JTextField`, dan `JButton`.

Komponen diatur dengan LayoutManager untuk mengatur tata letaknya di jendela aplikasi.

4.implementasi rumus konversi

`public double konversiSuhu(double suhu, String dari, String ke) {`
    
    // Implementasikan rumus konversi
    if (dari.equals("Celsius") && ke.equals("Fahrenheit")) {
        return (suhu * 9 / 5) + 32;
    } else if (dari.equals("Fahrenheit") && ke.equals("Celsius")) {
        return (suhu - 32) * 5 / 9;
    }
    // Tambahkan logika untuk konversi lainnya sesuai kebutuhan
    return suhu; // Jika tidak ada konversi yang cocok, kembalikan suhu asli

5.Event Handling serta isi perintah

`private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {`                                         
   
     String suhuText = txtSuhu.getText(); // Ambil teks dari txtSuhu

    // Cek apakah input kosong
    if (suhuText.isEmpty()) {
        hasil.setText("Input tidak boleh kosong!"); // Tampilkan pesan kesalahan
        return; // Keluar dari metode jika input kosong
    }

    try {
        double suhu = Double.parseDouble(suhuText); // Konversi ke double
        String dari = comboBoxSuhu.getSelectedItem().toString();
        String ke = ""; // Anda perlu menentukan nilai ini berdasarkan pilihan konversi

        // Menentukan nilai 'ke' berdasarkan pilihan radio button
        if (jRadioButton1.isSelected()) {
            ke = "Fahrenheit"; // Jika radio button untuk Celsius ke Fahrenheit dipilih
        } else if (jRadioButton2.isSelected()) {
            ke = "Celsius"; // Jika radio button untuk Fahrenheit ke Celsius dipilih
        } else {
            hasil.setText("Pilih jenis konversi!"); // Jika tidak ada pilihan radio button
            return;
        }

        // Lakukan konversi suhu
        double hasilKonversi = konversiSuhu(suhu, dari, ke);
        
        // Tampilkan hasil konversi di JLabel
        hasil.setText("Hasil: " + hasilKonversi);
    } catch (NumberFormatException e) {
        hasil.setText("Input tidak valid!"); // Tampilkan pesan kesalahan jika input tidak valid
    }
    }                             
# Cara Menjalankan

-Buka proyek di NetBeans.

-Jalankan proyek dengan menekan Run atau Shift + F6.


