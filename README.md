# Advance Programming Tutorial 8
Tutorial for Advanced Programming 2024 Module 8 - Faculty of Computer Science, Universitas Indonesia

---

## Reflection

1. What is `amqp`?

    AMQP atau Advanced Message Queueing Protocol adalah protokol standar lapisan aplikasi yang memungkinkan aplikasi klien berkomunikasi dengan server dan berinteraksi. AMQP juga menentukan protokol lapisan jaringan dan _high-level architecture_ untuk _message brokers_.

2. What it means? `guest:guest@localhost:5672`, what is the first `guest`, and what is the second `guest`, and what is `localhost:5672` is for?

    - `guest` pertama adalah _username_ sedangkan `guest` yang kedua adalah _password_. Dalam hal ini, `guest:guest` berarti _username_ dan _password_-nya adalah guest.
    - `localhost:5672` artinya server berjalan pada mesin klien dengan port 5672 yang merupakan port default untuk AMQP.