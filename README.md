# Jarkom_Modul1_Praktikum_C10

## Kelompok C_10
## Asisten Dosen Bella Septina 
## Adrian Danindra 05111840000068
## Amelia Puji     05111840000147


### 1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
Jawab :
- Menggunakan display filter http.host ==  “testing.mekanis.me”

![96018508-f2138b00-0e7d-11eb-8752-79cbf9a28578](https://user-images.githubusercontent.com/57977401/96024558-7833cf80-0e86-11eb-81ed-81e7c4dd0f87.png)

- Klik kanan => follow => TCP Stream pada HTTP

![2](https://user-images.githubusercontent.com/57977401/96024712-add8b880-0e86-11eb-9620-e7b7100db918.png)

### 2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
Jawab :
- Menggunakan Export Objects dengan langkah 
  File => Export Objects => HTTP..
- Masukkan Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436 jpg pada Text Filter 
- Klik pada gambar, save as

![3](https://user-images.githubusercontent.com/57977401/96024850-e7112880-0e86-11eb-9f68-ccd84b4a8630.png)

### 3.	Cari username dan password ketika login di "ppid.dpr.go.id"!
Jawab : 

- Menggunakan display filter http.host == "ppid.dpr.go.id" && http.request.method == "POST" atau http.host == "ppid.dpr.go.id" && http contains login

![image](https://user-images.githubusercontent.com/57977401/96019076-9990bd80-0e7e-11eb-96e8-be0e98032b9c.png)

- Klik kanan, follow, TCP Stream. Pada filter, ketik user dan cari tulisan yang bertulisakn "username" dan "password"

![image](https://user-images.githubusercontent.com/57977401/96019076-9990bd80-0e7e-11eb-96e8-be0e98032b9c.png)

### 4. Temukan paket dari web-web yang menggunakan basic authentication method!
Jawab : 
- Ada 5 web dengan display filter http.authbasic. 
Testing.mekanisme.me dan aku.pengen.pw, beserta 3 favicon dan png dibawahnya. Bisa dilihat pada gambar dibawah

Untuk testing.mekanisme.me

![image](https://user-images.githubusercontent.com/57977401/96019205-ca70f280-0e7e-11eb-94ab-222b1194948e.png)
dan

Untuk aku.pengen.pw

![image](https://user-images.githubusercontent.com/57977401/96019365-0310cc00-0e7f-11eb-9f68-6a6db55f473a.png)

### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
Jawab : 
- Display filter http.host == "aku.pengen.pw". Hypertext Transfer Protocol. Authorization basic. Credentials berisi username dan password

![image](https://user-images.githubusercontent.com/57977401/96019511-36ebf180-0e7f-11eb-97f2-090de3183dc9.png)

- Masukkan username dan password. Selesai

![image](https://user-images.githubusercontent.com/57977401/96019594-4e2adf00-0e7f-11eb-86cb-6cc4aa982fb9.png)

### 6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
Jawab : 
Untuk Answer.zip
- Display filter ftp-data.command == "STOR Answer.zip".
- Pada salah satu FTP-DATA, klik kanan => follow => TCP Stream. 

![image](https://user-images.githubusercontent.com/57977401/96019637-5f73eb80-0e7f-11eb-9463-184b26e832c1.png)

- Pada bagian bawah (show and save data as) pilih raw, lalu save as

![image](https://user-images.githubusercontent.com/57977401/96019675-70246180-0e7f-11eb-8499-6af41c897ab6.png)

Lakukan langkah yang sama dengan zipkey nya. 
-  Display filter ftp-data.command == "STOR zipkey.txt".

![6b](https://user-images.githubusercontent.com/57977401/96020000-f8a30200-0e7f-11eb-98a6-c2ee6856497f.png)

- Pada file FTP-DATA, klik kanan => follow => TCP Stream. akan terlihat passwordnya seperti gambar dibawah

![6b2](https://user-images.githubusercontent.com/57977401/96020176-33a53580-0e80-11eb-936f-287ff1d87e77.png)

- Masukkan password pada Open This.pdf, lalu hasilnya akan muncul seperti ini

![image](https://user-images.githubusercontent.com/57977401/96020306-664f2e00-0e80-11eb-937d-e3652d830942.png)

### 7.Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
Jawab : 
- Display filter menggunakan frame contains "Yes.pdf". 
- Lalu seperti biasa, klik kanan => follow => TCP Stream

![image](https://user-images.githubusercontent.com/57977401/96020410-91398200-0e80-11eb-8eb7-8e5102e0d68e.png)

- Pada bagian bawah (show and save data as) pilih raw. 

![7b](https://user-images.githubusercontent.com/57977401/96020611-df4e8580-0e80-11eb-812c-08aa3eaa0765.png)

- Lalu save as. Extract file zip lalu buka file Yes.pdf

![image](https://user-images.githubusercontent.com/57977401/96020662-f2f9ec00-0e80-11eb-985f-f3da415b5833.png)

### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
Jawab : 
- Dengan display filter ftp.request.command == "RETR". Klik kanan => follow => TCP Stream, lalu muncul paling atas Microsoft FTP Service

![image](https://user-images.githubusercontent.com/57977401/96020920-5421bf80-0e81-11eb-9b93-44dd830df0ee.png)

### 9. Cari username dan password ketika login FTP pada localhost!
Jawab : 
- Filter menggunakan query ftp
- Username dan password terlihat di stream dengan command USER dan PASS (ftp.request.command == “PASS” dan ftp.request command == “USER”)
Untuk PASSWORD 

![9a](https://user-images.githubusercontent.com/57977401/96022531-94823d00-0e83-11eb-9f3e-b9bbd4f90b02.png)
Untuk USER

![9b](https://user-images.githubusercontent.com/57977401/96022672-cbf0e980-0e83-11eb-90dd-b3ee2a97706d.png)
- Atau bisa dilakukan dengan klik kanan => follow => TCP Stream

![9c](https://user-images.githubusercontent.com/57977401/96022871-1f633780-0e84-11eb-90a6-97d1ed84463d.png)
- Akan didapatkan Username : dhana, password: dhana123

### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46" 
Jawab : 
- Display filter dengan frame contains "application/pdf" dan pencet ctrl + F, lalu pada display filter diganti hex value dan masukkan 25 50 44 46

![image](https://user-images.githubusercontent.com/57977401/96022933-386be880-0e84-11eb-809a-d7a538723b2f.png)

- Klik kanan => follow => TCP Stream
- Pada bagian bawah (show and save data as) => ubah ASCII menjadi raw. Lalu save as.

![image](https://user-images.githubusercontent.com/57977401/96022988-533e5d00-0e84-11eb-965f-e2e5d6d878e8.png)

- Ketik (nama pdf).pdf, lalu buka. Hasilnya adalah undang-undang

![image](https://user-images.githubusercontent.com/57977401/96023030-63563c80-0e84-11eb-932f-2e1fd88d87e8.png)

### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
Jawab : 
Mengetikkan Port 21

![image](https://user-images.githubusercontent.com/57977401/96023157-900a5400-0e84-11eb-87aa-fc041e49270a.png)

![image](https://user-images.githubusercontent.com/57977401/96023164-939ddb00-0e84-11eb-8a15-2f7048cd0be0.png)

### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
Jawab : 
Mengetikkan src port 80

![image](https://user-images.githubusercontent.com/57977401/96023233-b03a1300-0e84-11eb-9305-999df1d43a60.png)

![image](https://user-images.githubusercontent.com/57977401/96023239-b29c6d00-0e84-11eb-9e18-851b6d9aa672.png)

### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
Jawab : 
Mengetikkan dst port 443

![image](https://user-images.githubusercontent.com/57977401/96023345-dcee2a80-0e84-11eb-8109-f8ce8d3fcae9.png)

### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
Jawab : 
Mengetikkan src net (IP masing - masing)
- IP Amel

![image](https://user-images.githubusercontent.com/57977401/96023660-56861880-0e85-11eb-8449-a5b0f3c4e56a.png)

- IP Adrian 

![image](https://user-images.githubusercontent.com/60964359/96082804-199e3e00-0ee6-11eb-8e13-5f7ece856a04.png)

* IP bisa didapat dari Command Prompt dengan mengetikkan ipconfig. Scroll kebawah sedikit hingga menemukan IPv4 Address

![14](https://user-images.githubusercontent.com/57977401/96023622-479f6600-0e85-11eb-8961-6d3444128c1e.png)

### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
Jawab : 
Mengetikkan dst monta.if.its.ac.id

![image](https://user-images.githubusercontent.com/57977401/96023876-a2d15880-0e85-11eb-9a76-2aac859e768f.png)

![image](https://user-images.githubusercontent.com/57977401/96023881-a533b280-0e85-11eb-8acf-4364cb5639d0.png)
