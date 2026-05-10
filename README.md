# Module 09 - Software Architectures (Publisher)

## Tutorial A: Event-Driven Architecture

### a. How much data your publisher program will send to the message broker in one run?
Dalam satu kali eksekusi, program publisher ini akan mengirimkan 5 buah data (pesan) ke *message broker*. Data tersebut adalah representasi dari objek `UserCreatedEventMessage` dengan *user_name* yang memuat NPM dan nama (Amir, Budi, Cica, Dira, dan Emir).

### b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Penggunaan URL yang sama berarti program **Publisher** dan **Subscriber** terhubung ke instans (server) *message broker* RabbitMQ yang persis sama. Hal ini wajib dilakukan karena agar Subscriber bisa menerima pesan dari Publisher, keduanya harus berkomunikasi melalui "jalur" atau "kantor pos" (RabbitMQ di `localhost` port `5672`) yang sama. Jika URL-nya berbeda, pesan yang dikirim Publisher tidak akan pernah sampai ke antrean yang didengarkan oleh Subscriber.