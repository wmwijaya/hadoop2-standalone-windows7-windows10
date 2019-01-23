# hadoop2-standalone-windows7
Cara sederhana install Hadoop 2 mode Standalone pada Windows 7

Artikel ini dimuat di http://www.teknologi-bigdata.com/ website tentang teknologi big data: teori dan contoh implementasi.

Hadoop adalah framework open-source  berbasis Java yang ditujukan untuk memproses data secara terdistribusi melalui kemampuan penyimpanan data secara terdistribusi. Hadoop dapat menyimpan data apapun dan memprosesnya dengan model pemrograman MapReduce. Hadoop didesain untuk dapat mengatasi permasalahan yang disebabkan oleh kegagalan fungsi hardware sehingga dapat mencegah hilangnya data maupun proses kerja. Hadoop memotong-motong data untuk didistribusikan ke setiap node di dalam suatu kluster untuk kemudian diproses secara paralel dan lokal di tiap node yang bersangkutan.

Kebutuhan Software
Berikut adalah software yang harus disiapkan untuk dapat menjalankan Hadoop 2 mode standalone dengan OS Windows 7:
1. Java JDK 1.8, dapat diunduh dari https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
2. Apache Hadoop 2.7.7, dapat diunduh dari https://hadoop.apache.org/releases.html
3. Hadoop Patch File untuk OS Windows, dapat diunduh dari https://github.com/wmwijaya/hadoop2-standalone-windows7

Langkah-langkah Install Hadoop-2.7.7
1. Download JDk 1.8 dari URL Java JDK diatas, install dan kemudian set JAVA_HOME dan Path pada Environment Variables>System Variables Windows 7.
2. Download Apache Hadoop-2.7.7 (hadoop-2.7.7.tar.gz). Ekstrak, kemudian pindahkan dikehendaki. Pada tutorial ini, direktori hadoop-2.7.7 adalah C:\hadoop-2.7.7
3. Edit file hadoop-env.cmd yang ada di direktori C:\hadoop-2.7.7\etc\hadoop menggunakan Notepad atau Notepad++ atau text editor lain: set variabel JAVA_HOME sesuai lokasi instal Java JDK 1.8 pada OS Windows 7. Pada tutorial ini adalah: set JAVA_HOME=C:"\Program Files\Java\jdk1.8.0_201"
4. Edit file core-site.xml yang ada di direktori C:\hadoop-2.7.7\etc\hadoop dengan menggunakan Notepad atau Notepad++ atau text editor lain. Silahkan di-copy-paste contoh berikut:
5. Edit file hdfs-site.xml yang terdapat pada direktori C:\hadoop-2.7.7\etc\hadoop untuk menentukan jumlah replika yang harus dibuat, kemudian lokasi namenode dan datanode seperti pada contoh:
6. Masih di direktori C:\hadoop-2.7.7\etc\hadoop, copy file mapred-site.xml.template, kemudian paste pada direktori ini dan ganti namanya menjadi mapred-site.xml. Edit seperti contoh berikut untuk menentukan dimana aplikasi MapReduce pada Hadoop harus dijalankan.
7. Tetap pada direktori C:\hadoop-2.77\etc\hadoop, edit file yarn-site.xml seperti pada contoh berikut:
8. Agar Hadoop dapat dioperasikan pada OS Windows, diperlukan patch file Hadoop yang spesifik untuk OS Windows. Patch file ini secara default tidak menjadi bawaan Hadoop. Patch file tersebut bisa diperoleh dari Github URL https://github.com/wmwijaya/hadoop2-standalone-windows7 dengan mengunduh semua file yang ada dalam direktori bin. Kemudian, hapus semua file yang ada dalam direktori C:\hadoop-2.7.7\bin, ganti dengan patch file yang sudah diunduh tersebut.
9. Set HADOOP_HOME dan Path pada Environment Variables>System Variables Windows 7. Nilai variabel HADOOP_HOME adalah C:\hadoop-2.7.7 sedangkan pada variabel Path silakan diisi C:\hadoop-2.7.7\bin dan C:\hadoop-2.7.7\sbin seperti pada contoh.
10. Jalankan aplikasi Command Prompt Windows sebagai Administrator, kemudian eksekusi perintah hadoop namenode --format
11. Jalankan Command Prompt Windows sebagai Administrator, eksekusi perintah start-all.cmd untuk menjalankan Namenode, Datanode, Resource Manager, dan Nodemanager. Masing-masing service tersebut akan membuka jendela Command Prompt baru. Jika anda ingin mengetahui service apa saja yang sedang berjalan, silakan eksekusi perintah jps di Command Prompt.

Demikian, Hadoop sudah selesai di-install dan berjalan pada mode standalone. Penampilan GUI-nya dapat diakses melalui URL berikut:
Resource Manager : http://localhost:8088
Namenode : http://localhost:50070

Selamat mencoba!
