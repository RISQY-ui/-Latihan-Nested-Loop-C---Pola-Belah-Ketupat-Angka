# -Latihan-Nested-Loop-C---Pola-Belah-Ketupat-Angka

# Latihan Nested Loop: Pola Angka (Belah Ketupat)

Pada latihan ini kita belajar menggunakan **nested loop (perulangan bersarang)** untuk membuat pola angka.

Program meminta pengguna memasukkan sebuah angka, kemudian angka tersebut disimpan ke dalam variabel `ris`.

```cpp
int ris;
cin >> ris;
```

Misalnya pengguna memasukkan:

```text
5
```

Maka nilai:

```text
ris = 5
```

Nilai ris inilah yang menjadi batas semua perulangan (for).

Catatan: \n atau endl tidak mengubah nilai ris. Fungsinya hanya untuk berpindah ke baris berikutnya.
Contoh: cout << "\n"; atau cout << endl; keduanya hanya membuat output berpindah ke baris baru.

---

1. Pohon Angka (Segitiga Naik)

Kode:

```cpp
#include <iostream>
using namespace std;

int main() {
    int ris;
    cout << "Masukkan angka: ";
    cin >> ris;

    // Segitiga Naik
    for(int i = 1; i <= ris; i++){
        for(int j = 1; j <= i; j++){
            cout << j;
        }
        cout << endl;
    }

    return 0;
}
```

Jika ris = 5, Output:

```text
1
12
123
1234
12345
```

Cara Kerja

· Loop luar (i) menentukan jumlah baris.
· Loop dalam (j) menentukan berapa angka yang dicetak.

Misalnya:

· Baris pertama: i = 1 → Loop dalam berjalan satu kali → mencetak 1
· Baris kedua: i = 2 → Loop dalam berjalan dua kali → mencetak 12
· Begitu seterusnya hingga mencapai nilai ris.

---

2. Belah Ketupat Angka (Segitiga Naik + Turun)

Tambahkan kode berikut setelah segitiga naik.

Kode Lengkap:

```cpp
#include <iostream>
using namespace std;

int main() {
    int ris;
    cout << "Masukkan angka: ";
    cin >> ris;

    // Segitiga Naik
    for(int i = 1; i <= ris; i++){
        for(int j = 1; j <= i; j++){
            cout << j;
        }
        cout << endl;
    }

    // Segitiga Turun
    for(int k = ris - 1; k >= 1; k--){
        for(int l = 1; l <= k; l++){
            cout << l;
        }
        cout << endl;
    }

    return 0;
}
```

Jika ris = 5, Output menjadi:

```text
1
12
123
1234
12345
1234
123
12
1
```

Cara Kerja Segitiga Turun

· Loop luar (k) dimulai dari ris - 1.
  · Jika ris = 5, maka k = 4.
  · Kemudian terus berkurang: 4, 3, 2, 1.
· Loop dalam (l) mencetak angka mulai dari 1 sampai k.
  · Sehingga menghasilkan: 1234, 123, 12, 1.

Gabungan segitiga naik dan segitiga turun membentuk pola seperti belah ketupat.

---

3. Mengapa Menggunakan l <= k?

Perhatikan kode berikut:

```cpp
for(int l = 1; l <= k; l++)
```

Artinya: Selama nilai l masih kurang dari atau sama dengan k, maka loop akan terus berjalan.

Misalnya:
k = 4 → Maka output: 1234 (karena loop berjalan: 1, 2, 3, 4).

Jika diubah menjadi:

```cpp
for(int l = 1; l <= 1; l++)
```

Outputnya menjadi:

```text
1
1
1
1
```

Karena loop dalam selalu berjalan satu kali saja, berapa pun nilai k.

---

4. Perbedaan cout << l dan cout << k

Mencetak l (cout << l;)
Output: 1234
Karena yang berubah adalah nilai l.

Mencetak k (cout << k;)
Jika k = 4, Output: 4444
Karena nilai k tetap, sedangkan loop hanya mengulang pencetakannya.

---

Kesimpulan

1. ris menyimpan angka yang dimasukkan pengguna melalui cin.
2. \n dan endl hanya berpindah baris, tidak mengubah nilai variabel.
3. Loop luar menentukan jumlah baris.
4. Loop dalam menentukan jumlah angka yang dicetak.
5. cout << l mencetak angka yang berubah.
6. cout << k mencetak angka yang sama berulang.
7. Menggabungkan segitiga naik dan turun menghasilkan pola belah ketupat angka.

💡 Latihan nested loop adalah salah satu cara terbaik untuk melatih logika pemrograman karena kita belajar memahami hubungan antara loop luar dan loop dalam.
