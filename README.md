# advprog-module9-grpc-tutorial

1. What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable?

    Perbedaan utama antara unary, server streaming, dan metode RPC streaming adalah sebagai berikut:

    Unary RPC: Client mengirim satu permintaan dan menerima satu respons dari server. Contoh penggunaan ketika ingin mengambil data dan melakukan autentikasi.

    Server streaming RPC: Client mengirim satu permintaan dan menerima respons dari server dalam bentuk stream. Contoh penggunaan ketika ingin mengambil data dalam jumlah besar.

    Client streaming RPC: Client mengirim stream permintaan ke server dan menerima satu respons dari server. Contoh penggunaan ketika ingin mengunggah file ke server.

    Bidirectional streaming RPC: Client dan server saling mengirim stream data. Contoh penggunaan ketika ingin mengirim pesan real-time.

2. What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption?

    Ketika ingin mengimplementasikan gRPC service di Rust, kita harus melakukan verifikasi dan otorisasi pengguna. Hal ini dapat dilakukan dengan menggunakan token JWT. Selain itu, kita juga harus mengenkripsi data yang dikirimkan antara client dan server. Hal ini dapat dilakukan dengan menggunakan TLS.

3. What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications?

    Beberapa masalah yang mungkin muncul saat menangani bidirectional streaming di Rust gRPC adalah kita harus memastikan bahwa koneksi tetap terbuka selama proses streaming berlangsung. Selain itu, kita juga harus memperhatikan pengelolaan memori dan penanganan kesalahan yang mungkin terjadi selama proses streaming.

4. What are the advantages and disadvantages of using the tokio_stream::wrappers::ReceiverStream for streaming responses in Rust gRPC services?

    Keuntungan menggunakan tokio_stream::wrappers::ReceiverStream adalah kita dapat mengubah Receiver menjadi Stream dengan mudah. Namun, kekurangannya adalah tidak cocok untuk kasus penggunaan yang kompleks dan memerlukan penanganan kesalahan yang lebih baik.

5. In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?

    Untuk memfasilitasi penggunaan kembali kode dan modularitas, kita dapat memisahkan kode ke dalam modul yang berbeda berdasarkan fungsionalitasnya. Selain itu, kita juga dapat menggunakan trait untuk mendefinisikan perilaku yang dapat digunakan oleh berbagai jenis struktur. Hal ini akan memudahkan kita dalam memperluas dan memelihara kode kedepannya.

6. In the MyPaymentService implementation, what additional steps might be necessary to handle more complex payment processing logic?

    mungkin bisa ditambahkan error handling ketika angka yang diinput minus

7. What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?

    Penerapan grpc sebagai protokol komunikasi dalam sistem terdistribusi memiliki dampak besar pada arsitektur dan desain keseluruhan. Diantaranya adalah gRPC menggunakan protokol HTTP/2 untuk transport data, yang mendukung multiplexing, kompresi header, dan streaming. Ini menghasilkan performa yang lebih tinggi dibandingkan dengan protokol REST tradisional, terutama dalam kasus aplikasi yang memerlukan transfer data yang besar atau sering.

8. What are the advantages and disadvantages of using HTTP/2, the underlying protocol for gRPC, compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs?

    Keunggulan HTTP/2 dibandingkan dengan HTTP/1.1 atau HTTP/1.1 dengan WebSocket untuk REST API adalah sebagai berikut:

    Keunggulan HTTP/2:
    - Multiplexing: Memungkinkan multiple requests dan responses dalam satu koneksi TCP.
    - Header Compression: Mengurangi overhead header dengan menggunakan HPACK.

    Kekurangan HTTP/2:
    - Kompleksitas: Memiliki kompleksitas yang lebih tinggi dibandingkan dengan HTTP/1.1.
    - Tidak support di semua server: Belum semua server mendukung HTTP/2.

9. How does the request-response model of REST APIs contrast with the bidirectional streaming capabilities of gRPC in terms of real-time communication and responsiveness? 

    Model request-response pada REST API hanya mendukung komunikasi satu arah, yaitu dari client ke server dan dari server ke client. Sedangkan gRPC mendukung streaming data, baik dari client ke server maupun dari server ke client. Hal ini memungkinkan gRPC untuk mendukung komunikasi real-time dan responsif, yang tidak dapat dicapai dengan REST API.

10. What are the implications of the schema-based approach of gRPC, using Protocol Buffers, compared to the more flexible, schema-less nature of JSON in REST API payloads?

    Pendekatan berbasis skema dari gRPC menggunakan Protocol Buffers memiliki beberapa implikasi dibandingkan dengan pendekatan yang lebih fleksibel dan tanpa skema dari JSON dalam payload REST API:

    Implikasi dari pendekatan berbasis skema gRPC:
    - Validasi data: Protocol Buffers memungkinkan validasi data berdasarkan skema yang telah ditentukan.
    - Performa: Protocol Buffers memiliki ukuran payload yang lebih kecil dan lebih efisien dibandingkan dengan JSON.
    - Interoperabilitas: Protocol Buffers memungkinkan komunikasi antar platform dengan mudah karena skema data yang telah ditentukan.

    Implikasi dari pendekatan tanpa skema JSON:
    - Fleksibilitas: JSON memungkinkan struktur data yang lebih fleksibel dan mudah diubah tanpa perlu memperbarui skema.
    - Keterbacaan: JSON lebih mudah dibaca oleh manusia dibandingkan dengan Protocol Buffers.


