class Pengguna:
    def _init_(self, id, nama, peran):
        self.id = id
        self.nama = nama
        self.peran = peran

    def login(self):
        print(f"{self.nama} berhasil login.")

class AdminDosen(Pengguna):
    def _init_(self, id_dosen, nama_dosen, email):
        super()._init_(id_dosen, nama_dosen, "admin_dosen")
        self.email = email

    def kelola_data_mahasiswa(self):
        print("Admin/Dosen mengelola data mahasiswa (tambah/hapus).")

    def input_absensi(self, mahasiswa, status):
        print(f"Absensi {mahasiswa.nama} diinput dengan status: {status}")
        # Logika untuk menyimpan data absensi ke database

class Mahasiswa(Pengguna):
    def _init_(self, id_mahasiswa, nama_mahasiswa):
        super()._init_(id_mahasiswa, nama_mahasiswa, "mahasiswa")

    def cek_absensi_pribadi(self):
        print(f"{self.nama} melihat absensi pribadi.")
        # Logika untuk menampilkan data absensi dari database

# Contoh penggunaan
admin = AdminDosen(1, "Pak Budi", "budi@example.com")
mahasiswa1 = Mahasiswa(101, "Aulia")
mahasiswa2 = Mahasiswa(102, "Yogi")
mahasiswa3 = Mahasiswa(103, "Nurul")

admin.login()
admin.kelola_data_mahasiswa()
admin.input_absensi(mahasiswa1, "Hadir")

mahasiswa2.login()
mahasiswa2.cek_absensi_pribadi()# nur
