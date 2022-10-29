# Rust-ohjelmointikielen-perusteet
Rust peruskurssi

## Mikä Rust on?

Rust on Mozilla foundationin kehittämä käännettävä ohjelmointikieli. Rust julkaistiin vuonna 2010. Rustia pidetään tehokkaana ja turvallisena järjestelmätason ohjelmointikielenä, joka soveltuu moneen käyttötarkoitukseen. 

## Rustin asennus
Rustin voit ladata niiden verkkosivuilta. Suositelluin tapa käyttää Rustupia.

(https://www.rust-lang.org/tools/install)


## Ensimmäinen Rust-ohjelma

Rust vaatii jokaiseen ohjelmaan main-funktion eli pääohjelman.

Tulostus tapahtuu Rustissa komennolla *println!* .

Ensimmäinen Rust-ohjelma näyttää seuraavalta:
```rust
fn main()
{
  println!("Hello world");
}

```

#### Kommentit

Kommentit tehdään Rustilla täysin samoin, kuin vaikkapa C++ tai Javassa.
```rust
//Tämä on yhden rivin kommentti.

/* Tämä 
on usean rivin kommentti. */

```


### Muuttujat

Rust on staattisesti tyypitetty kieli samoin, kuin C++ ja Java.
Kaikissa tilanteissa tyyppia ei ole kuitenkaan pakko antaa, vaan kääntäjä osaa tunnistaa sen automaattisesti.

Rustissa muuttujat aloitetaan sanalla *let*. Rustissa kaikki muuttujat ovat muuttumattomia. Jotta voimme muuttaa muuttujaa sen esittelyn ja määrittelyn jälkeen, on 
käytettävä avainsanaa mut.

```rust
let a = 0; //Tämän muuttujan arvoa ei voida muuttaa.

a = 2; //Tämä ei toimi.

let mut b = 0; //Tämän arvon voi muuttaa.

b = 5; //Tämä toimii.

const VAKIO = 0; //Vakioita voidaan luoda *const* avainsanalla.
```


### Ehdot ja ehtolauseet

#### Vertailuoperaattorit
| Operaattori | Kuvaus | Esimerkki |
| --- | --- | --- |
| == | Yhtäsuuri | 5 == 5 |
| != | Erisuuri | 5 != 6 |
| >= | Suurempi tai yhtäsuuri | 10 >= 5 |
| <= | Pienempi tai yhtäsuuri | 5 <= 6 |
| > | Suurempi kuin | 15 > 5 |
| < | Pienempi kuin | 4 < 5 |

#### Matemaattiset operaattorit
| Operaattori | Kuvaus | Esimerkki |
| --- | --- | --- |
| + | Yhteenlasku | 5 + 5 |
| - | Vähennyslasku | 5 - 5 |
| * | Kertolasku | 5 * 5 |
| / | Jakolasku | 5 / 5 |
| % | Jakojäännös | 5 % 2 |


| Operaattori | Kuvaus | Esimerkki |
| --- | --- | --- |
| && | AND | x == 5 && y == 5|
| &#124&; | OR | x == 5 || y == 5 |
| ! | NOT | !(a > 10) |
