# DriveBridge – letöltés és telepítés tesztelőknek

A DriveBridge Android-alkalmazás: vezetés közben, a telefon érintése nélkül beszélhetsz a saját Claude-fiókoddal. A kérdést diktálod, a választ az autó hangszórója olvassa fel, a vezérlés az autó médiagombjaival megy.

Az alkalmazás zárt tesztben van, és nincs a Google Playen. A tesztelők innen töltik le a telepítőfájlt (APK).

## Aktuális verzió

| | |
|---|---|
| Verzió | 0.9.0 (build 55) |
| Kiadva | 2026-10-08 |
| Fájl | `DriveBridge-0.9.0.apk`, 133 280 bájt |
| Letöltés | [DriveBridge-0.9.0.apk](https://github.com/Endre999/Release/releases/download/v0.9.0/DriveBridge-0.9.0.apk) |
| SHA-256 | `4b74baeb247747c5f9cc2050e430ac9d45406fb307d5c3b7ae70141f9b4b7650` |

Minden kiadás a [Releases](https://github.com/Endre999/Release/releases) oldalon van, közvetlenül letölthető APK-ként, ZIP-csomagolás nélkül.

## Amire szükséged van

- Android-telefon, Android 13 vagy újabb. A diktáláshoz a telefon beszédfelismerője kell, magyar nyelvi támogatással.
- Autó, amely Bluetoothon hangot játszik le, és vannak médiagombjai.
- Claude-fiók, amelyhez egyéni connector adható.
- Böngésző vagy Claude Desktop a connector egyszeri hozzáadásához.
- Internetkapcsolat a telefonon vezetés közben.

## Telepítés

1. Töltsd le a telefonra a fenti `DriveBridge-0.9.0.apk` fájlt.
2. Nyisd meg a letöltött fájlt, és engedélyezd a telepítést ebből a forrásból, amikor az Android rákérdez.
3. Indítsd el a DriveBridge-et. Két engedélyt kér: a mikrofont a diktáláshoz és az értesítéseket a médiavezérlőhöz.
4. Ellenőrizd a főképernyő alján a feliratot: `Build 0.9.0 (55)`.

Az alkalmazásban nincs bejelentkezés. Az első indításkor név és e-mail-cím nélkül regisztrál a DriveBridge szerverén.

### Ha már van a telefonon korábbi DriveBridge tesztverzió

- A `0.9.0-test18` verzióra a 0.9.0 ráfrissíthető, eltávolítás nélkül.
- Az ennél régebbi tesztverziókat előbb el kell távolítani, mert más aláírással készültek, és az Android nem engedi rájuk telepíteni az újat. Az eltávolítás törli a telefonon tárolt leiratokat, ezért a megtartandókat előbb mentsd ki az alkalmazás Leiratok listájából.

## Beüzemelés

A teljes, lépésenkénti útmutató a honlapon van: **[DriveBridge beüzemelése](https://www.pandaonthemoon.io/hu/drivebridge/setup/)**. Ugyanezt nyitja meg az alkalmazás Kapcsolódás kártyáján a „Beállítási útmutató” gomb.

A lényeg röviden:

1. **Connector hozzáadása a Claude-hoz**, egyszer. Név: `DriveBridge`, cím: `https://mcp.pandaonthemoon.io/mcp`.
2. **Jóváhagyás.** A hozzáadáskor megnyíló „DriveBridge engedélyezés” oldal tulajdonosi jelszót kér. Ezt a jelszót a tesztelők nem kapják meg: a teszt alatt ezt a lépést közösen végezzük el veled. Egyeztess időpontot azzal, akitől a tesztmeghívót kaptad.
3. **Eszközengedélyek.** A Claude-ban a DriveBridge minden eszközét állítsd „Always allow” értékre. Ha a Claude vezetés közben engedélyt kér, senki nem tudja megnyomni a választ, és a beszélgetés megáll.
4. **Minden út elején:** csatlakoztasd a telefont az autóhoz Bluetoothon, nyomd meg a DriveBridge-ben a Kapcsolódás gombot, majd a vágólapra másolt mondatot illeszd be és küldd el abban a Claude-beszélgetésben, amelyben dolgozni szeretnél.

A gombok részletes leírása: [DriveBridge vezérlés](https://www.pandaonthemoon.io/hu/drivebridge/controls/).

## Ismert hibák a 0.9.0-ban

- Az autó médialejátszóján előfordulhat, hogy nem jelenik meg a DriveBridge ikonja. A vezérlés, a diktálás és a felolvasás ettől függetlenül működik.
- Ha közben másik alkalmazásban (például a YouTube-on) szól valami, előfordulhat, hogy a Claude magától küldött közlése nem hangzik el. A diktált kérdésre adott válasz felolvasását ez nem érinti.

## Hová kerül, amit mondasz

- A diktált szöveg és a válaszok a DriveBridge szerverén haladnak át a telefon és a Claude között, és ott nem tárolódnak tartósan.
- A beszédet a telefon beszédfelismerő szolgáltatása alakítja szöveggé, nem a DriveBridge.
- A beszélgetés a saját Claude-fiókodban marad. A DriveBridge nem fér hozzá a Claude-belépésedhez, a beszélgetéseid listájához és a projektjeid tartalmához.
- A menet leirata 7 napig megmarad a telefonon, utána törlődik.

Részletek: [Adatvédelem](https://www.pandaonthemoon.io/hu/privacy/), [Feltételek](https://www.pandaonthemoon.io/hu/terms/).

## Visszajelzés

A hibákat és az észrevételeket annak jelezd, akitől a tesztmeghívót kaptad. Segít, ha megírod a verziót (`Build 0.9.0 (55)`), a telefon és az autó típusát, és azt, hogy mit csináltál közvetlenül a hiba előtt.

## A letöltött fájl ellenőrzése

Nem kötelező. A fájl SHA-256 kivonata egyezzen a fenti értékkel; ugyanez a Releases oldalon a `DriveBridge-0.9.0.apk.sha256` fájlban is megvan.

Az APK a DriveBridge saját kiadási kulcsával van aláírva. Az aláíró tanúsítvány SHA-256 ujjlenyomata:

`eeb48e8fc76744ca4c07f0fa13dfa0d1684894250a7f870a214e2492b203e5fa`
