# GCP - Implementasi Autoscaling & Load Balancing
Membuat simulasi aplikasi implementasi Autoscaling & Load Balancing pada Google Cloud Platformm. 

Casenya : 
- Aplikasi tersedia secara global, bisa melayani basis user yang ada di Asia Tenggara dan Eropa.
- Infrastruktur dapat menyesuaikan kapasitas secara otomatis (autoscaling).
- Pemantauan terhadap infrastruktur cloud.
- Auditor eksternal memiliki akses untuk mengaudit arsitektur cloud.

Tahapan : 
1. Membuat 2 Firewall Rules agar bisa berkomunikasi walau beda region yaitu asia dan europe karena dari pihak client meminta setting di region tersebut. 
2. Kemudian agar bisa berkomunikasi secara global jangan lupa allow HTTP,
3. Selanjutnya membuat Instance Templete agar memudahkan nanti untuk autoscaling, Membuat 2 Instance Templete yaitu untuk Asia (asia-southeast-2) dan Europe (europe-west1). Saya sebelumnya menggunakan yang singapore namun sepertinya ketersediaan disana kurang jadi untuk autoscaling tidak memungkinkan /tidak maksimal jadi saya mengubahnya ke jakarta (asia-southeast2)
4. Membuat Instance Group agar nantinya kita bisa mengontrol dengan mudah instance yang dibuat.
5. Setelah kita konfigure Instance Templele dan Instance Group, kita bisa melihat instance yang terbuat. 
6. Selanjutnya Saya Mengkonfigurasi Load Balancer agar ketika terjadi autoscaling traffic bisa terbagi dan autoscaling yang sudah dibuat bisa maksimal. 
7. Pada Load Balancing ini saya membuat settingan pada frontend dengan menggunakan 2 IP yaitu IPv4 dan IPv6. Kemudian pada bagian backend saya menambahkan 2 group yaitu untuk asia-group & europe-group. 
8. Setelah konfigurasi berhasil, IP bisa diakses dan menampilkan keterangan instance. 
9. Selanjutnya jangan lupa membuat Cloud Monitoring secara custom agar kita bisa memantau sesuai keinginan.
10. Menghitung Pricing dari resource yang digunakan.

Tools : 
- Design Cloud Architect : https://app.diagrams.net/
- GCP Pricing Calculator : https://cloud.google.com/products/calculator
- GCP : https://console.cloud.google.com/

Services : 
- Compute Engine (Instances Templete, Instances Group, VM Instances)
- VPC Network : Firewall Rule
- Cloud Monitoring : Dashboard Custom
- Network Services : Load Balancing
