halo kalian. salam ( damai sejahtera dan kasih karunia bagi kita semua ).
db_alkitab.sql. 
Pilih database yang baru dibuat (atau yang sudah ada)
USE db_alkitab; 
2 table, 1. table bible_book, 2. table bible_verses. ( indonesia ).

tutorial : bensonname.
Buat tabel bible_books jika belum ada
CREATE TABLE IF NOT EXISTS bible_books (
    -- Kolom ID sebagai Primary Key, otomatis bertambah
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,

    -- Kolom untuk menyimpan nama lengkap kitab
    -- VARCHAR(100) cukup untuk nama kitab terpanjang sekalipun
    book_name VARCHAR(100) NOT NULL,

    -- Kolom untuk menentukan Perjanjian (Lama/Baru)
    -- ENUM membatasi nilai hanya 'Old' atau 'New'
    testament ENUM('Old', 'New') NOT NULL,

    -- Kolom untuk menyimpan singkatan kitab
    -- VARCHAR(10) cukup untuk singkatan seperti '1Sa' atau 'Why'
    -- UNIQUE memastikan tidak ada dua kitab dengan singkatan yang sama
    abbreviation VARCHAR(10) UNIQUE,

    -- Kolom untuk menyimpan jumlah pasal
    -- SMALLINT cukup karena jumlah pasal tidak akan terlalu besar
    -- UNSIGNED karena jumlah pasal tidak mungkin negatif
    -- NOT NULL karena skrip Anda selalu menyediakan nilainya
    chapter_count SMALLINT UNSIGNED NOT NULL

    -- Tentukan Storage Engine ke InnoDB (default di MySQL modern)
    -- InnoDB diperlukan untuk fitur seperti Foreign Keys nanti
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

view :
'Old' => [
        ['Kejadian', 'Kej', 50],
        ['Keluaran', 'Kel', 40],
        ['Imamat', 'Ima', 27],
        ['Bilangan', 'Bil', 36],
        ['Ulangan', 'Ula', 34],
        ['Yosua', 'Yos', 24],
        ['Hakim-hakim', 'Hak', 21],
        ['Rut', 'Rut', 4],
        ['1 Samuel', '1Sa', 31],
        ['2 Samuel', '2Sa', 24],
        ['1 Raja-raja', '1Ra', 22],
        ['2 Raja-raja', '2Ra', 25],
        ['1 Tawarikh', '1Ta', 29],
        ['2 Tawarikh', '2Ta', 36],
        ['Ezra', 'Ezr', 10],
        ['Nehemia', 'Neh', 13],
        ['Ester', 'Est', 10],
        ['Ayub', 'Ayb', 42],
        ['Mazmur', 'Mzm', 150],
        ['Amsal', 'Ams', 31],
        ['Pengkhotbah', 'Pen', 12],
        ['Kidung Agung', 'Kid', 8],
        ['Yesaya', 'Yes', 66],
        ['Yeremia', 'Yer', 52],
        ['Ratapan', 'Rat', 5],
        ['Yehezkiel', 'Yeh', 48],
        ['Daniel', 'Dan', 12],
        ['Hosea', 'Hos', 14],
        ['Yoel', 'Yoe', 3],
        ['Amos', 'Amo', 9],
        ['Obaja', 'Oba', 1],
        ['Yunus', 'Yun', 4],
        ['Mikha', 'Mik', 7],
        ['Nahum', 'Nah', 3],
        ['Habakuk', 'Hab', 3],
        ['Zefanya', 'Zef', 3],
        ['Hagai', 'Hag', 2],
        ['Zakharia', 'Zak', 14],
        ['Maleakhi', 'Mal', 4],
    ],
    // === Perjanjian Baru ===
    'New' => [
        ['Matius', 'Mat', 28],
        ['Markus', 'Mrk', 16],
        ['Lukas', 'Luk', 24],
        ['Yohanes', 'Yoh', 21],
        ['Kisah Para Rasul', 'Kis', 28],
        ['Roma', 'Rom', 16],
        ['1 Korintus', '1Ko', 16],
        ['2 Korintus', '2Ko', 13],
        ['Galatia', 'Gal', 6],
        ['Efesus', 'Efe', 6],
        ['Filipi', 'Flp', 4],
        ['Kolose', 'Kol', 4],
        ['1 Tesalonika', '1Te', 5],
        ['2 Tesalonika', '2Te', 3],
        ['1 Timotius', '1Ti', 6],
        ['2 Timotius', '2Ti', 4],
        ['Titus', 'Tit', 3],
        ['Filemon', 'Flm', 1],
        ['Ibrani', 'Ibr', 13],
        ['Yakobus', 'Yak', 5],
        ['1 Petrus', '1Pe', 5],
        ['2 Petrus', '2Pe', 3],
        ['1 Yohanes', '1Yo', 5],
        ['2 Yohanes', '2Yo', 1],
        ['3 Yohanes', '3Yo', 1],
        ['Yudas', 'Yud', 1],
        ['Wahyu', 'Why', 22],
