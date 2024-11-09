# AplikasiCekGenapGanjil

APLIKASI GENAP GANJIL

Latihan 1 (Zainal Abidin_2210010087)

KELAS : 5B NONREG BANJARMASIN

DI SINI SAYA :

#1. Membuat Proyek Baru

-Buka NetBeans, pilih File > New Project.

-Pilih Java > Java Application > Next.

-Beri nama proyek dan pilih Create Main Class (atau bisa dihapus jika tidak diperlukan).

#2. Membuat JFrame Form

-Klik kanan pada proyek Anda di Projects tab, pilih New > JFrame Form. Beri nama JFrame, misalnya CekNomorFrame.

#3. Mendesain GUI

Tambahkan komponen berikut ke dalam JFrame:

-JPanel untuk menampung komponen.

-JLabel untuk petunjuk input, misalnya "Masukkan Angka".

-JTextField untuk input angka.

-JButton dengan label "Cek".

-JLabel untuk menampilkan hasil, kosongkan dulu untuk diisi nanti.

#4. Menambahkan "CODING" pada Tombol

Disini saya memasukkan codding pada tombol "CEK"

private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {
try { int angka = Integer.parseInt(inputTextField.getText());

    if (angka % 2 == 0) {
        hasilLabel.setText("Angka " + angka + " adalah Genap");
    } else {
        hasilLabel.setText("Angka " + angka + " adalah Ganjil");
    }
     String hasilPrima;
    if (isPrime(angka)) {
        hasilPrima = "Ya, bilangan prima.";
    } else {
        hasilPrima = "Bukan bilangan prima.";
    }
    
    // Tampilkan hasil bilangan prima di JLabel
    hasilText.setText(hasilPrima);
} catch (NumberFormatException e) {
    JOptionPane.showMessageDialog(this, "Harap masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
}
}            


#5. Menambahkan Validasi Input Gunakan KeyAdapter pada JTextField untuk membatasi input hanya angka dengan koding sebagai berikut :

private boolean isPrime(int n) {

if (n <= 1) return false;
for (int i = 2; i <= Math.sqrt(n); i++) {
    if (n % i == 0) return false;
}
return true;
}


#6 Menambahkan variasi

-Memeriksa bilangan prima:

private boolean isPrime(int n) {

if (n <= 1) return false;
for (int i = 2; i <= Math.sqrt(n); i++) {
    if (n % i == 0) return false;
}
return true;
}

-Menampilkan hasil dengan JOptionPane jika tidak ada angka yang di input:

} catch (NumberFormatException e) {

    JOptionPane.showMessageDialog(this, "Harap masukkan angka yang valid!", "Error", JOptionPane.ERROR_MESSAGE);
}
-Menggunakan FocusListener untuk membersihkan input saat fokus:

inputTextField.addFocusListener(new java.awt.event.FocusAdapter() {

    public void focusGained(java.awt.event.FocusEvent evt) {
        inputTextField.setText(""); // Mengosongkan text field saat mendapatkan fokus
    }
