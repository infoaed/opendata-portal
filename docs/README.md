# Avaandmete portaali mitmekeelne kasutajaliides

[Avaandmete portaal](https://opendata.riik.ee) põhineb Briti Ühendkuningriigi valitsuse [Data.gov.uk portaali](https://github.com/datagovuk/dgu-vagrant-puppet) tarkvaral, mis omakorda põhineb Open Knowledge Internationali [CKAN avaandmete halduse tarkvaral](http://ckan.org/) ja [Drupali sisuhaldustarkvaral](https://www.drupal.org/). Eesti avaandmete portaali mitmekeelne kasutajaliides on realiseeritud kasutades võimalust mööda sellele aluseks oleva [avatud lähtekoodiga tarkvara](https://www.mkm.ee/sites/default/files/tarkvara_raamistik.pdf) tõlkemooduleid ja nendele moodulitele aluseks olevaid tarkavaratõlke standardeid.

Kõik alustarkvara ja selle moodulite tõlkesüsteemid põhinevad vaba ja avatud lähtekoodiga tarkvara vallas _de facto_ standardi staatust omava [GNU _Gettext_](https://www.gnu.org/software/gettext/manual/html_node/Introduction.html) vahenditel. Nende kasutamist on jätkatud ning tõlgete haldus põhineb GNU _Gettext_ ökosüsteemis [sissetöötatud praktikatel](https://viki.pingviin.org/Tarkvara_t%C3%B5lkimine_(juhend)).

## CKAN

Kuigi portaali tuum põhineb CKANi avaandmete halduse tarkvaral, siiski ei kasuta ei ühendkuningriigi avaandmete portaal (edaspidi DGUK) ega meie avaandmete portaal märkimisväärselt selle tõlkesüsteemi, sest suurem jagu kasutajaliidesest on realiseeritud CKAN funktsionaalsuse ülekatetena _ckanext_-laiendmoodulite kujul ja Drupali sisuhalduses. Siiski genereeritakse ja hallatakse CKANil põhineva portaaliosa tõlkefaile [koodipuu CKANi harus](https://github.com/opendata-ee/ckan).

### Kasutajaliidese tõlked

Tõlkimist vajavad kasutajaliidese fraasid on süsteemi loogikat realiseerivas lähtekoodis ja dünaamilistes kujundusmallides. CKANi on sisse ehitatud nende tõlkimiseks vajalikud vahendid, kuid DGUK portaalis tõlget realiseeritud pole, mistõttu on CKANist päritud tõlkemoodulite töökord osaline, nt ei kasutata üldse CKANi süsteemseid JavaScripti funktsioone, mh [Jed-tõlkemoodulit](http://docs.ckan.org/en/ckan-2.2.3/frontend-development.html#i18n-jed).

> Kuna avaandmete portaalis on kasutusel DGUK tarkvara versioon 2014. aastast, mis põhineb [CKANi 2.2 seerial](https://docs.ckan.org/en/release-v2.2.3/), siis on nüüdseks on DGUK võtnud [CKANi eeskujul](http://docs.ckan.org/en/latest/contributing/frontend/templating.html) HTMLi mallide jaoks kasutusele Jinja2 raamistiku. See tähendab, et DGUK ja CKAN tarkvara uute versioonide kasutuselevõtmisel tuleb ka tõlkesüsteem uuele standardile üle kanda.
>
> Avaandmete portaali loomise ajal kasutas CKAN juba Jinja2 raamistikku, DGUK kasutas veel Genshi raamstikku, aga oli Jinja2 raamistikule üle minemas. 2017. aasta alguses hindavad DGUK arendajad oma portaali kasutajaliidest vananenuks ning pakuvad, et see uuendatakse poole aasta jooksul (info kirjavahetusest portaali arendajaga).
>
> Lisaks sellele on CKAN alustanud 2016. aasta suvel [üleminekut _Pylons_-raamistikult _Flask_-raamistikule](https://github.com/ckan/ckan/wiki/Flask-Migration-Roadmap), mis toob samuti kaasa mõningaid muutusi mallide esitamisel ja ilmselt ka tõlgete puhul.

Avaandmete portaali CKANil põhineva kasutajaliidese tõlgitavad fraasid on:

* [Pythoni lähtekoodis](http://docs.ckan.org/en/latest/contributing/string-i18n.html#internationalizing-strings-in-python-code), mis on CKANi peamine programmeerimiskeel ja on kasutusel läbivalt CKANis, kõigis selle moodulites ning dünaamilistes HTML-mallides. Tõlkefraasid on märgistatud _Gettext_-notatsiooniga ja tõlgitakse [Pylons-raamistiku _Gettext_-vahenditega](http://pylonsbook.com/en/1.1/internationalization-and-localization.html#extracting-messages-and-handling-translations), kuigi lähtekoodis leidub ka otsepöördumisi _Gettexti_ poole.
* [Genshi HTML-mallides](https://pythonhosted.org/Genshi/i18n.html), mis asuvad peamiselt [ckanext-dgu mallide kataloogides](https://github.com/opendata-ee/ckanext-dgu/tree/look_feel_est/ckanext/dgu/theme/templates), aga ka muude kasutusel olevate _ckanext_-moodulite alamkataloogides. Tõlkefraase märgistatakse ainult vajadusel, Genshi DOM-parser tuvastab suurema jao neist ise ja tõlke korraldab taas Pylons.
* [JavaScripti lähtekoodis](https://github.com/infoaed/shared_dguk_assets/commits/look_feel_est/src/js/odp-ee-i18n.js), mille tõlkimiseks on minimalismi põhimõttest lähtuvalt võetud kasutusele [Simple i18n for JavaScript Apps](https://github.com/roddeh/i18njs).

Täpsemad juhised tõlgete haldamiseks leiab [paigaldusjuhisest](../INSTALL.md#skripti--laadi--ja-keeleseadistuste-genereerimine).

### Andmestiku mitmekeelsus

CKAN võimaldab lisamoodulite abil hallata ka [mitmekeelset andmesisu](http://docs.ckan.org/en/latest/maintaining/multilingual.html), kuid kasutajaliidese tõlkimiseks osutus vajalikuks ainult märksõnastiku tõlgete moodul, mille abil realiseeritakse [Eurovoc sõnastiku](http://eurovoc.europa.eu/drupal/?q=et) automaattõlge inglise keelde. Märksõnastik on andmebaasis talletatud eestikeelsena ja tõlgitakse [CKANi enda vahenditega](http://docs.ckan.org/en/latest/api/index.html#ckan.logic.action.get.term_translation_show) jooksvalt inglise keelde. Samamoodi on teemade klassifikaatorid eestikeelsed ning neid hoitakse andmebaasis eesti keeles, aga [esitatakse vajadusel jooksvalt inglise keeles](https://github.com/infoaed/ckanext-dgu/blob/look_feel_est/ckanext/dgu/themes.json).

Täpsema kirjelduse märksõnastiku tõlgete halduse kohta leiab [paigaldusjuhisest](../INSTALL.md#ckani-eurovoc-märksõnastiku-ja-tõlgete-importimine).

### Otsingusüsteemi mitmekeelsus

DGUK portaalis on seadistatud andmehulkade otsing inglise keele baasil, CKAN võimaldab samas seadistada mitmekeelset ja/või eri keelte eripärasid arvestavat indekseerimist (nt sõnade algvormide eraldamine, liitsõnade osadeks jagamine jmt). Kasutajaliidese mitmekeelsuse jaoks on otsing seadistatud leidma märksõnu sõltumata valitud keelest.

### Paar erandit

JQuery kuupäevade lehitseja tõlge on realiseeritud [selle enda vahenditega](https://github.com/infoaed/ckanext-dgu/commit/613fd1d260bb1775bbc6cca3883fc468c02000aa#diff-9c32c9d3a13c765a55b4f50748a9a831) ja parandatud on üks [Genshi iseärasus](https://github.com/infoaed/ckan/commit/a5b00f8e400cb9c17a4bb6ed85be2450214e0722), mille tulemusena kasutajaliidese tühjad sõned asendati tõlkefaili päiseinfoga.

## Drupal

DGUK portaalis on võimalik kasutada Drupali sisuhaldusse sisseehitatud tõlkemooduleid, millele lisaks on avaandmete portaalis kasutusel hulk Drupali arendusmeeskonna poolt soovitatavaid [täiendavaid tõlkemooduleid](https://www.drupal.org/project/i18n).

Drupali tõlgitavad fraasid on laiali selle [lähtekoodis](http://cgit.drupalcode.org/drupal/tree/?h=7.x) (see on portaali paigalduse raames alla laaditud serveri kataloogi `/var/www/drupal/dgu`), laiendmoodulites (need on paigalduse raames alla laaditud serveri kataloogi `/var/www/drupal/dgu/profiles/dgu/modules/contrib`) ja DGUK täiendavates [_Features_-moodulites](https://github.com/opendata-ee/dgu_d7/tree/look_feel_est/modules/features) ja muudes kohandatud moodulites kataloogides [modules/custom](https://github.com/opendata-ee/dgu_d7/tree/look_feel_est/modules/custom) ja `/var/www/drupal/dgu/sites/all/modules`.

Tõlkimisel kasutatakse _Gettext_ PO-failide importimist/eksportimist, Drupali vastavat liidest ning protsessi hõlbustavaid lisamooduleid. JavaScripti tõlkimisel kasutatakse Drupali standardseid [JavaScript API vahendeid](https://www.drupal.org/docs/7/api/localization-api/translating-strings-in-javascript).

Drupali poolel on foorumite jaotised, valdkonnad ja sektorid aga vastavalt saidi tehnilisele algkeelele vaikimisi inglise keeles ja neid tõlgitakse _Gettext_-vahenditega dünaamiliselt eesti keelde, samas on ka seal klassifikaatorite näol tegemist saidi sisu ja mitte seadistustega.

Drupali tõlkimise täpsem kirjeldus on [paigaldusjuhises](../INSTALL.md#tõlgete-lisamine).

### Otsingusüsteemi mitmekeelsus

DGUK portaali Drupali osa rakenduste ja foorumiteemade otsing oli seadistatud inglise keele baasil. Kuna mitmekeelse otsingu ega saidi mitmekeelse sisu, sj märksõnade indekseerimise võimalusi pole loodud, siis on kasutajaliidese tõlkeprojekti raames seadistatud [elementaarne keelest sõltumatu otsing DGUK vaikimisi seadistustega](../INSTALL.md#dgu-search).

## CKANi täiendavad tõlked

DGUK portaali loogikas jagavad CKAN ja Drupal kujundusi, nendega seotud laadifaile ja kasutajaliides skripte [shared_dguk_assets](https://github.com/opendata-ee/shared_dguk_assets) harus. Kuna Drupali sisuhaldusel on sisseehitatud JavaScripti tõlkimise vahend ja jagatud skriptides olevad tõlked oli võimalik pagendada tagasi Drupali lähtekoodi, siis kasutatakse _i18njs_ JavaScripti tõlkimise moodulit ainult CKANi jaoks.

Täpsemalt kirjeldab jagatud _JavaScript_'i tõlgete haldamist [paigaldusjuhis](../INSTALL.md#skripti--laadi--ja-keeleseadistuste-genereerimine).

## Tehtud tööd

Algses avaandmete portaalis tõlkemooduleid [hoolimata nende olemasolust sisuliselt ei kasutatud](https://github.com/datagovuk/ckanext-dgu/issues/46), eri komponentides esinevad kasutajaliidese fraasid olid vastavalt vajadusele täidetud eestikeelse sisuga. [_Hardcoding_](https://en.wikipedia.org/wiki/Hard_coding#Overview)-võtetega tõlgitud kasutajaliidese puhul ei ole tõlked hallatavad, mh muudab tõlgitavate fraaside ning programmkoodi läbisegi esinemine kaelamurdvaks ka baastarkvara ja selle uuenduste haldamise ka juhul, kui portaal on kasutusel ühekeelsena.

![Tõlkemooduleid kasutamata on raske tagada järjekindlalt isegi portaali ükskeelsust, mitmekeelsusest rääkimata.](search_hardcoded.png "Näide eestikeelsest kasutajaliidesest enne tööde algust")

> Siiski pole selline _hardcoded_-viisil tõlkimine DGUK portaali Eesti kohanduse eripära, samasuguse _ad hoc_ lahenduse teed on läinud ka [Horvaatia avaandmete portaal](https://github.com/datagovhr/data.gov.hr) ja [Sloveenia avaandmete portaal](https://gitlab.xlab.si/MJU-POPS/ckanext-dgu). Teadaolevatest kohandustest pole ükski peale Eesti avaandmete portaali praegu korrektset tõlkemehhanismi seadistanud, nt [Iirimaa avandmete portaal](https://data.gov.ie/about) saab ootuspäraselt läbi tõlgeteta. Rohkematest käigus olevatest DGUK kohandustest selle arendajad 2017. aasta alguses teadlikud polnud ning pakkusid, et DGUK portaali aluseks võtmine võib olla mitte niivõrd tehniliselt läbikaalutud, vaid paljuski poliitiline otsus, võimalik et inspireeritud Briti Ühendkuningriigi Euroopa avaandmete lipulaeva rollist. Sloveenia portaali puhul oli otsus tõlkesüsteemist mööda minna seotud arendustööde tähtajaga (info kirjavahetusest portaali arendajaga).

Mitmekeelsuse tagamiseks tehti:

* Lähtekoodi tekstis tuvastati _ad hoc_ eesti tõlked ja eraldati need programmkoodist (vt seotud muudatused [`look_feel_est` võrdluspäringutes](../README.md#replace-hardcoded-estonian-with-gettexted-english)).
* Eestikeelsed tekstiõigud ja fraasid [tõlgiti inglise keelde ja toimetati](https://github.com/infoaed/opendata-portal/tree/master/translations).
* Portaali eri tarkvarakomponentiode jaoks valiti ja seadistati tõlkemoodulid, loodi mitmekeelsuse jaoks vajalikud kasutajaliidese komponendid (vt seotud muudatused [`i18n_logic` harus](https://github.com/infoaed/opendata-portal#language-switcher-gettext-generation-and-other-i18n-logic)).
* Eesti fraasid asendati lähtekoodis ingliskeelse tõlkega ja märgendati _Gettext_-vahendite abil tõlgitavaks, eesti vasted talletati ning teisendati _Gettext_-vormingusse taaskasutamiseks tõlkemoodulite abil.
* Seadistati tõlgitavaks portaali olemasolev sisu ja tõlgiti, kui võimalik, nt Eurovoc-märksõnastik ja klassifikaatorid.
* Kanti _Features_-moodulitesse üle Drupali portaali 2014. aastast alates laiv-keskkonnas tehtud muudatused ja veenduti, et tõlked on realiseeritud sisuhalduse lähtekoodis ning ülekantavad test- ja toodanguportaali vahel (vt muudatusi [`odp_ee_features` harus](https://github.com/infoaed/opendata-portal#merge-live-portal-changes-since-2014-into-drupal-features)).
* Muudatused viidi sisse ja dokumenteeriti [GitHubi arenduskeskkonna avalikes koodivaramutes](https://github.com/infoaed/opendata-portal) avatud lähtekoodiga tarkvaraarenduse põhimõtetest lähtuvalt.

## Hinnang portaali tarkvara seisundile

Kuna mitmekeelsuse tagamiseks tuli teha muudatusi kõigis portaali komponentides, siis andis selline arendustöö läbilõikelise pildi tarkvara üldisest olukorrast.

### Portaali arenduse üldised eesmärgid ja nende saavutamine

Arendaja vaatepunktist on silmatorkav, et portaalil puudub arendaja perspektiivi silmas pidav dokumentatsioon, mis kirjeldaks portaalis DGUK baastarkvara suhtes tehtud muudatusi ja põhjendaks mingil tasemel tehtud valikuid elik motivatsiooni nende taga (lähimad sellele on [portaali paigaldusjuhend](https://github.com/opendata-ee/dgu-vagrant-puppet/blob/togo/Avaandmete%20portaali%20paigaldusjuhend.odt) ja varundus- ning taasteplaan, aga need täitavad seda rolli ainult osaliselt, veidi on abi [GitHubi arendusvaramu](https://github.com/opendata-ee) kommentaaridest, aga ka neis puudub süstemaatilisus).

Kuigi portaali üldine dokumentatsioon tervikuna mõjub oma mõnedest ülerõhutatusest hoolimata eesmärgipäraselt ja läbimõeldult, siis arendustööde tegelik seis seda kogemust ei kinnita ja pigem jääb mulje, et algsest plaanist on hälbitud. Ilmselt on kohane diagnoos, et _Avaandmete portaali organisatsiooni kirjelduses_ koordinaatori, evangelisti, kasutajatoe ja spetsialisti kõrval ette nähtud süsteemiadministraatori ning tarkvaraarendaja rolli täitmata jätmine on kinnistanud portaali sellesse [esialgsesse seisu](https://en.wikipedia.org/wiki/Minimum_viable_product), millesse ta esimese arendustsükli järel jäi ning mis on ajapikku seda enam süvenenud kui on hajunud arendustöödes eri rollides osalenute mälestused tehtud töödest, valikutest ja väljakutsetest.

Portaali [avalike kasutusraportite](https://opendata.riik.ee/et/data/site-usage) märkamatu toppama jäämine 2015. aasta maikuusse on küll silmatorkav, aga siiski ainult sümptom. Tegelikult oleks portaali esimese arendustsükli lõppedes pidanud alustama järgmist tsüklit, mille jaoks oleks olnud vaja viia portaali muudatused taasesitatavasse seisu, kuid seda ei tehtud. Selle ebameeldivaks sümptomiks on ka tõlkemoodulite arendustööde toodanguportaali paigaldamise ajal ilmenud vajadus hakata [alates 2014. aastast Drupali laiv-süsteemis tehtud muudatusi _Feature_-moodulitesse üle kandma](https://github.com/infoaed/dgu_d7/compare/6fd3ffb00e93bb863448f524300904d63406bbc4...odp_ee_features). Arusaadavalt pole selliseid töid mõistlik lasta teha kolmandatel ja omaaegse arenduse üksikasjadest informeerimata arendajal kaks aastat pärast algse arendusprojekti lõppu ja ilma asjakohase dokumentatsioonita.

![Portaali Drupali poole põhisisu moodustavate `dgu_*` _Feature_-moodulite seisund mitmekeelsuse muudatuste rakendamise eel.](features_initial.png "DGU _Feature_-moodulite täiendused polnud pärast arendusi üle kantud lähtekoodi, kasutamata moodulid polnud välja lülitatud")

Esimese arendustsükli tulemusena loodud tarkvara täidab oma esialgse funktsiooni, arenduses toimunud pausi tõttu puudulikuks jäänud dokumentatsioonini saab praegu ilmselt jõuda ainult arendustöö käigus [jooksvalt kerkivate küsimuste](https://github.com/opendata-ee/opendata.riik.ee/issues/2) lahendamise dokumenteerimise teel.

Suurem väljakutse võib olla aga portaali töökindluse tagamine selle laiema kasutamise korral, kahtlustäratavaid märke esines ka arendustööde käigus, nt kippus toppama jääma Eurovoc märksõnade ja nende tõlgete [importimine CKAN API kaudu](..INSTALL.md#ckani-eurovoc-märksõnastiku-ja-tõlgete-importimine) ning konkreetne probleem leidurluse ja taaskäivituste kombinatsioonis, kuid mõistagi pole sellised lahendused kättesaadavad ega kohased laias kasutuses olevale süsteemile. Portaal vajaks põhifunktsionaalsuse täiendavat testimist [kõige elementaarsemal tasemel](https://github.com/opendata-ee/opendata.riik.ee/issues/3) ja kui täiemahulise testimisplaani elluviimine ei osutu otstarbekaks, siis võib olla alternatiiviks leida avaandmetest sisuliselt huvitatud partnereid, kellele pakkuda motivatsiooni beetatestija rolli enda peale võtmiseks.

Andmeteadus ja kitsamalt avaandmed on kiirelt arenev infoühiskonna eesliinil asuv valdkond ja selle uuendustega kaasas käimine eeldab pidevat asjaga tegelemist ka valdkonna jaoks vajalikku taristut tagava tarkvara tasemel. Avaandmete portaali aluseks võetud DGUK portaal on ise osana laiemast ökosüsteemist näide sellisest arendusmudelist, kus kasutatakse ära alussüsteemide avatud lähtekoodi, arhitektuuri modulaarsust ja orienteeritust taaskasutusele.

Avatud lähtekoodi ja [sellel põhineva tarkvaraarenduse](http://oss-watch.ac.uk/resources/softwaredevelopment) puhul on oluline teha koostööd arendajate kogukondadega, mis väljendub kõrgendatud nõudmistes lähtekoodi kvaliteedile, modulaarsuse ja taaskasutatavuse loogika järgimisele ja standarditele vastavusele. Käesolev arendusprojekt on tegelikult standardite ja [kogukonna vedajate soovituste vähese prioritiseerimise tulemus](https://github.com/datagovuk/ckanext-dgu/issues/46), sama võib ütelda ka Drupali arenduse ja CKANi koodi kohta, mis sobivad esimeste töötavate lahendustena — ja kliendile võib see esialgu tundudagi piisav —, kuid avaandmete ja avatud lähtekoodi ökosüsteemiga kasu saamiseks tuleb need viimistleda, kogukonda n-ö tagasi panustada ja arendus tugevalt tarkvara aluseks olevate projektide eesliiniga haakida.

### Mitmekeelsus ja portaali edasine arendus

Realiseeritud mitmekeelse kasutajaliidese lahendus on geneeriline ja vastab _Gettext_ vahendite kasutamise praktikatele, mistõttu pole tõlkelahendus ülemääraseks koormaks lähtekoodi või selle moodulite edasisele uuendamisele, liitmisele, asendamisele vmt.

Portaali tarkvara arendamisel või uute moodulite kasutuselevõtmisel on edaspidi üks tööde osa ingliskeelsete fraaside märgistamine tõlkimiseks, nende tõlkimine ja seejärel tõlkemoodulitele _Gettext_ formaadis kättesaadavaks tegemine. Enamasti on lõppkasutajale mõeldud avatud lähtekoodil põhinevad tarkvaramoodulid juba tõlkimiseks ette valmistatud ning vaja ainult _Gettext_-vahendeid kasutades ära teha eestikeelne tõlge.

Avaandmete portaali tõlkeprotsessi tehnilise kirjelduse koos selgitustega leiab [paigaldusjuhisest](../INSTALL.md#skripti--laadi--ja-keeleseadistuste-genereerimine) ja üldisema ülevaate avatud lähtekoodiga tarkvara tõlkimise korraldusest ning sellega kaasnevatest valikutest leiab [Pingviini vikist](https://viki.pingviin.org/Tarkvara_tõlkimine_(juhend)).

Kuna CKAN oli juba avandmete portaali arenduse algul loobunud Genshi mallide kasutamisest [Jinja2 mallide kasuks](http://docs.ckan.org/en/latest/contributing/frontend/templating.html) ja DGUK läks Jinja2 mallidele lõplikult üle [2016. aasta alguses](https://github.com/datagovuk/ckanext-dgu/issues/313), siis mistahes sellesse aega ulatuvate uuenduste kasutuselevõtmine ja/või tarkvara uuendamine võib kaasa tuua vajaduse tõlkesüsteemi mallide osas korrigeerida.

Portaalis on hulk sisu eesti keelde tõlkimata või ebaühtlase kvaliteediga, nt aluseks olevast CKANi tarkvarast on tõlgitud üksainus kasutajatele kuvatav veateade, tõlkimata on ka suurem jagu DGUK administraatorile mõeldud sisust, aga ka kasutajale veebis otseselt presenteerimata, kuid tegelikult ligipääsetavat sisu, nt kasutaja [isikliku konto ülevaatelehekülg](https://opendata.riik.ee/user) jmt.

Kuna mitmekeelsuse arendustööde ülesanne piirdus ingliskeelse tõlke tagamisega ja eestikeelse tõlke puhul silmatorkavamate ebakõlade parandamise ja selleks tarbeks mõnede tõlkimata fraaside lisamisega, siis täiendavate eestikeelsete tõlgete pakkumiseks on tarkvara ja moodulite lähtekoodis vaja tehtud tööde eeskujul täiendavalt puuduvaid fraase märgendada.

#### Mitmekeelne sisu

Kasutajaliidese mitmekeelsusest eraldiseisev küsimus on, kuidas hoida ja esitada portaalis mitmekeelset sisu. Esialgu seda otseselt plaanitud ega teostatud pole, kuid kuna Eurovoc-märksõnastik jt kategooriad on portaali sisu (sj on märksõnade loetelu kasutajate poolt jooksvalt täiendatav), siis nende tõlkimine on tegelikult sisu esitamine mitmes keeles ja on hetkel realiseeritud vastavalt kliendi soovile _ad hoc_ tõlkelahendusena.

Kui selgub, et avaandmete portaalis on vaja talletada ja esitada andmehulkade metaandmeid eri keeltes, siis tuleks mitmekeelse sisu lahendus üle vaadata ja korrektselt kasutusele võtta. Siin võib püüda kasutada CKANi sisemisi vahendeid, kuid näiteks [Kanada avaandmete portaali](http://open.canada.ca/data/en/dataset) puhul pole peetud seda piisavaks ning on [lahendatud mitmekeelsuse probleem teisel viisil](https://github.com/ckan/ckan/wiki/Multilingual-Datasets,-the-Government-of-Canada-approach).

#### Mitmekeelne otsing 

Kuna otsing on seotud saidi sisu indekseerimisega, siis on otsingu seadistamine mitmekeelse kasutajaliidese projektist väljapoole jääv ülesanne.

Hetkel on mindud mitmekeelse sisu (st tõlgitavate kategooriate) otsingu seadistamisega _ad hoc_ lahenduse teed, CKANi puhul on lisatud kategooriate indekseerimise koodi automaatselt ka [Eurovoc-sõnastiku kategooriate ja andmehulkade teemade tõlked](https://github.com/infoaed/ckanext-dgu/commit/162a419d5b451e01c7cfc279c10a26c65bed5b76#diff-89295958013b217b319131ab088f6b83) ja Drupali puhul on [paigaldatud mitmekeelse otsingu moodul ja see elementaartasemel seadistatud](../INSTALL.md#dgu-search).

Tegelikult vajaks sisu indekseerimine korrektset seadistamist eesti keele eripäradest lähtuvalt, et otsingus tuleks välja ka sõnade muutvormid, liitsõnad ja jäetaks kõrvale [üleliigsed sõnad](https://en.wikipedia.org/wiki/Stop_words), sest vastasel juhul võib jääda kasutajatele mulje, et otsing ei tööta. Kui portaalis saab olema rohkem mitmekeelset sisu, siis peaks otsingu seadistama ka baasfunktsionaalsuses mitmekeelseks.

Kuigi pragune lahendus n-ö ajab asja ära, siiski ei vasta siiski otsingu seadistamise heale praktikale ega ole kasutatav edasiarendustes.

### Portaali taristut puudutavad valikud

Avaandmete portaali edasiarenduste lähteühesandes arutatakse portaali tehnilise taristu küsimuste all ka DGUK ja CKAN kombinatsiooniga jätkamise mõttekust.

Tagantjärele võib ütelda, et DGUK valimine avaandmete portaali aluseks ei pruukinud olla kõige mõistlikum samm, eriti kui arvestada, et DGUK portaali CKANi täiendavast funktsionaalsusest kasutatakse ainult väikest osa, st peamiselt [rakenduste nimekirja](https://opendata.riik.ee/et/apps) ja [foorumite/kommenteerimise võimalust](https://opendata.riik.ee/et/forum), samal ajal kui DGUK portaal on Euroopa ühe eeskujulikumana realiseerinud hulga ühendkuningriigi spetsiifikale vajalikke täiendusi, mis väljenduvad mh portaali [andmete menüü võimalustes](https://data.gov.uk/data) ning tehnilises mõttes Eesti avaandmete portaali [väljalülitatud lisamoodulites](../INSTALL.md#drupali-feature-moodulid). Laiendmoodulite jaoks loodud raamistik on nende tegeliku mitte kasutamise korral lõppkokkuvõttes aga pigem koormaks.

Ilmselt kõige mõistlikum oleks olnud kasutada portaali alusena mitte DGUK portaali, vaid mõnda meile kultuurilisest ja tehnilisest vaatepunktist lähedasemat lahendust, mille arendajatega oleks saanud CKAN funktsionaalsuse kohandamisel koostööd teha. Üldiselt saavad avaandmete portaalid hakkama CKANi baasfunktsionaalsusega ja täiendavad seda enda vajadustest lähtuvalt, nt ühe eeskujuna võib vaadata Soome poole, mis on avaandmete valdkonnas seni Eestist edukam olnud, aga kellega me jagame siiski paljusid väljakutseid.

Soome avaandmete portaal kasutab [CKANi ja seda vahendavat Drupali sisuhaldust](https://github.com/yhteentoimivuuspalvelut), aga on realiseerinud selle enda vajadustest lähtuvalt soome, rootsi ja inglise keele kasutajaliidesega, Helsingi avaandmete portaal aga kasutab [CKANi ja Wordpressi sisuhaldust](http://ckan.org/case-studies/helsinki/). Seejuures erinevalt DGUK valikust suurem jagu CKAN kasutajaliidesest üle katta kasutavad mõlemad Soome portaalid vahetult ära CKANi vahendeid ning on baastarkvara soome keelde tõlkinud.

Kõigis Euroopa Liidu keeltes, sh eesti keeles on olemas [Euroopa Liidu avaandmete portaal](http://data.europa.eu/euodp/et/data/), mille lähtekoodi avaldamine koos kõigi tõlgetega on arendajal plaanis (info teabenõudest portaali haldajale, kahjuks eesti tõlget kasutataval kujul ei õnnestunud neilt pooleteise kuu jooksul kätte saada).

Lisaks on olemas CKANi funktsionalsust kopeeriv [Drupali sisuhalduse süsteemiga integreeritud avaandmete portaal DKAN](http://docs.getdkan.com/), mis erinevalt CKANi universalistlikust modulaarsest lähenemisest võimaldab andmeid ja täiendavat sisu hallata ning omavahel siduda otse Drupalis. See oleks arendaja aspektist mugav lahendus, kuid võib olla pikaajalisse kasutusse plaanitud riikliku portaali jaoks ebapiisav, sj töökindluse, laiendatavuse ja kogukonna eesmärkide jagamisest tuleneva kasu mõttes on CKAN koodile toetumine ilmselt parem strateegia.

DGUK portaali raamistikus jätkates oleks vajalik tihedam koostöö DGUK ja Sloveenia ning Horvaatia avaandmete portaalide arendajatega, kellega võiks püüda läbi rääkida arenduse eesmärke ja klapitada uuenduste ajakavasid. Esialgne suhtlus ühendkuningriigi ja Sloveenia portaalide arendajatega lubab arvata, et selline koostöö võiks olla viljakas, küll aga pole selge, kas nende ja meie huvides leidub piisav ühisosa, et arendusele koos eesmärke seada.

Sõltuvalt avaandmete valdkonda plaanitavate ressursside mahust ja poliitilistest eesmärkidest ning nendest tulenevatest arenguvajadustest on ilmselt mõttekas olemasoleva lahenduse juurest suunduda kas otse või samm-sammuliselt konkreetseid vajadusi paremini rahuldava lahenduse poole. Üldise põhimõttena oleks portaalile tehnilist taristut pakkuva avatud lähtekoodi ökosüsteemi parimal viisi ärakasutamiseks vaja haakida end avaandmete valdkonna arenduste eesliiniga, mis tähendab, et oleks kasuks kas tihedam sidumine ja kaasarääkimine DGUK arenduses või siis just suurem sõltumatus DGUK arendustest ning lähenemine selle baasiks olevale CKAN arendusele, et saaks vahetult võita mitmesaja arendajaga kogukonna eri pingutustest ning neid ka ise suunata. Mistahes valik eeldab aga tarkvaraarenduse senisest suuremat ja püsivamat prioritiseerimist.

DGUK raamistiku ja laienduste kasutamine ning vajadus nende kasutamise järele tuleks täpsemalt dokumenteerida, et saaks otsustada, kas on mõeldav samm-sammuline DGUK raamistikust loobumine ja arenduse tugevam haakimine nt Soome avaandmete portaali jt meile oludele sarnaste CKAN tuletiste arendusega.

Soomega koostöö tegemise kasuks räägib ka nende otsus hakata riiklikus andmevahetuses kasutama variatsiooni meie X-teest, millest avaandmete eksportimiseks võiks kasutada ühist tarkvara, aga võib-olla lõppkokkuvõttes taristut ennast. Ilmselt oleks sellel variandil oma häid külgi ka mainekujunduslikust aspektist ning avaandmete valdkonnas nägi koostööd Soomega ette ka _Avaandmete rohelise raamatu_ lisana vastu võetud valdkondlik tegevuskava.

### Kokkuvõtvad soovitused

Sõltuvalt sellest, kas soovitakse jätkata _Avaandmete portaali organisatsiooni kirjelduses_ ette nähtud tegevusi, peaks seal määratud rollidele leidma täitjad ning varustama need vajalike ressurssidega — või siis plaanitud tegevused ümber hindama. Kui plaanid jäävad üldjoontes samaks, siis:

* Tuleks mistahes edasiste arenduste tarvis dokumenteerida avaandmete portaali komponentide kasutamine (sh mitte kasutamine), kasutamise viisid ja eesmärgid ning markeerida erinevused CKAN ja DGUK raamistikest. 
* Sõltuvalt avaandmete valdkonna ja portaali arendamise ajakavast ja eesmärkidest tuleks otsustada, kas on otstarbekas jätkata DGUK portaali ühendkuningriigi konteksti jaoks kohandatud raamistiku kasutamist ning teha rohkem koostööd Sloveenia ja Horvaatia avaandmete portaalide arendajatega — või peaks arenduse viima lähemale DGUK tarkvara baasiks olevale CKANi ökosüsteemile ja jätkama arendust sünergias meile kultuuriliselt ja tehnilistelt vajadustelt lähemate Soome avaandmete portaalidega vm partneritega. 
* Tööde tulemusel realiseeritud mitmekeelsuse lahendus ei ole mistahes valikute korral arendustele ülemääraseks koormaks ja kui jätkata DGUK raamistikuga, siis tuleks selles tehtud täiendused liita võimalustmööda DGUK koodiga, et suurendada ühilduvust DGUK raamistikuga ning vähendada tööde hulka edaspidi portaali tarkvara uuendades.
* Uute arenduste korral tuleks pöörata tähelepanu baassüsteemide heade tavade, standardite ja arenduskogukonna liidrite/haldurite soovituste järgimisele ning tarkvara dokumenteerida arendaja vaatepunkist, vastasel juhul muutub baastarkvara turva- jm uuendustega kaasas käimine ja/või tarkvara mugandamine ülemääraselt töömahukaks.
* Portaali baasfunktsionaalsus vajab täiendavat testimist kas vastava eraldi projekti raames või siis piloteerides portaali eri funktsioonide kasutamist koostöös mõne huvitatud asutusega.
* Avaandmete valdkond vajab ilmselt süstemaatilist arendamist, st avaandmete portaali arendusi peaks toetama teavitustööga teabevaldajate juures, andmete esitamise parimate praktikate ja standardite juurutamisega, konkurssidega andmetele parimate rakenduste leidmiseks, andmeteaduse populariseerimisega üldhariduses jpm. Vaevalt portaali täiustamine ilma toetavate tegevusteta väga tulemuslik saab olla ja portaali arendust oleks kõige otstarbekam plaanida toetavate tegevustega sünkroonselt.