# RabbitmqNotes

Broker: Rabbitmq nun çalıştığı kısımdır, master ve slave olarak bulunabilir.
Producer: Mesajları rabbitmqya gönderir, mesajla birlikte routing key bilgiside gönderilmelidir.
mesajın ulaşıp ulaşmadığı confirm.select ile kontrol edilir.
Exchange(önemli!): Gelen mesajları routing key sayesinde kuyruklara yönlendiren sana bir alan. 4 e ayrılır.
- Direct Exchange:
    Exchange'e bağlı olan her kuyruğun dinlediği sadece 1 key vardır.
    Point to point olarak bilinir. Aşağı örnekte görüldüğü gibi sadece aynı isimde olan binding keyler birbirine bağlanabilir. 
        a.bey ======> a.bey
        b.dey ======> b.dey
        c.*      x
- Topic Exhange
    Burada binding key yapısı biraz daha farklı olarak bağlanır ve işleme alınır. Aşağıdaki örnekte görüldüğü gibi gelen tüm bilgiler key veya valueya göre gelir.
        Notification.Email ==========> *.Email
        Alert.Email ===========> alert.*
        Notification.Sms ========> *.Sms
- Fanout Exchange
    Key value yapısına bakılmaksızın rabbitden gönderilen veriler karşıya aktarılır.
- Header Exchange
    Headerda key value olarak bir dictionary gönderilir. 
    Burada x-match "any" dersek key veya value nun eşleşmesi beklenir.
    Eğer x-match "all" dersek, key ve valuenun eşleşmesi beklenir.
