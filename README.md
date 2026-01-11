# tugas-UAS-pemrograman-Dimas-ferdiansyah-312510504
class StudentData:
    def __init__(self, name, score):
        self.name = name
        self.score = score


class StudentProcess:
    def validate_score(self, score):
        if score < 0 or score > 100:
            raise ValueError("Nilai harus 0 - 100")
        return score

    def get_grade(self, score):
        if score >= 80:
            return "A"
        elif score >= 70:
            return "B"
        elif score >= 60:
            return "C"
        else:
            return "D"


class StudentView:
    def show_table(self, student: StudentData, grade):
        print("================================")
        print("| Nama        | Nilai | Grade |")
        print("================================")
        print(f"| {student.name:11} | {student.score:5} | {grade:5} |")
        print("================================")


# Main Program
process = StudentProcess()

try:
    name = input("Masukkan nama: ")
    nim = input("masukan nim: ")
    score = int(input("Masukkan nilai: "))

    score = process.validate_score(score)

    student = StudentData(name, score)
    grade = process.get_grade(score)

    view = StudentView()
    view.show_table(student, grade)

except ValueError as e:
    print("Error:", e)


- Program ini dibuat untuk meminta data mahasiswa berupa nama, NIM, dan nilai. Setelah itu nilai akan dicek apakah valid (harus berada di antara 0 sampai 100). Jika valid, nilai akan diproses untuk menentukan grade (A, B, C, atau D), kemudian hasilnya ditampilkan dalam bentuk tabel. Program ini menggunakan konsep OOP (Object Oriented Programming) dengan tiga class utama, yaitu StudentData, StudentProcess, dan StudentView.

Class StudentData digunakan untuk menyimpan data mahasiswa. Ketika objek StudentData dibuat, program menyimpan nama dan nilai ke dalam atribut name dan score. Jadi class ini hanya berfungsi sebagai penyimpan data.

Class StudentProcess berfungsi untuk memproses nilai mahasiswa. Di dalamnya ada dua fungsi penting. Pertama, fungsi validate_score yang bertugas mengecek apakah nilai berada dalam rentang 0 sampai 100. Jika nilai kurang dari 0 atau lebih dari 100, program akan menampilkan error menggunakan ValueError, sehingga pengguna tahu bahwa nilai tidak valid. Kedua, fungsi get_grade digunakan untuk menentukan grade berdasarkan nilai. Jika nilai 80 ke atas maka grade A, jika 70 ke atas grade B, jika 60 ke atas grade C, dan jika kurang dari 60 maka grade D.

Class StudentView digunakan untuk menampilkan hasil akhir. Fungsi show_table menampilkan data mahasiswa dalam bentuk tabel sederhana. Di dalam tabel tersebut ditampilkan nama mahasiswa, nilai, dan grade dengan tampilan yang rapi.

Pada bagian main program, pertama dibuat objek StudentProcess. Program kemudian meminta input dari pengguna yaitu nama, NIM, dan nilai mahasiswa. Nilai yang dimasukkan kemudian divalidasi menggunakan fungsi validate_score. Jika nilai valid, maka program membuat objek StudentData untuk menyimpan nama dan nilai mahasiswa. Setelah itu nilai diproses dengan fungsi get_grade untuk mendapatkan grade. Kemudian program membuat objek StudentView dan memanggil fungsi show_table untuk menampilkan nama, nilai, dan grade dalam bentuk tabel. Apabila pengguna memasukkan nilai yang tidak valid, maka program akan masuk ke blok except dan menampilkan pesan kesalahan, sehingga program tidak langsung berhenti secara tiba-tiba.

Secara singkat, alur programnya adalah: input data → validasi nilai → tentukan grade → tampilkan hasil → tangani error jika ada.
