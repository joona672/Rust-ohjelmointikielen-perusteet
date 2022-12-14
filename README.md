# Rust-ohjelmointikielen-perusteet
Rust peruskurssi

## Mikä Rust on?

Rust on Mozillan kehittämä käännettävä ohjelmointikieli. Rust julkaistiin vuonna 2010. Rustia pidetään tehokkaana ja turvallisena järjestelmätason ohjelmointikielenä, joka soveltuu moneen käyttötarkoitukseen. 

## Rustin asennus
Rustin voit ladata niiden verkkosivuilta. Suositelluin tapa käyttää Rustupia.

(https://www.rust-lang.org/tools/install)

Voit myös kokeilla Rustia netissä. Esimerkiksi Rust-playground.
(https://play.rust-lang.org/)


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

Tulostaessa muuttujien arvoja, tulee argumenttina olla merkkijono tai vähintään `"{}"` ja pilkulla erotettuna muuttuja/muuttujat.
Ohjelma korvaa aaltosulut muuttujien arvoilla.

##### Esimerkki
```rust
fn main()
{
  let x:u8 = 20;
  let y:u8 = 10;
  
  println!("Muuttujan x arvo on {}", x); //Tämä toimii. Ohjelma tulostaisi: Muuttujan x arvo on 20
  
  println!("{}", x); //Tämä toimii myös
  
  println!(x); //Tämä ei toimi
  
  println!("{} {}", x, y); //Useamman muuttujan tulostus. Tulostus näyttäisi: 20 10
}
```

Rust antaa varoituksen käyttämättömistä muuttujista.
Halutessaan tämän saa kytkettyä pois lisäämällä ohjelman 
alkuun `#[allow(unused_variables)]` rivin.

#### Tietotyypit
| Koko | Etumerkillinen | Etumerkitön |
| --- | --- | --- |
| 8 bittiä | i8 | u8 |
| 16 bittiä | i16 | u16 |
| 32 bittiä | i32 | u32 |
| 64 bittiä | i64 | u64 |
| Riippuu koneen arkkitehtuurista | isize | usize |


Jos muuttuja saa suuremman arvon, kuin sen koko sallii, alkaa muuttuja uudelleen nollasta.
##### Esimerkki
```rust
   // 0-255 on etumerkittömän 8-bittisen laajuus.
   let x:u8 = 256;   //Muuttujalle tulee arvoksi 0
   let y:u8 = 257;   //Muuttujalle tulee arvoksi 1
   let z:u8 = 258;    //Muuttujalle tulee arvoksi 2
```

##### Float
Float on liukuluku. Liukuluvulla on kaksi tyyppiä `f32` ja `f64`.

##### Boolean
Boolean muuttujalla on vain kaksi tilaa, jotka ovat `true` ja `false`.
Alla esimerkki Tämäntyyppisistä muuttujista.

```rust
fn main()
{
  let a = true;
  let b:bool = false;
}
```

##### Char ja string
Char on yhden merkin mittainen muuttujatyyppi. Rustissa char vie 4 tavua toisin, kuin useimmissa kielissä char vie vain 1 tavun.


```rust
fn main()
{
  let merkki = '@';
  let merkki2:char = '♥';
  
}
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
| \|\| | OR | x == 5 || y == 5 |
| ! | NOT | !(a > 10) |


#### if-lause

If-lause alkaa if avainsanalla, tätä seuraa ehto. Ehdon toteutuessa mennään lohkon sisään.
```rust
let luku = 5;
if luku == 5
{
  println!("Muuttujan luku arvo on 5");
}
```

Usein on tarpeen lisätä vaihtoehtoja if lohkoon. Jos ylläolevassa esimerkissä muuttujan luku arvo olisi muu, kuin 5, mitään ei tapahtuisi.
Voimme lisätä else-haaran, joka toteutetaan silloin, kun luku ei ole viisi.
Voimme luoda myös useampia haaroja else if-lauseen avulla. Else if-haaroja voi käytännössä kuinka paljon tahansa.

##### Esimerkki

```rust
let luku = 5;
if luku == 5
{
  println!("Muuttujan luku arvo on 5");
} else if luku > 100 {
  println!("Muuttujan luku arvo on suurempi, kuin 100");
} else {
  println!("Muuttujan luku arvo ei ole 5, mutta se ei ole 100 suurempi");
}

```
