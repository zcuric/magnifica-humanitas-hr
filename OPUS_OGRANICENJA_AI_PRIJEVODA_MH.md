# Ograničenja AI-prijevoda — studija na primjeru enciklike *Magnifica Humanitas*

**Predmet.** Usporedba dvaju hrvatskih prijevoda enciklike pape Lava XIV. *Magnifica Humanitas — Veličanstveno čovještvo* (2026.):

- **AI-prijevod** (GPT‑5.4), izrađen s **engleske** vatikanske verzije i objavljen na web-stranici (`index.html`), uz naknadnu ljudsku lekturu;
- **službeni prijevod** Hrvatske biskupske konferencije (Kršćanska sadašnjost, 2026.), prijevod Tihane Semijalac, teološka lektura Stjepana Balobana, rađen izravno s **talijanskoga izvornika**.

**Cilj nije popis grešaka** (za to služe `ANALIZA_PRIJEVODA_MH.md` i `ISPRAVIME_USPOREDBA_MH.md`), nego **studija o tome gdje i zašto AI-prijevod strukturno posustaje** kad se prevodi crkveni, tradicijski gusto utkan tekst. Primjeri su ilustrativni, ne iscrpni.

**Metoda.** Za svako sporno mjesto uspoređena su četiri sloja: talijanski izvornik (IT), engleska verzija koja je AI‑ju služila kao predložak (EN), AI-prijevod (AI) i službeni prijevod (SLUŽ). Izvori IT/EN uzeti su iz `assets/compare.json`, AI iz `index.html`, službeni iz priloženoga PDF-a.

**Važna ograda.** AI-tekst u `index.html` **već je jednom ljudski lektoriran** (git-commit *„ispravi prijevod i lekturu enciklike”*). Sve površinske nezgrapnosti iz ranije analize — `pounutarnjujućoj`, `suradnjivati`, `Odrjeći`, `razmotavati`, obrnuti smisao u §240, neujednačeno *AI/UI* — **danas su ispravljene**. To je za ovu studiju ključno: pogreške koje slijede **preživjele su ljudsku lekturu** jer ih lektura usmjerena na tečnost i pravopis u pravilu ne vidi. Upravo su te „duboke” pogreške pravi otisak ograničenja strojnoga prevođenja.

---

## Središnja teza

> **AI vjerno prevodi *tekst koji vidi*, ali ne prevodi *tekst koji tekst priziva*.**

Crkveni dokument nije samostalna jezična cjelina. On je čvor u mreži drugih tekstova: Biblije, koncilskih konstitucija, prethodnih enciklika, papinskih govora — od kojih svaki **već ima svoj ustaljeni hrvatski oblik**. Ljudski prevoditelj crkvenih tekstova refleksno *ne prevodi* citat iz Evanđelja ili iz *Gaudium et spes*, nego ga **prepisuje iz postojećega hrvatskog prijevoda**. AI toga sloja nije svjestan: on svaki navod prevodi iznova, „iz nule”, proizvodeći tečan, ali **apokrifan** hrvatski oblik svetopisamskih i učiteljskih riječi.

Tomu se pridružuje drugo strukturno ograničenje: AI je prevodio **preko engleskoga međujezika**, pa je naslijedio sve pomake i pogreške koje je engleski prijevod već unio u odnosu na talijanski izvornik.

Iz toga izvire pet razreda ograničenja.

---

## I. Međujezik: „prijevod prijevoda”

Enciklika je izvorno napisana **talijanski**. AI je prevodio s engleskoga. Engleski je već bio interpretacija izvornika, pa AI nije mogao vratiti ono čega u engleskom više nije bilo.

### 1. Izgubljen *incipit* — a s njim i naslov dokumenta

Enciklike se imenuju po **prvim riječima**. Talijanski §1 počinje sintagmom koja *jest* naslov:

| | tekst |
|---|---|
| IT | **La magnifica umanità** creata da Dio si trova oggi di fronte ad una scelta decisiva… |
| EN | **Humanity, created by God in all its grandeur**, is today facing a pivotal choice… |
| AI | **Čovječanstvo, stvoreno od Boga u svoj svojoj veličini**, danas je suočeno s presudnim izborom… |
| SLUŽ | **VELIČANSTVENO ČOVJEŠTVO** koje je stvorio Bog danas se nalazi pred odlučujućim izborom… |

Engleski je *„magnifica umanità”* razložio u opisnu konstrukciju (*„humanity … in all its grandeur”*), pa je AI dosljedno preveo tu konstrukciju — i **naslovna je sintagma nestala**. Službeni prijevod, radeći s talijanskoga, prepoznaje da prve riječi teksta moraju glasiti kao naslov: *Veličanstveno čovještvo*. Ovo nije stvar tečnosti; to je **gubitak identiteta dokumenta**.

### 2. Razbijena *inkluzija* (§1 ↔ §233 ↔ §245)

Papa istu sintagmu namjerno ponavlja pri kraju, obrubljujući cijelu encikliku:

| mjesto | IT | AI | SLUŽ |
|---|---|---|---|
| §1 | La **magnifica umanità** | u svoj svojoj **veličini** | **veličanstveno čovještvo** |
| §233 | una **magnifica umanità** che illumina… | **veličinu čovječanstva** koja rasvjetljuje… | **veličanstveno čovještvo**… koje rasvjetljuje |
| §245 | la bellezza di una **magnifica umanità** abitata da Dio | **veličini čovječanstva**, u kojemu je Bog nastanio prebivalište | ljepotu **veličanstvenoga čovještva** u kojemu prebiva Bog |

Službeni prijevod tri puta drži isti izraz i tako čuva teološku zagradu; AI-prijevod (jer je slijedio tri različite engleske formulacije: *grandeur of humanity / grandeur / grandeur*) tu zagradu **ne prepoznaje ni na jednom kraju**. Dodatno, u §245 talijanski govori o *ljepoti* (*bellezza*) — engleski je izbacio i pretvorio u *grandeur*, pa je i AI izgubio *ljepotu*.

### 3. Naslijeđena engleska pogreška (§241)

Najčišći dokaz „prijevoda prijevoda”:

| | tekst |
|---|---|
| IT | …ottiene il **permesso di partire**… *(dopuštenje da **krene / ode**)* |
| EN | …received **permission to return**… |
| AI | …primio **dopuštenje da se vrati**… |
| SLUŽ | …dobiva **dopuštenje za polazak**… |

Engleski je *partire* (poći, otputovati) pogrešno preveo kao *return* (vratiti se). AI je tu pogrešku **doslovno naslijedio**. Biblijski i povijesno to je netočno: Nehemija je rođen u progonstvu i od kralja traži dopuštenje da **pođe** u Jeruzalem (usp. Neh 2,5) — nikamo se ne „vraća”. Službeni prijevod, s talijanskoga, ima ispravno. AI ovdje nije mogao biti u pravu jer njegov predložak nije bio u pravu.

### 4. Antropološki spljošten sadržaj (§233)

| | tekst |
|---|---|
| IT | In Cristo comprendiamo che **l’uomo è chiamato a essere collaboratore** nell’opera della creazione |
| EN | In Christ, **we are called to cooperate** in the work of creation |
| AI | U Kristu **smo pozvani surađivati** u djelu stvaranja |
| SLUŽ | U Kristu **razumijemo da je čovjek pozvan biti suradnikom** u djelu stvaranja |

Engleski je sažeo „*razumijemo da je čovjek pozvan biti su-stvarateljem*” u „*pozvani smo surađivati*”. Tako je iščezla antropološka jezgra (*imago Dei*, čovjek kao su-stvaratelj) — a AI je slijedio engleski.

---

## II. Nepoznavanje „drugoga teksta” — intertekstualnost

Ovdje je razlika najveća i najspecifičnija za AI. Enciklika obilno navodi Bibliju, koncil, prethodne pape i papinske govore. Ljudski prevoditelj te navode **traži u postojećim hrvatskim izdanjima**; AI ih prevodi iznova.

### 5. Magnificat (Lk 1,46–55) — najizrazitiji primjer

Hvalospjev Marijin ima **ustaljen, molitveno uvriježen hrvatski oblik** koji svaki vjernik zna napamet. Službeni prijevod ga citira; AI ga sklada iznova:

| redak | SLUŽ (uvriježeni oblik) | AI (iznova preveden) |
|---|---|---|
| Lk 1,47 | i **klikće** duh njezin u Bogu | i njezin se duh **raduje** u Bogu |
| Lk 1,52 | **silne zbaci s prijestolja**, uzvisi neznatne | **zbaci moćnike**, uzvisi neznatne |
| Lk 1,53 | **gladne napuni dobrima, a bogate otpusti prazne** | napuni gladne dobrima i bogate **otpusti praznih ruku** |

AI-ova inačica je gramatički besprijekorna, ali **apokrifna**: „*raduje se*” umjesto „*klikće*”, „*moćnike*” umjesto „*silne*”, a nestala je i slika **prijestolja** (*s prijestolja*). U dokumentu koji nosi naslov izveden iz iste riječi (*Magnificat* ← *magnificat anima mea Dominum* ← *veliča duša moja*), gubitak kanonske dikcije Hvalospjeva nije sitnica.

### 6. Citat iz *Gaudium et spes* 22 (§1)

| | tekst |
|---|---|
| SLUŽ | »otajstvo čovjeka **stvarno postaje jasnim jedino** u otajstvu utjelovljene Riječi« |
| AI | „**samo** u otajstvu utjelovljene Riječi **doista razjašnjava** otajstvo čovjeka” |

Službeni reproducira **primljeni koncilski tekst** (hrvatski prijevod GS 22); AI proizvodi vjeran, ali novosloženi parafrazirani oblik. Za citat iz temeljne koncilske konstitucije to je razlika između navođenja i prepričavanja.

### 7. Ponovno prevedeni učiteljski navodi (§243, §244)

Zaključni odlomci nižu doslovne navode iz papinskih tekstova; svaki od njih ima izvor u bilješci i postojeći hrvatski oblik.

- **Benedikt XVI. (§243).** IT *„si schiera dalla parte degli **ultimi**”* → SLUŽ *„**staje na stranu posljednjih**”* → AI (preko eng. *„takes the part of the lowly”*) *„**uzima stranu poniznih**”*. Talijanski *ultimi* = *posljednji*; engleski ga je pomaknuo u *lowly*, pa je AI dobio *ponizni*. Uz to: SLUŽ *„skriven **iza privida** ljudskih zbivanja”* — AI *„skriven **pod neprozirnim kontekstom** ljudskih događaja”* (kalk *opaque context*).
- **Pavao VI. (§244).** IT *„l’inno più forte e **innovatore**”* → SLUŽ *„najsnažniji i **najnapredniji hvalospjev**”* → AI *„najsilniji i **najnoviji himan**”*. Ovdje su dvije pogreške: *innovatore* nije *najnoviji* (nego *inovativan/najnapredniji*), a *hvalospjev* je pravi hrvatski liturgijski naziv za Magnificat — *himan* je posuđenica koja registarno odudara.

Nijednu od ovih razlika stroj nije mogao ispraviti jer **nema pristup ciljanom korpusu** (hrvatskim izdanjima tih govora); on nije ni znao da citat *ima* svoj postojeći hrvatski oblik.

---

## III. Teološka terminologija — ustaljene formule

Socijalni nauk Crkve ima **zatvoren skup ustaljenih naziva**. Odstupanje od njih nije „drugi izbor riječi”, nego signal da autor nije unutar tradicije.

### 8. „Povlaštena opcija za siromašne” (§78)

| | tekst |
|---|---|
| IT | opzione preferenziale **per i poveri** |
| SLUŽ | povlaštenu opciju **za siromašne** |
| AI | povlaštenoj opciji **za siromahe** |

*„Opcija/opredjeljenje za siromašne”* je **terminus technicus** socijalnoga nauka. AI-jevo *„za siromahe”* (od *siromah*) razumljivo je, ali izlazi iz ustaljene formule. Suptilno, ali za teološki tekst prepoznatljivo.

> Napomena o preciznosti službenoga: talijanski razlikuje *opzione* i *cura preferenziale*, a službeni to dosljedno prevodi kao *opciju* odnosno *brigu za siromašne* — razina distinkcije koju AI ne održava.

### 9. *Čovještvo* nasuprot *čovječanstvu*

Službeni prijevod svjesno razlikuje dva registra: **čovještvo** (svečani, naslovni, „*magnifica umanità*”) i **čovječanstvo** (obični „*mankind*”). AI pretežno rabi samo *čovječanstvo* (u tekstu 64:11 u korist *čovječanstva*), pa svečani registar naslova ne provlači kroz dokument (v. primjere 1–2).

### 10. *Trojedini* nasuprot *trojstveni* (naslov)

| | tekst |
|---|---|
| SLUŽ | Ljudsko biće: slika **Trojedinoga** Boga |
| AI | Ljudska osoba: slika **trojstvenoga** Boga |

*Trojedini Bog* je ustaljeni hrvatski teološki naziv (Deus Trinus); *trojstveni* je opisna, rjeđa varijanta. Također: *„essere umano”* → SLUŽ *ljudsko biće*, AI *ljudska osoba* (pomak *biće → osoba*).

### 11. *Predšasnik* nasuprot *prethodnik* (§3)

Za papu koji govori o prethodniku na Petrovoj stolici crkveni registar traži **predšasnik** (kako ima službeni); AI-jev *prethodnik* je točan, ali neutralno-svjetovan.

---

## IV. Registar, idiom i anglizmi

Kalkovi iz engleskoga i „internacionalni” oblici razotkrivaju da tekst nije *mišljen* na hrvatskom.

| # | mjesto | AI | SLUŽ / bolje | komentar |
|---|---|---|---|---|
| 12 | §3 | *Rerum **N**ovarum* | *Rerum **n**ovarum* | engleska velika slova u latinskom naslovu (title-case) |
| 13 | §3 | živi ***corpus*** istine | živi **korpus** istine | nepreveden latinizam po engleskom uzoru |
| 14 | §1 | novu **Kulu babilonsku** | novu **Babilonsku kulu** | obrnut, neprirodan red riječi |
| 15 | §244 | **himan** | **hvalospjev** | posuđenica umjesto liturgijskoga naziva |
| 16 | §245 | Bog **nastanio svoje prebivalište** | u kojemu **prebiva** Bog | rečito-pleonastičan kalk *made his dwelling* |
| 17 | §245 | **tkaoci** nade | graditelji / tkalci nade | *tkaoci* je nestandardan oblik množine (uz to: SLUŽ svjesno bira *graditelji* zbog slike gradnje) |
| 18 | naslov | Prve **etape** Socijalnoga nauka | Prvi **koraci** socijalnog nauka | *etape* (⟵ *stages*) mj. *„primi passi” → koraci* |
| 19 | naslovi | **Socijalnoga** nauka (vel. slovo) | **socijalnog** nauka | sustavno englesko pisanje velikim slovom |

---

## V. „Tihi” semantički pomaci

Najopasnije su pogreške koje su savršeno tečne pa ne pobuđuju sumnju — a smisao je otklizio.

- **§243 — „ultimi” → „ponizni”** (v. primjer 7): *posljednji* (najmanji, izgubljeni) pretvoreni u *ponizne* (krepost) — teološki različite kategorije.
- **§245 — izgubljena *ljepota*** (v. primjer 2): *bellezza* → (eng.) *grandeur* → *veličina*.
- **§233 — čovjek kao su-stvaratelj → puko surađivanje** (v. primjer 4).

Zajedničko im je da su **prošle i englesku redakciju i hrvatsku lekturu** neopaženo, jer na razini rečenice „zvuče točno”.

---

## VI. Poštenja radi: gdje je AI jednako dobar ili bolji

Studija bi bila pristrana bez ovoga. AI-prijevod je **iznadprosječno tečan** i na dugim je dionicama ravnopravan službenomu; katkad i precizniji:

- **§241 — „parabola luminosa”.** AI: *„snažnu **prispodobu**”* (prispodoba = točan hrvatski naziv za parabolu); SLUŽ: *„svijetli **primjer**”* — službeni je ovdje izgubio *„prispodobu”*. Prednost AI-ju.
- **§242 — Otk 21,2.** Oba prijevoda konvergiraju gotovo doslovno (*„opremljen kao zaručnica nakićena za svoga muža”*).
- **Opća tečnost i ritam.** Duge argumentativne rečenice (npr. §218, §219) AI prenosi glatko i pravilno; „strojni” trag se na razini sintakse gotovo ne osjeti.

Zaključak nije da je AI-prijevod loš, nego da **njegove slabosti nisu ondje gdje ih očekujemo**: ne u gramatici, nego u tradiciji.

---

## Zašto se to događa — mehanizam

1. **Optimizacija lokalne vjernosti i tečnosti.** Model prevodi *dani* niz tokena što uvjerljivije; nema poticaja tražiti da neka rečenica *već postoji* na ciljnom jeziku.
2. **Nema dohvata ciljnoga korpusa (RAG).** Bez alata, model nema pristup hrvatskoj Bibliji, koncilskim tekstovima ni papinskim govorima; citat prevodi kao običan tekst.
3. **Zbrajanje pogrešaka preko međujezika.** Svaka nepreciznost engleskoga predloška ulazi u hrvatski bez mogućnosti provjere s izvornikom.
4. **Nema memorije na razini dokumenta.** Ponovljene sintagme (naslovna *magnifica umanità*), ustaljeni nazivi i kratice lako se raspu jer se svaki odlomak prevodi zasebno.
5. **Neosjetljivost na žanrovske konvencije.** *Incipit* kao naslov, svečani crkveni registar, liturgijska dikcija — pravila koja ljudski prevoditelj zna, a koja iz površine teksta nisu očitljiva.
6. **Lektura ne doseže tu razinu.** Lektor koji glača pravopis i tečnost neće posumnjati u tečno sročen Magnificat ni primijetiti da je *incipit* izgubio naslov — pa te pogreške **prežive**.

---

## Pouke i preporuke

Za buduće AI-prevođenje crkvenih (i općenito tradicijski gustih) tekstova:

1. **Prevoditi s izvornika, ne s međujezika.** Već je taj jedan korak uklonio primjere 1–4 i 7.
2. **Uvesti dohvat kanonskih izvora (RAG).** Automatski prepoznati i **umetnuti postojeći hrvatski oblik** svakoga biblijskog i učiteljskog navoda (Biblija KS, koncilski dokumenti, enciklike, papinski govori iz bilježaka).
3. **Termbaza / pojmovnik prije prevođenja.** Zaključati ustaljene nazive: *povlaštena opcija za siromašne, socijalni nauk Crkve, Trojedini Bog, čovještvo/čovječanstvo, UI*.
4. **Provjera dosljednosti na razini dokumenta** za ponovljene sintagme, naslove i kratice (npr. naslovna *magnifica umanità* na svim mjestima).
5. **Dvoprolazni postupak.** Prvi prolaz: prijevod. Drugi prolaz: *„poravnanje s tradicijom”* — usporedba svakoga navoda s kanonskim tekstom i provjera žanrovskih konvencija.
6. **Teološka lektura je nezamjenjiva.** Ostaje jedini pouzdan filtar za pogreške iz razreda II. i V., koje ni jezična lektura ni alati poput `ispravi.me` sustavno ne hvataju.

---

## Zaključak

Na razini rečenice AI-prijevod je zreo: tečan, gramatičan, često elegantan. Njegova ograničenja leže **jedan sloj dublje** — ondje gdje tekst prestaje biti samo jezik i postaje **dio predaje**. AI prevodi riječi; ne prevodi *pamćenje* zajednice koje te riječi nose. Izgubljeni *incipit*, apokrifni Magnificat, naslijeđena engleska pogreška i ponovno prevedeni koncilski citat nisu omaške u jeziku, nego **prekid u tradiciji** — a upravo je čuvanje te tradicije ono što crkveni prijevod čini crkvenim.
