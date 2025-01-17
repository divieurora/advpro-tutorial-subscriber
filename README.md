# Advance Programming Tutorial 8
Tutorial for Advanced Programming 2024 Module 8 - Faculty of Computer Science, Universitas Indonesia

---

## Reflection

1. What is `amqp`?

    AMQP atau Advanced Message Queueing Protocol adalah protokol standar lapisan aplikasi yang memungkinkan aplikasi klien berkomunikasi dengan server dan berinteraksi. AMQP juga menentukan protokol lapisan jaringan dan _high-level architecture_ untuk _message brokers_.

2. What it means? `guest:guest@localhost:5672`, what is the first `guest`, and what is the second `guest`, and what is `localhost:5672` is for?

    - `guest` pertama adalah _username_ sedangkan `guest` yang kedua adalah _password_. Dalam hal ini, `guest:guest` berarti _username_ dan _password_-nya adalah guest.
    - `localhost:5672` artinya server berjalan pada mesin klien dengan port 5672 yang merupakan port default untuk AMQP.

## RabbitMQ

1. Simulation slow subscriber

    ![RabbitMQ Slow Rates](/image/RabbitMQ-1.png)

    Total number queue dalam mesin saya adalah 50, karena saya melakukan `cargo run` Publisher sebanyak 10 kali.

2. Running at least three subscribers

    ![Terminal Cargo Run](/image/Terminal.png)
    ![RabbitMQ Slow 3 Subscriber](/image/RabbitMQ-2.png)

    Ketika menjalankan 3 Subscriber, spike berkurang secara lebih cepat karena setiap _request_ yang dikirimkan ke Subscriber dibagi ke 3 Subscribers yang berbeda. Dengan beberapa Subscriber yang _running_, setiap _message_ yang diterima oleh Publisher akan dikirimkan ke masing-masing Subscriber secara paralel.

    Hal yang mungkin dapat di-_improve_ dari _code_ adalah:
    - Pada Subscriber, `thread::sleep` dapat dihilangkan atau dikurangi agar waktu eksekusi dapat menjadi lebih efisien.
    - Pada Publisher, dapat diubah menjadi _asynchronous_ menggunakan _async_/_await_ untuk meningkatkan kinerja dan skalabilitas program.