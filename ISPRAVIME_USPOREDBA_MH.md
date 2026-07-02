# Usporedba nalaza `ispravi.me` i ručne analize

## Kako je provjera provedena

- Tijelo enciklike iz `index.html` (odlomci **§1–§245**) poslano je na `https://ispravi.me/api/ispravi`.
- Zbog ograničenja usluge od **1800 znakova po zahtjevu**, tekst je razlomljen u **249** zasebnih poziva.
- Korištene su opcije:
  - `context = on`
  - `punctuation = on`
  - `showinfo = on`
- **Nije korišten korisnički kolačić** koji je bio naveden u primjeru zahtjeva.
- U ovom izvještaju nisu prepisivani podaci koje servis vraća o mreži i internom ključu korisnika.

## Sažetak rezultata

| Metrika | Vrijednost |
|---|---:|
| Broj API poziva | 249 |
| Uspješnih odgovora (`200`) | 249 |
| Odlomaka s barem jednom prijavom | 106 |
| Ukupno prijavljenih stavki | 150 |

### Raspodjela po klasama koje vraća `ispravi.me`

| Klasa | Broj |
|---|---:|
| `punctuation` | 57 |
| `minor` | 32 |
| `pleonasm` | 13 |
| `moderate` | 13 |
| `extreme` | 11 |
| `info` | 8 |
| `dual` | 6 |
| `unclasifiable` | 5 |
| `grammar` | 3 |
| `style` | 1 |
| `major` | 1 |

## Usporedba s ručnom analizom

Ručna analiza u `ANALIZA_PRIJEVODA_MH.md` označila je **27** ključnih problematičnih mjesta.  
`ispravi.me` je prijavio barem jednu stavku u **17** od tih 27 odlomaka, ali je samo manji dio tih pogodaka stvarno zahvatio **bit problema**.

| Skup | Broj |
|---|---:|
| Ručno označeni odlomci | 27 |
| Ručno označeni odlomci koje je API barem dotaknuo | 17 |
| Ručno označeni odlomci koje API nije dotaknuo | 10 |
| API-jem označeni odlomci koje ručna analiza nije označila | 89 |

## Gdje `ispravi.me` doista pomaže

Ovo su nalazi koje vrijedi uzeti ozbiljno jer se podudaraju s ručnom analizom ili joj korisno dopunjuju trag:

| Odlomak | Nalaz `ispravi.me` | Procjena |
|---|---|---|
| §22 | `pounutarnjujućoj` | **Važna potvrda** ručne analize: riječ je neidiomatska i treba preoblikovanje. |
| §120 | `Odrjeći` → `Odreći` | **Jasna pravopisna pogreška**; ručna analiza ju je ispravno izdvojila. |
| §233 | `suradnjivati` | **Jasna potvrda** ručne analize; bolji je oblik `surađivati`. |
| §3, §4, §5, §17, §82, §230 i dr. | razmaci prije interpunkcije / uz zagrade | **Korisna potvrda** općega uredničkog problema koji se ponavlja kroz tekst. |
| §69 | `bez da` | **Korisni dodatni nalaz** koji ručna analiza nije izdvojila, a vrijedi ga urednički razmotriti. |
| §39 | `ukoliko` → `ako` | Nije pogreška u strogom smislu, ali je **stilski koristan prijedlog** za čišći standardni hrvatski. |

## Gdje `ispravi.me` propušta bitne probleme

Na više mjesta servis nije prepoznao teološki, semantički ili sintaktički problem, nego je uhvatio tek površinski detalj ili ništa.

| Odlomak | Ručno utvrđen problem | Status u `ispravi.me` |
|---|---|---|
| §10 | slomljena i sintaktički nedovršena rečenica | **Promašeno**; uhvaćen je samo razmak uz zagradu. |
| §14 | `povlaštena ljubav prema siromašnima` umjesto ustaljenog `opcija za siromašne` | **Promašeno**. |
| §68 | neslaganje u `Ako je svaka žena i muškarac pozvan` | **Promašeno**. |
| §73 | `viđenja ljudske osobe rođena iz vjere` | **Promašeno**. |
| §110 | `čovjeku prijateljskom` kao doslovni kalk | **Promašeno**. |
| §132 | `istina činjenica` | **Promašeno**. |
| §134 | `silazak u totalitarizam` kao loša metafora | **Promašeno**. |
| §146 | `moglo bi nastati obrazovni sustav` | **Promašeno**. |
| §200 | `samosvjesnom ljudskom kontrolom` | **Promašeno**. |
| §239 | `međudjelovanje` u ovom registru | **Promašeno**. |
| §240 | smisao je preokrenut: `da veću pravednost zamijeni nejednakost` | **Promašeno**, iako je riječ o jednoj od najozbiljnijih pogrešaka u tekstu. |

## Tipični lažno pozitivni ili ograničeno korisni nalazi API-ja

Velik dio prijava nije stvarna pogreška nego posljedica rječničkih i stilskih ograničenja alata.

| Vrsta | Primjer | Procjena |
|---|---|---|
| Biblijske kratice | `Neh` | Lažno pozitivno; legitimna biblijska kratica. |
| Latinski naslovi dokumenata | `Octogesima`, `Exercens`, `Socialis`, `Adveniens` | Lažno pozitivno; vlastita imena / naslovi. |
| Stariji ili svečaniji književni oblici | `utjelovljenomu`, `bratskijega`, `cjelovitomu`, `nepovrjedivom` | Ograničeno korisno; nije nužno pogreška, često je riječ o registru. |
| Teološko-filozofski leksik | `posthumanističkim`, `samoreferencijalna`, `preobraziteljsku` | Često lažno pozitivno zbog ograničena leksika alata. |
| Stilističke primjedbe kao da su tvrde pogreške | `zajedno s`, `sastavni dio`, `na taj način` | Korisno samo kao stilistički signal, ne kao obvezna korekcija. |
| Rijetki, ali mogući oblici | `tkaoci`, `obezčovječuje`, `zamislivima` | Za ručnu provjeru; nije dovoljno za automatsku izmjenu. |

## Zaključak

`ispravi.me` se pokazao **korisnim kao pomoćni alat za tipografiju, pravopisne omaške i poneku očitu jezičnu nespretnost**, ali **nije dovoljan za teološku, prevoditeljsku i stilsku reviziju ove enciklike**.

Najtočniji sažetak usporedbe bio bi:

1. **Dobro hvata površinske greške**: razmake, pojedine zatipke i pokoji loš oblik.
2. **Slabo hvata dubinske prevoditeljske probleme**: semantičke pomake, kalkove, pogrešnu teološku terminologiju i sintaktičke lomove.
3. **Daje dosta lažno pozitivnih nalaza** na latinskim naslovima, biblijskim kraticama i svečanijem crkvenom registru.

Zato je za ovaj tekst najpouzdaniji redoslijed rada:

1. najprije **ručna revizija prijevoda i terminologije**,
2. zatim **`ispravi.me` kao završni jezično-tipografski filter**,
3. pa onda **konačno uredničko čitanje u kontinuitetu cijelog dokumenta**.
