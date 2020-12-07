# IntAlkBeadando
Készítette: 2.Csapat: Kirner Ábel, van Bochove Viktor

Az oldal egy fogadási oldalt hivatott megvalósítani, ahol bejelentkezés után tud a felhasználó fogadást tenni. A fogadás, pedig bekerül egy fogadás táblába, ahol a username és a találati szám tárolódik.

Az admin belépés után az admin felületen látja a felhasználók és fogadások listáját. Tud felhasználót hozzáadni és felhasználót törölni, valamint fogadást törölni.
Létrehozott database belépési adatai:

database:
    user: projekt
    jelszo: jelszo

Felhasználó tábla létrehozása

    create table felhasznalok(
    userid INT not null GENERATED ALWAYS AS IDENTITY
        (START WITH 1, INCREMENT BY 1), 
    username varchar(50),
    password varchar(50),
    email varchar(50),
    PRIMARY KEY(userid),
    UNIQUE(username)    
    );
    
Kezdeti belépési adatok

    insert into felhasznalok(username,password,email) values('admin','jelszo','admin@admin.hu');
    insert into felhasznalok(username,password,email) values('teszt','jelszo','teszt@teszt.hu');
    
Fogadási tábla létrehozása

    create table fogadasok(
    fogadas_id int not null generated always as identity,
    username varchar(50),
    talalatszama varchar(50),
    Primary key(fogadas_id)
    );

Nehézség volt a projekt során, hogy lehet átadni taglib kódnak egy java kódban létrehozott változót. Amit végül a request.setAttribute(’változó’, valtozonev) kóddal sikerült megoldani.

Valamint integer érték beszúrása is nehézség volt a projekt során. A fogadás táblában a találati érték beszúrása, csak stringként valósult meg, valamint az admin változó is stringként került beszúrásra a felhasználó táblába, ami nem a legoptimálisabb megoldás.
Illetve az adatbázis a projekttel való exportálása is nehézséget jelentett.
