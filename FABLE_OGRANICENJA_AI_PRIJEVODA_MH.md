# Ograničenja AI-prijevoda — kritička studija na primjeru enciklike *Magnifica Humanitas*

**Predmet.** Usporedba dvaju hrvatskih prijevoda enciklike pape Lava XIV. *Magnifica Humanitas — Veličanstveno čovještvo* (2026.):

- **AI-prijevod** (GPT‑5.4), izrađen s **engleske** vatikanske verzije, objavljen na web-stranici (`index.html`) i naknadno ljudski lektoriran;
- **službeni prijevod** Hrvatske biskupske konferencije (Kršćanska sadašnjost, Dokumenti 205, 2026.; prijevod Tihana Semijalac, teološka lektura Stjepan Baloban), rađen izravno s **talijanskoga izvornika** (*Lettera enciclica Magnifica humanitas sulla custodia della persona umana nel tempo dell'intelligenza artificiale*).

**Cilj.** Ovo nije errata (za to služe `ANALIZA_PRIJEVODA_MH.md` i `ISPRAVIME_USPOREDBA_MH.md`), nego **studija o tome gdje i zašto AI-prijevod strukturno posustaje** kad prevodi crkveni, tradicijski gusto utkan tekst — i što nam to govori o naravi strojnoga prevođenja.

**Metoda.** Za svako sporno mjesto uspoređena su četiri sloja: talijanski izvornik (**IT**), engleska verzija koja je AI‑ju bila predložak (**EN**), AI-prijevod (**AI**) i službeni prijevod (**SLUŽ**). IT/EN preuzeti su iz `assets/compare.json`, AI iz `index.html`, SLUŽ iz PDF-a službenoga izdanja. Uzorak pokriva cijeli dokument: uvod (§§1–14), povijest socijalnoga nauka (§§29–45), antropologiju (§§50–58), digitalnu moć i etiku UI (§§96–110), istinu i demokraciju (§§132), rad (§§152–158), rat i mir (§§190–224) te zaključni marijanski dio (§§233–245).

**Ključna metodološka ograda.** AI-tekst u `index.html` **već je prošao ljudsku lekturu** (git-povijest: *„ispravi prijevod i lekturu enciklike"*). Sve površinske mane iz ranije analize — *pounutarnjujućoj*, *suradnjivati*, *Odrjeći*, *razmotavati*, obrnuti smisao u §240, neujednačeno *AI/UI* — **danas su ispravljene**. To je za ovu studiju presudno: pogreške opisane u nastavku **preživjele su lekturu**, jer lektura usmjerena na pravopis i tečnost tu vrstu pogreške u načelu ne vidi. One su, dakle, *strukturni* otisak strojnoga prevođenja, a ne slučajni šum.

---

## Središnja teza

> **AI vjerno prevodi *tekst koji vidi*, ali ne prevodi *tekst koji tekst priziva*.**

Enciklika nije samostalna jezična cjelina nego čvor u mreži drugih tekstova — Biblije, koncilskih konstitucija, prethodnih enciklika, papinskih govora — od kojih svaki **već ima ustaljeni hrvatski oblik**. Ljudski crkveni prevoditelj citat iz Evanđelja ili *Gaudium et spes* refleksno **ne prevodi nego prepisuje** iz postojećega hrvatskog izdanja; naslove enciklika i teološke formule zna neovisno o predlošku i ispravlja predložak kad je predložak kriv. AI radi obratno: predložak mu je konačni autoritet, a svaki navod prevodi „iz nule" — tečno, gramatično i **apokrifno**.

Tomu se pridodaje drugo strukturno ograničenje: AI je prevodio **preko engleskoga međujezika**, pa je naslijedio svaki pomak i svaku pogrešku koju je engleski prijevod već unio prema talijanskom izvorniku — bez mogućnosti da ih uoči.

Iz toga izvire pet razreda ograničenja, s primjerima koji slijede.

---

## I. Međujezik: „prijevod prijevoda"

### 1. Izgubljen *incipit* — a s njim i naslov dokumenta

Enciklike se imenuju po prvim riječima. Talijanski §1 počinje sintagmom koja *jest* naslov:

| | tekst |
|---|---|
| IT | **La magnifica umanità** creata da Dio si trova oggi di fronte ad una scelta decisiva… |
| EN | **Humanity, created by God in all its grandeur**, is today facing a pivotal choice… |
| AI | **Čovječanstvo, stvoreno od Boga u svoj svojoj veličini**, danas je suočeno s presudnim izborom… |
| SLUŽ | **VELIČANSTVENO ČOVJEŠTVO** koje je stvorio Bog danas se nalazi pred odlučujućim izborom… |

Engleski je *„magnifica umanità"* razložio u opisnu konstrukciju, AI je dosljedno preveo tu konstrukciju — i **naslovna sintagma je nestala iz prve rečenice dokumenta koji se po njoj zove**. Službeni prijevod, radeći s izvornika, zna da prve riječi moraju glasiti kao naslov. To nije pitanje tečnosti nego **identiteta dokumenta**.

### 2. Razbijena *inkluzija* (§1 ↔ §233 ↔ §245)

Papa istu sintagmu namjerno ponavlja pri kraju, obrubljujući encikliku teološkom zagradom:

| mjesto | IT | AI | SLUŽ |
|---|---|---|---|
| §1 | la **magnifica umanità** | u svoj svojoj **veličini** | **veličanstveno čovještvo** |
| §233 | una **magnifica umanità** che illumina… | **veličinu čovječanstva** koja rasvjetljuje… | **veličanstveno čovještvo**… koje rasvjetljuje |
| §245 | la **bellezza** di una **magnifica umanità** abitata da Dio | **veličini čovječanstva**, u kojemu je Bog nastanio prebivalište | **ljepotu veličanstvenoga čovještva** u kojemu prebiva Bog |

Službeni triput drži isti izraz; AI (slijedeći tri različite engleske formulacije) zagradu **ne prepoznaje ni na jednom kraju**. U §245 usput je nestala i *ljepota* (*bellezza*) — izbacio ju je već engleski, pa je AI nije mogao vratiti.

### 3. Naslijeđen iskrivljen naslov enciklike (§31)

Engleska vatikanska verzija sadrži pogrešku u naslovu jedne od najpoznatijih socijalnih enciklika — i AI ju je vjerno prenio:

| | tekst |
|---|---|
| IT | L'Enciclica **Quadragesimo anno** di Pio XI… |
| EN | Pius XI's Encyclical **Quadragesima Anno** was published… |
| AI | Enciklika Pija XI. **Quadragesima Anno** objavljena je 1931.… |
| SLUŽ | Enciklika **Quadragesimo anno** Pija XI., objavljena… |

Naslov glasi *Quadragesimo anno* (ablativ: „u četrdesetoj godini"); *„Quadragesima Anno"* gramatički je nemoguć latinski. Ljudski prevoditelj koji poznaje socijalni nauk ispravio bi to automatski, **usprkos predlošku** — jer dokument zna neovisno o tekstu pred sobom. Za AI je predložak konačni autoritet.

### 4. Naslijeđena engleska pogreška u sadržaju (§241)

Isti mehanizam, na razini smisla:

| | tekst |
|---|---|
| IT | …ottiene il **permesso di partire**… *(dopuštenje da **pođe**)* |
| EN | …received **permission to return**… |
| AI | …primio **dopuštenje da se vrati**… |
| SLUŽ | …dobiva **dopuštenje za polazak**… |

Engleski je *partire* (poći) preveo kao *return* (vratiti se). Biblijski i povijesno netočno: Nehemija je **rođen u progonstvu** i od kralja traži dopuštenje da *pođe* u Jeruzalem (usp. Neh 2,5) — nema se kamo „vratiti". AI ovdje nije mogao biti u pravu jer njegov predložak nije bio u pravu.

### 5. Antropološki spljošten sadržaj (§233)

| | tekst |
|---|---|
| IT | In Cristo comprendiamo che **l'uomo è chiamato a essere collaboratore** nell'opera della creazione |
| EN | In Christ, **we are called to cooperate** in the work of creation |
| AI | U Kristu **smo pozvani surađivati** u djelu stvaranja |
| SLUŽ | U Kristu **razumijemo da je čovjek pozvan biti suradnikom** u djelu stvaranja |

Engleski je „razumijemo da je *čovjek* pozvan biti *suradnikom*" (antropološka izjava o čovjeku kao su-stvaratelju, jeka *imago Dei*) sažeo u „pozvani smo surađivati" (moralni apel). AI je vjerno slijedio — i izgubio jezgru.

---

## II. Nepoznavanje „drugoga teksta" — intertekstualnost

Ovdje je razlika između čovjeka i stroja najdublja i najspecifičnija.

### 6. Magnificat (Lk 1,46–55) — apokrifni hvalospjev

Marijin hvalospjev ima **ustaljen, molitveno uvriježen hrvatski oblik** koji vjernici znaju napamet (Večernja, krunica). Službeni ga prijevod citira; AI ga je iznova skladao:

| redak | SLUŽ (uvriježena dikcija) | AI (novosloženo) |
|---|---|---|
| Lk 1,47 | i **klikće** duh njezin u Bogu | i njezin se duh **raduje** u Bogu |
| Lk 1,52 | **silne zbaci s prijestolja**, uzvisi neznatne | **zbaci moćnike**, uzvisi neznatne |
| Lk 1,53 | **gladne napuni dobrima, a bogate otpusti prazne** | napuni gladne dobrima i bogate otpusti **praznih ruku** |

AI-ova inačica je gramatički besprijekorna — i upravo je zato opasna: „raduje se" umjesto „klikće", „moćnici" umjesto „silnih", nestala slika **prijestolja**. U dokumentu čiji je naslov izveden iz iste riječi (*Magnificat* ← *veliča duša moja Gospodina*), gubitak kanonske dikcije Hvalospjeva nije sitnica nego simptom.

### 7. Citat iz *Gaudium et spes* 22 (§1)

| | tekst |
|---|---|
| SLUŽ | »otajstvo čovjeka **stvarno postaje jasnim jedino** u otajstvu utjelovljene Riječi« |
| AI | „**samo** u otajstvu utjelovljene Riječi **doista razjašnjava** otajstvo čovjeka" |

Službeni reproducira **primljeni hrvatski koncilski tekst**; AI proizvodi vjernu parafrazu. Za navod iz temeljne konstitucije Drugoga vatikanskog koncila to je razlika između *navođenja* i *prepričavanja* — a čitatelj koji tekst poznaje odmah osjeti da „nešto nije na svom mjestu".

### 8. Ponovno prevedeni učiteljski navodi (§243–244)

Zaključni odlomci nižu doslovne citate s bilješkama — svaki ima postojeći hrvatski oblik:

- **Benedikt XVI. (§243).** IT *„si schiera dalla parte degli **ultimi**"* → SLUŽ *„staje na stranu **posljednjih**"* → AI (preko eng. *„takes the part of the **lowly**"*) *„uzima stranu **poniznih**"*. Talijanski *ultimi* = *posljednji* (najmanji, zadnji u redu); engleski ga je pomaknuo u *lowly*, pa je AI dobio *ponizne* — **kategorijalna zamjena društvenoga položaja krepošću**. Uz to: SLUŽ *„skriven iza **privida** ljudskih zbivanja"* — AI *„skriven pod **neprozirnim kontekstom** ljudskih događaja"* (kalk *opaque context*).
- **Pavao VI. (§244).** IT *„l'inno più forte e **innovatore**"* → SLUŽ *„najsnažniji i **najnapredniji hvalospjev**"* → AI *„najsilniji i **najnoviji himan**"*. Dvostruko: *innovatore* nije *najnoviji*; a *hvalospjev* je hrvatski liturgijski naziv za Magnificat — *himan* registarno odudara.

Stroj te razlike nije mogao izbjeći: **nije znao da citat već postoji na hrvatskom**, a kamoli gdje ga naći.

---

## III. Teološka terminologija — ustaljene formule

Socijalni nauk i dogmatika imaju zatvoren skup naziva; odstupanje nije „drugi izbor riječi" nego signal izvanjskosti tradiciji.

### 9. „Povlaštena opcija za siromašne" (§78)

IT *„opzione preferenziale **per i poveri**"* → SLUŽ *„povlaštenu opciju **za siromašne**"* → AI *„povlaštenoj opciji **za siromahe**"*. Formula glasi *za siromašne*; *siromasi* su izvan nje. Suptilno, ali u teološkom tekstu prepoznatljivo. (Službeni k tomu dosljedno razlikuje *opzione* ↔ *opciju* i *cura preferenziale* ↔ *povlaštenu brigu* — razina distinkcije koju AI ne održava.)

### 10. *Čovještvo* ↔ *čovječanstvo*

Službeni prijevod razlikuje dva registra: **čovještvo** (svečano-naslovni, *magnifica umanità*, i human**ost** kao kakvoća: *„braća i sestre u čovještvu"*) i **čovječanstvo** (kolektiv, *mankind*). AI pretežno rabi samo *čovječanstvo* (omjer u tekstu ~64:11), pa svečani registar naslova ne prolazi kroz dokument (v. primjere 1–2).

### 11. *Trojedini* ↔ *trojstveni* Bog

SLUŽ: *„Ljudsko biće: slika **Trojedinoga** Boga"*; AI: *„Ljudska osoba: slika **trojstvenoga** Boga"*. *Trojedini* je ustaljeni hrvatski teološki naziv (*Deus Trinus*); *trojstveni* je opisna, rubna varijanta. Usput i pomak *essere umano* → *ljudsko biće* (SLUŽ) prema *ljudska osoba* (AI).

### 12. *Predšasnik* ↔ *prethodnik* (§3)

Za papu koji govori o prethodniku na Petrovoj stolici crkveni registar traži **predšasnik** (SLUŽ); AI-jev *prethodnik* točan je, ali neutralno-svjetovan.

### 13. Franjina krilatica (§44)

IT *„guerra mondiale **a pezzi**"* → SLUŽ *„svjetskim **ratom u dijelovima**"* (ustaljeni hrvatski oblik te često citirane sintagme) → AI *„svjetskim ratom **vođenim u dijelovima**"* — opisno, mimo uvriježena oblika. Ista logika kao kod biblijskih citata: krilatice imaju svoj primljeni oblik.

---

## IV. Registar, idiom i anglizmi

Kalkovi i engleske konvencije odaju da tekst nije *mišljen* na hrvatskom.

| # | mjesto | AI | SLUŽ / bolje | komentar |
|---|---|---|---|---|
| 14 | §§3, 29–45 | *Rerum **N**ovarum, Mater et **M**agistra, Populorum **P**rogressio, Evangelii **G**audium, Fratelli **T**utti…* | *Rerum novarum, Mater et magistra…* | **sustavni** engleski title-case u latinskim naslovima; hrvatska (i vatikanska) norma: velikim slovom samo prva riječ |
| 15 | §3 | živi ***corpus*** istine | živi **korpus** istine | nepreveden latinizam po engleskom uzoru |
| 16 | §1 | novu **Kulu babilonsku** | novu **Babilonsku kulu** | obrnut, neprirodan red riječi |
| 17 | §244 | **himan** | **hvalospjev** | posuđenica umjesto liturgijskoga naziva |
| 18 | §245 | Bog **nastanio svoje prebivalište** | u kojemu **prebiva** Bog | pleonastičan kalk (*made his dwelling*) |
| 19 | §245 | **tkaoci** nade | graditelji / tkalci nade | nestandardna množina; SLUŽ bira *graditelje* u skladu sa slikom gradnje koja nosi encikliku |
| 20 | naslov | Prve **etape** Socijalnoga nauka | Prvi **koraci** socijalnog nauka | *etape* ⟵ eng. *stages*; IT *primi passi* = koraci |
| 21 | naslovi | **S**ocijalnoga nauka | **s**ocijalnog nauka | englesko veliko slovo u sintagmi koja se hrvatski piše malim |

---

## V. „Tihi" semantički pomaci — najopasniji razred

Pogreške koje su savršeno tečne, pa ne bude sumnju — a smisao je otklizio. Krunski primjer nije s ruba teksta, nego iz **antropološke jezgre enciklike**:

### 22. §50 — odlomak o *imago Dei*

| | tekst |
|---|---|
| IT | …uomo e donna sono creati **a immagine e somiglianza** del Dio trinitario (cfr Gen 1,26-27). **Costitutivamente fatta per la relazione**, ogni persona è pensata e voluta da Dio… |
| EN | …men and women are created in the **image and likeness** (cf. Gen 1:26-27) of the Triune God. **Created for relationship**, every human person is planned and willed by God… |
| AI | …da je čovjek „na sliku Božju" stvoren kao „muško i žensko" (usp. Post 1,26-27). **Stvoren na sliku trojstvenoga Boga**, svaka je ljudska osoba zamišljena i htjena od Boga… |
| SLUŽ | …da su muškarac i žena stvoreni… na sliku trojedinoga Boga (usp. Post 1,26-27). **U osnovi stvorena za odnos**, svaka je osoba zamišljena i željena od Boga… |

U jednom odlomku četiri kvara, **nijedan naslijeđen** — engleski je ovdje bio ispravan:

1. ispao je dvojac **„slika i sličnost"** (*immagine e somiglianza* — temeljni patristički par), premda ga i EN ima (*image and likeness*);
2. **nestala je rečenica o relacijskoj naravi osobe** (*Created for relationship* / *stvorena za odnos*) — umjesto nje AI je **ponovio** sintagmu o slici Božjoj iz prethodne rečenice; a upravo je relacijalnost poanta odlomka (osoba stvorena za zajedništvo);
3. viseći particip: *„**Stvoren** na sliku… **svaka je ljudska osoba**…"* (m. r. jd. prema ž. r.);
4. *„sa **stvorenjem**"* umjesto *„sa **stvorenim svijetom**"* (*creato/creation*).

Ovo pokazuje da tihi pomaci nisu samo posljedica međujezika: **model i sam ispušta i duplicira sadržaj** kad restrukturira rečenicu, a rezultat ostaje tečan i lektorski nevidljiv.

Ostali primjeri razreda: *ultimi* → *ponizni* (§243, v. primjer 8), izgubljena *bellezza* (§245, v. primjer 2), su-stvaratelj → surađivanje (§233, v. primjer 5).

---

## VI. Poštenja radi: gdje je AI jednako dobar ili bolji

Studija bi bila pristrana bez ovoga — i nalaz je jednoznačan: **na dugim argumentativnim dionicama AI je ravnopravan službenomu prijevodu.** Provjereni uzorci iz sredine dokumenta (§§52, 58, 96, 104, 152, 158, 190, 208 — dostojanstvo, digitalna moć, moralna ne-neutralnost UI, rad, rat) tečni su, točni i terminološki uredni (*opća namjena dobara, supsidijarnost, solidarnost* — sve ispravno). Mjestimice je AI i precizniji:

- **§241 — *parabola luminosa*.** AI: *„snažnu **prispodobu**"* (točan hrvatski naziv za parabolu); SLUŽ: *„svijetli **primjer**"* — službeni je tu izgubio *prispodobu*. Bod za AI.
- **§242 — Otk 21,2.** Oba prijevoda gotovo doslovno konvergiraju (*„opremljen kao zaručnica nakićena za svoga muža"*).

Zaključak nije da je AI-prijevod loš — nego da mu slabosti **nisu ondje gdje ih tražimo**. Nisu u gramatici ni u tečnosti; u **tradiciji su**.

---

## Zašto se to događa — mehanizam

1. **Optimizacija lokalne vjernosti.** Model prevodi *dani* niz što uvjerljivije; nema poticaja pitati se *postoji li* ta rečenica već na ciljnom jeziku.
2. **Nema dohvata ciljnoga korpusa.** Bez alata model ne može posegnuti za hrvatskom Biblijom, koncilskim tekstovima, prethodnim enciklikama — citat je za njega običan tekst.
3. **Predložak kao konačni autoritet.** Pogreške međujezika (*Quadragesima Anno*, *to return*) ulaze bez otpora; model ne „zna bolje" od teksta pred sobom — ili točnije, znanje koje ima ne aktivira protiv predloška.
4. **Nema memorije na razini dokumenta.** Ponovljene sintagme (naslovna *magnifica umanità*), registri i kratice raspu se jer se odlomci prevode lokalno.
5. **Restrukturiranje ispušta i duplicira.** Pri preslagivanju rečenice sadržaj zna ispasti ili se ponoviti (§50) — a rezultat ostaje gramatičan, pa ga ništa ne prijavljuje.
6. **Neosjetljivost na žanr.** *Incipit* kao naslov, inkluzija kao kompozicijsko sredstvo, liturgijska dikcija — konvencije koje ljudski prevoditelj zna, a iz površine teksta se ne vide.
7. **Lektura ne doseže tu razinu.** Jezična lektura (i alati poput `ispravi.me`) glača tečnost; tečno sročen apokrifni Magnificat za nju je besprijekoran. Zato ove pogreške **prežive** — što je i empirijski potvrđeno na ovom tekstu.

---

## Pouke i preporuke

Za buduće AI-prevođenje crkvenih (i općenito tradicijski gustih) tekstova:

1. **Prevoditi s izvornika, ne s međujezika.** Taj jedan korak uklanja primjere 1–5.
2. **Dohvat kanonskih izvora (RAG).** Prepoznati svaki biblijski i učiteljski navod te **umetnuti postojeći hrvatski oblik** (Biblija KS, koncilski dokumenti, enciklike, govori iz bilježaka).
3. **Termbaza prije prevođenja.** Zaključati: *povlaštena opcija za siromašne, socijalni nauk Crkve, Trojedini Bog, čovještvo/čovječanstvo, predšasnik, hvalospjev, rat u dijelovima*, pisanje latinskih naslova.
4. **Dokumentna provjera dosljednosti** ponovljenih sintagma, naslova, kratica (naslovna *magnifica umanità* na svim mjestima).
5. **Dvoprolazni postupak:** (1) prijevod → (2) *poravnanje s tradicijom* — svaki navod usporediti s kanonskim tekstom, provjeriti žanrovske konvencije.
6. **Poravnanje s izvornikom po odlomku** (IT ↔ HR) kao mehanička provjera da ništa nije ispalo ni duplicirano (§50).
7. **Teološka lektura je nezamjenjiva** — jedini pouzdan filtar za razrede II. i V., koje jezična lektura dokazano propušta.

---

## Zaključak

Na razini rečenice AI-prijevod je zreo: tečan, gramatičan, često elegantan — i na velikim dijelovima enciklike ravnopravan službenomu. Njegova ograničenja leže jedan sloj dublje, ondje gdje tekst prestaje biti samo jezik i postaje **dio predaje**. Izgubljeni *incipit*, apokrifni Magnificat, *Quadragesima Anno*, Nehemija koji se „vraća", ispala *sličnost* i *odnos* iz odlomka o slici Božjoj — to nisu omaške u jeziku nego **prekidi u tradiciji**. AI prevodi riječi; ne prevodi *pamćenje zajednice* koje te riječi nose. A upravo je čuvanje toga pamćenja ono što crkveni prijevod čini crkvenim — i ono zbog čega službeni prijevod, uza svu tehničku ravnopravnost AI-a, ostaje mjerodavan.
