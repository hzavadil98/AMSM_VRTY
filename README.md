# Group of Applied Mathematics &amp; Stochastics
**(Katedra matematiky FJFI ČVUT &amp; D4 Rázy a vlny v tělesech/ÚT AV ČR)** \
hledá AMSM talenty na zpracování dat a aplikace STROJOVÉHO UČENÍ

Vyhlašujeme Soutěž &#39;AMSM AI Drill Challange&#39;
O nejlepší AI klasifikaci otupení vrtáků \
Úkolem je klasifikace do 5 tříd tuposti vrtáku
z detekovaných signálů akustické emise (AE)

Popis na  webu [GAMS](https://gams.fjfi.cvut.cz/drill-challange)

#### Co je Akustická Emise
Akustická emise (AE) je jev, při kterém se do materiálu uvolňují elastické napěťové vlny o frekvencích v řádu až MHz, tedy daleko nad slyšitelnou částí frekvenčního spektra. Po dosažení povrchu tělesa lze tyto vlny měřit piezoelektrickými snímači a detekovat tak např. mikroskopický růst trhlin (únava materiálu), netěsnost tlakových nádob (jaderných či chemických reaktorů), tření v ložiscích a převodových ústrojích apod. Pokud má AE charakter příliš častých pulzů, které splývají v signál podobný spíše šumu, mluvíme o spojité AE. Jedním z příkladů vzniku ultrazvukových vln v materiálech jsou i procesy obrábění kovů nebo vrtání, což je případ této výzvy.

#### Měřící set-up (Ústav termomechaniky AV ČR, v.v.i., M. Chlada):
Měření bylo provedeno USB osciloskopem Handyscope HS6 DIFF, výrobce TiePie, za pomocí tří typů
snímačů AE: dva s korundovou keramickou styčnou plochou, jeden magnetický s poniklovanou
styčnou plochou a jeden s ocelovou styčnou plochou. Každý typ snímače má jinou frekvenční
charakteristiku neboli citlivost na různé frekvence obsažené ve snímaných akustických vlnách,
způsobenou svou konstrukcí. Vrtačkou Bosch, upevněnou ve stojanu pro zajištění konstantního
přítlaku a otáček, bylo vrtáno do ocelové desky o rozměrech 70 x 93 x 10 mm. Měřící aparatura
snímala se vzorkovací frekvencí 3,125 MHz na všech čtyřech vstupních kanálech.

#### RAW data (ÚT AVČR, v.v.i., M. Chlada):
Bylo provedeno 5 sad měření spojité AE, mezi kterými byl vrták uměle otupen za použití brusného kamene. Tupost vrtáku ovlivňuje charakter AE v důsledku odkrajování tenkých vrstev materiálu a třením styčných ploch. V každé sadě měření bylo vrtáno do děr 1 až 5 pro každou z 5 úrovní otupení vrtáku po dobu přibližně 5 sekund. Z každého signálu byla vyříznuta čtyřsekundová střední část souvislého vrtání na 4 kanálech odpovídajících 4 snímačům AE. Délka jednoho signálu je 12,5 milionu hodnot (vzorků).

#### Struktura dat signálů ke klasifikaci (KM FJFI, Jan Zavadil):
Náhodný výběr podúseků z každého signálu o délce 6000 vzorků - dostatečně dlouhé úseky pro zachycení charakteristiky signálu, zároveň dostatečně krátké pro rozumnou výpočetní dobu současných ML/AI algoritmů. Pro každou úroveň tuposti vrtáku ze signálu příslušejícího každé díře vybráno náhodně 500 podúseků. Celkem je tedy k dispozici pro každou z pěti úrovní otupení vrtáku 2500 výseků akustických signálů o délce 6000
vzorků, každý z nichž má 4 kanály příslušející čtyřem AE snímačům.

#### Úkol pro klasifikaci tupostí vrtáku:
90% signálů, tzn. 11250 výseků signálů, se známým původem, vybaveny ‚labely‘ označujícími stupeň tuposti 0 až 4 (0-zcela nový až 4-nejvíce otupený vrták). V souboru *VRTY_studen-pkl* je jak trénovací dataset s příslušnými labely tak evaluační dataset, jehož labely máte za úkol predikovat. Připnutý jupyter notebook na Google Colab je k dispozici pro načtení dat, případně i pro jejich zpracování.

#### Způsoby hodnocení kvality klasifikace: 
Ze zaslaného vektoru predikovaných tříd pro data z *eval_dataset* bude spočtena přesnost (accuracy) vaší predikce, podle které budou seřazeny výsledky. 


