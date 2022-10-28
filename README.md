# Rust-ohjelmointikielen-perusteet
Rust peruskurssi

## Mikä Rust on?

Rust on Mozilla foundationin kehittämä käännettävä ohjelmointikieli. Rust julkaistiin vuonna 2010. Rustia pidetään tehokkaana ja turvallisena järjestelmätason ohjelmointikielenä, joka soveltuu moneen käyttötarkoitukseen. 

## Rustin asennus
Rustin voit ladata niiden verkkosivuilta. Suositelluin tapa käyttää Rustupia.

(https://www.rust-lang.org/tools/install)


## Ensimmäinen Rust ohjelma

Rust vaatii jokaiseen ohjelmaan main-funktion eli pääohjelman.

Tulostus tapahtuu Rustissa komennolla *println!* .

Ensimmäinen Rust-ohjelma näyttää seuraavalta:
```rust
fn main()
{
  println!("Hello world");
}

```
### Muuttujat

Rust on staattisesti tyypitetty kieli samoin, kuin C++ ja Java.
Kaikissa tilanteissa tyyppia ei ole kuitenkaan pakko antaa, vaan kääntäjä osaa tunnistaa sen automaattisesti.

Rustissa muuttujat aloitetaan sanalla *let* ja vakiot *const*-sanalla.

