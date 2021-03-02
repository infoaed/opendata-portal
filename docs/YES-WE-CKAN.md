# Teabevärava sulgemine anno 2021

_Ehk lugu sellest, kuidas avaandmete edendamine käib riigi poolt pigem keerdtreppi pidi allapoole kuni selleni välja, et maailmapraktika kasutamise asemel viljeldakse lokaalseid veidrusi ning maetakse nendesse hunnikute viisi aega ja raha. Ja lõpuks pole meil isegi seda, mis oli alguses. Küsimuse all on raha (sada tuhhi siia, sada tuhhi sinna ja riigihanked, mida ei suudeta hallata), põhimõtted (avaandmete teabevärava avatus standardite, koosvõime ja lähtekoodi osas) ja elementaarne arusaamine, mida üldse tehakse (arusaamine muutub pidevalt lähtuvalt juhuslikest uitudest ja ei järgita ei kinnitatud plaane ega kokkuleppeid)._

Alustuseks väga lühike ülevaade [avaandmete](https://et.wikipedia.org/wiki/Avaandmed) teabeväravate ajaloost Eestis.

Eesti esimene, n-ö "katse"-teabevärav loodi 2011. aasta lõpus [piloodina majandusministeeriumi eestvedamisel](https://joinup.ec.europa.eu/sites/default/files/document/2014-04/Estonian%20Open%20Data%20Greenbook_0.pdf) ning põhines [CKAN-tarkvaral](README.md#ckan). Piloodi põhjal [hangiti 2014-2015 mõnevõrra kiirustades](https://riigihanked.riik.ee/rhr-web/#/procurement/609229) 39 100 euro eest üldkasutuseks mõeldud teabevärav. Selle ajakohastamiseks tellis ministeerium 2017-2018 mult omakorda 9200 euro eest teabevärava keelemoodulite tööleseadmise (pidin fiksima [kogu katki läinud modulaarsuse](README.md#hinnang-portaali-tarkvara-seisundile), tulemus on [seesama GitHubi repo siin](https://github.com/infoaed/opendata-portal)).

Sisuliselt samal ajal võitis [avaandmete valdkonna edendamise riigihanke](https://riigihanked.riik.ee/rhr-web/#/procurement/718616) ühing nimega [Open Knowledge Estonia](https://et.wikipedia.org/wiki/Open_Knowledge_Estonia), kus olin toona juhatuse liige, ning 2018. aasta sügisest lülitati hanke tulemusel ja [koostöös ministeeriumiga](https://foto.piletid.eu/konverents/events/2018-tarkeriik/Ott-Velsberg-ettekanne.pdf) teabevärav [väga väga väga segastel asjaoludel](https://www.facebook.com/groups/openestdata/permalink/1918100995150930) [JKAN-tarkvara](https://github.com/timwis/jkan) peale (see on pikem jutt, mida võin eraldi rääkida).

## CKANi uuesti hankimine...

Loetud kuude jooksul sai ministeerium ilmselt tehtud veast aru, sest juba märtsis 2020 kuulutati välja [järjekordne riigihange](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292) veel aasta eest olemas olnud CKAN-portaali uuesti hankimiseks eeldatava hinnaga 138 000 eurot:

> "Teabevärav on kavas välja arendada ja juurutada kasutades olemasolevat vabavaralist lahendust [CKAN](https://ckan.org/) ning kasutades maksimaalselt ära selles olemas olevaid funktsionaalsuseid. Lisafunktsionaalsused on kavas välja arendada paigaldatavate lisamoodulitena." [[1]](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/documents/source-document?group=B&documentOldId=13417356)

Suur oli minu üllatus, kui märgates 2. detsembril [teadet uue teabevärava valmimisest](https://www.facebook.com/groups/openestdata/permalink/2445342005760157/) ei paistnud CKAN-i kusagilt ja minu pärimise peale vastas ministeeriumis 2018. aasta hilissuvest avaandmete eest vastutav Ott Velsberg:

> "Avaandmete teabevärava puhul oleme tegelikult loobunud CKANi kasutamisest, seda ka jätkuarenduste puhul. Uuenenud teabevärav avalikustatakse juba peatselt, kõigi eelduste kohaselt järgmine nädal. Samas kindlasti ka jätkame teabevärava arendustega." [[2]](http://p6drad-teel.net/~p6der/ott-vastus.html)

## ...seda siiski saamata!

Lühidalt üteldes, riik oli juba 2015. aastal hankinud 39 100 euro eest CKAN-portaali, mis tal oli juba piloodina endal olemas. Mõte oli ilmselt teha piloodis kokku klopsitud asi korralikult, dokumenteerida jne. Võimalik, et see hange ei olnud hoolimta oma õilsast ideest kõige paremini õnnestunud, sest minult pidi tellima juba 2017. aastal parandusi ja [võin kinnitada](README.md#hinnang-portaali-tarkvara-seisundile), et algsel arendajal oli väga kiire või puudus kogemus avatud lähtekoodiga tarkvara arendusega, Drupali modulaarsusega jmt vajalikuga vmt, sj arendajale vajalikku dokumentatsiooni polnud üldse. Siiski vastas portaal [avaandmete rohelises raamatus](https://www.mkm.ee/sites/default/files/avaliku-teabe-masinloetava-avalikustamise-roheline-raamat-20141125_0.odt) eesmärgiks seatud esimestele sammudele, lihtsalt oleks vaja olnud sellega veel 3-4 kuud tööd teha.

Kui samuti Ott Velsbergi juhtimisel ette võetud umbes aastane JKAN-afäär oli lõppenud ja minu arvates igati õigustatult, siis CKANile varasemale kogemusele toetudes tagasi migreerumine olemasolevat koodi ja kogemust kasutades oleks olnud igati mõistlik. Sellest siiski hange ei räägi, vaid näib väljendavat otsust hankida 138 000 euro eest, st eelmisest korrast 3,5x kallimalt sisuliselt juba olemasoleva asja. See ei pea muidugi halb mõte olema, eriti kui sama asi tehakse algusest peale korralikult, dokumenteeritakse, juurutatakse, tehakse rohelises raamatus ette nähtud järgmised sammud, tagatakse teabeväravale tugi, hooldus ja uuendused jne.

Isegi varasema CKAN versiooni migreerimine on paras töö, eriti kui kavatsetakse selle raames vahetada välja ka sisuhalduse vmt. Aga kui töid teeb kogenud arendaja, siis tegelikult ei ole olemasoleva süsteemi kohandamine kuigi suur vaev, kuigi andmehalduse tarkara on veidi spetsiifiline ja igas ettevõttes pole ehk vajalikke oskusi kombineerivaid spetsialiste. Aga arvestades juba olemasolevat ja kogemust, oleks saanud siiski arendused ära teha sama hinnaga, mis eelmisel korral või natuke kallimalt, aga juba 2x sama hind tundub tõsiselt ülepakutud.

Kui tellitakse pärast ebaselget puterdamist hirmkallilt midagi, mis on juba olemas, aga siis ei saada sedagi — see paneb vist kulmu kergitama? Otsustasin asja uurida.

## Miks algsest hankest loobuti?

Palusin Otilt selgitust, mis kaalutlustel on riigihankes agselt nõutud CKAN-tarkvarast loobutud, mis on alternatiivi spetsifikatsioon ja kuidas põhjendatakse selle eelistamist. Hanke aluseks olnud [arendustööde tehnilises kirjelduses](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/documents/source-document?group=B&documentOldId=13417356) on nimelt ühemõtteliselt kirjas, et hangitakse CKAN-tarkvaral põhinev lahendus (tsitaat ülal), pakkujatele korraldatud [infotunni protokoll](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/communication/message/505231) ja [selle audiosalvestus](https://zoom.us/rec/share/5NQqE7vTx1pIG4not3qDGY8eD635eaa81XUZ-fcImkYxQjNgvRbVdOsVmJKX1EQq) ([5 min lühiversioon](https://soundcloud.com/ornoobikkuhutottadsa/ott-infotund)) kinnitavad, et on "nõutud kasutada" just CKAN-i andmete haldamise süsteemi (DMS), aga sisuhalduse funktsioonide (CMS) realiseerimisel on valik vaba, kuid on "rangelt soovituslik" kasutada laialt levinud, aktiivse toe ja hea ühilduvusega süsteeme (sj mainitakse võimalike lahendustena Wordpressi ja Drupalit ning suhtluses ka React esitluskihti).

Sain nädal hiljem pärast omapoolset uut meeldetuletust lõpuks telefonikõne, kus Ott väitis, et CKAN-ist loobuti, kuna see ei olevat arendaja väitel ühildunud Python 3 versiooniga (tegelikult arendusversioonis [tugi olemas jaanuarist 2020](https://github.com/ckan/ckan/issues/4801), st lepingu sõlmimise ajaks juba 5 kuud, ametlikult pakendatud [augustis](https://github.com/ckan/ckan/releases/tag/ckan-2.9.0)), selle jõudlus ei vastavat nõudmistele (aga vastab [UK](https://data.gov.uk/), [USA](https://www.data.gov/), [Kanada](https://open.canada.ca/en/open-data) jpt omadele), selle arendus oli toppama jäänud ja muud riigid olid sellest loobumas või loobunud (nt USA pani uue CKAN-portaali värskelt laivi [veebruaris 2021](https://www.infodocket.com/2021/02/06/new-version-of-the-data-gov-catalog-goes-live/)) ja kokkuleppel hanke võitjaga otsustati kirjutada kogu DMS-i nullist (aga kui olemasoleva vabavara kasutuselevõtmine ja uue eritarkvara nullist kirjutamine maksavad silma pilgutamata sama palju, siis on kuskil midagi **põhimõtteliselt väga valesti**, eks).

## Väidetavalt kõike seletav "detailanalüüs"

Põhjendused hanke aluspõhimõtete muutmisele pidid Oti sõnul olema kirjas "detailanalüüsis", mis olevat hanke tehnilise kirjelduse osa ja see pidi olema üleval hankedokumentide hulgas. Kuna jutt oli enam kui segane ja ma ei soovinud telefonis vaidlema hakata, siis palusin Otil selle mulle meilile saata, et saaksin põhjendustega tutvuda ja veenduda, et hangitakse seda, mida plaaniti. Kuna dokumenti järgmiseks päevaks ei saabunud, siis tegin selle saamiseks teabenõude, millele sain 22. detsembril eitava vastuse: kuna hange polevat lõppenud, siis on see dokument seni sisekasutuseks, antakse üle hanke lõppemisel 2023. aastal ja mul ega avalikkusel pole võimalik põhjendustega tutvuda.

Sellega minu erivõimed dokumentide ja teabevärava viimaste keerdkäikudega tutvumiseks piirdusid. Delegeerisin hanke veidruste ja vastustest hoidumisega tegelemise [rahandusministeeriumile](https://www.rahandusministeerium.ee/et/eesmargidtegevused/riigihangete-poliitika/jarelevalve), kes vastas mulle 18. jaanuaril, et [kuna hankeleping on juba sõlmitud, siis ei saa enam järelevalvet alustada]([3](http://p6drad-teel.net/~p6der/avaandmedte-portaal-2021.pdf)), aga nad siiski uurisid veidi toimuvat ning Ott vastas neile selgituseks, refereerides tagantjärgi korrigeerivalt iseennast korraldatud koosoleku audiosalvestisest:

> "Salvestusest selgub, et hankijal ei ole kokkulepet CKANiga ja et koosoleku
toimumise hetkel olemasoleva teabe alusel kasutab CKAN platvormi Euroopa avaandmete portaal, UK,
Kanada jt valitsused sh USA data.gov. Kui pakkuja eelistab kasutada DMSi (andmete haldamise süsteem),
siis on hankija soovitanud kasutada CKAN platvormi. Hankija ütles infotunnis, et tal ei ole eelistusi ega
piiranguid missugust platvormi peaks pakkuja soovima kasutada, sest pakkujal on valiku vabadus." [[3]](http://p6drad-teel.net/~p6der/avaandmedte-portaal-2021.pdf)

Väide sellest, et hankijal pole eelistusi ega piiranguid on puhas vale. Vale on see, et andmete haldamise süsteemi kasutamine oli tinglik. Sellest annab tunnistust viidatud infotunni raames aset leidnud suhtlus ja infotunni protokoll.

Kuulates üle [audiosalvestist](https://soundcloud.com/ornoobikkuhutottadsa/ott-infotund) (see on 5 min ekstrakt, kuula ise!), on seal korduvalt osutatud CKANile kui soovitud ja välja käidud DMS-ile ehk andmehalduse süsteemile, seejärel uurib küsija, kas "CKAN on mõeldud peamiselt andmete enda jaoks", aga portaali sisuhaldus võib olla ükskõik, mis CMS-i peal... Selle peale Ott esmalt vastab, et "ei, me plaaniksime kasutada ikkagi sedasama CKANi, aga ta on sisuliselt ikkagi andmete jaoks", mille peale küsitakse üle, et kuna CKANi enda lehel on toodud näidetena CKAN koos Drupaliga ja/või Wordpressiga, siis kas CMS ei võiks ikkagi olla ükskõik milline. Sellega on Ott "täiesti nõus".

Selguse mõttes palutakse veelkord kinnitada, et "CKAN on andmete poole peal, aga CMSi osas on käed vabad", mille peale kinnitab Ott taas, et "CKANi poole pealt on andmed", aga siis täpsustatakse, et CMSi puhul on eelistatud üldlevinud Wordpress või Drupal, et poleks "imeplatvorm", millega tekib pärast peavalu. Seda soovitatakse osaleja poolt hankesse selgelt sisse kirjutada, korraldajad kinnitavad, et protokolli saab see info sisse.

Kinnitatakse veelkord üle, et CMS pole ette antud rangelt, et valikuvabadus peab olema ja see oligi nii plaanitud. Audiosalvestise lõpetuseks tänab Ott osalejaid, et "CMSi pool on nüüd üle käidud", sest nende endi jaoks oli ka ebaselge see.

Ehk eelistusi (Dupal, Wordpress) ja piiranguid (mõni levinum, toega ja ühilduv) on hankijal CMSi osas ja DMSi osas on kindlas kõneviisis plaan kasutada CKANi, mida ei vaidlustata kordagi ning ka kogu infotunni kokkuvõttes üteldakse, et täpustatud sai CMSi küsimust.

Nagu kohe näeme, ütleb täpselt sama ka infotunni kokkuvõtteks lubatud protokoll.

## Mõistlik valdkonna spetsialist

Rahandusministeeriumi vastuses üteldakse väga ilusti, et "riigihanke alusdokumentide tingimusi kui avalikkusele suunatud tahteavaldust tuleb tõlgendada nii nagu **mõistlik isik** seda tahteavaldust mõistma pidi" ja "sealjuures lähtub mõistliku isiku arusaama sisustamine sellest, kuidas saavad hanketingimustest aru hanke esemega seonduva **valdkonna spetsialistid**". Infotunnis kuulamisel selgus, et hanke esmega seotud valdkonna spetsialistid said dokumentatsioonist aru ja palusid seda ka kinnitada, et DMS on rangelt CKAN ja CMS on vabalt valitav, aga eelistatud on levinumad nagu Drupal või Wordpress.

Niimoodi kinnitab mõistlike valdkonna spetsialistide soovil ja nende jaoks ka infotunni protokoll:

> "Tehnilised nõuded (kasutatavate tehnoloogiate valik peab olema põhjendatud, rangelt soovituslik on valida levinud platvorm, millel on community tugi, mis ühildub süsteemidega ning mille kvaliteedis saab kindel olla):
>  
> 1. CKAN – nõutud kasutada antud DMS’i (andmete haldamise süsteemi).
> 2. Drupal, WordPress – võib kasutada vabaltvalitud laialt levinud CMSi (sisuhaldussüsteemi).
>  
> Riigil ei ole CKANiga otseseid kokkuleppeid, kuid kuna CKAN on kasutusel ka teiste riikide avaandmete portaalides, siis võib eeldada, et tegu on hea koostööpartneriga, jättes kõrvale nende veebilehe väikese aktiivsuse." [[4]](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/communication/message/505231)

Kui vaadata seda protokolli, siis CKANi on "nõutud kasutada" DMSi ehk andmehalduse süsteemina. Mitte ühtegi reservatsiooni. Drupal või Wordpress on eelistatud CMSi ehk sisuhalduse rollis (aga valik on vaba, kuid "rangelt soovituslik" on levinud, toega ja ühilduvusega tehnoloogia). Protokoll kajastab infotunni audiosalvestut igati täpselt ja võib olla kinde, et CKANist loobumine on leidnud aset *pärast* hankelepingu sõlmimist nagu Ott mulle telefonis ütles, aga mida ta miskipärast rahandusministeeriumile ütelda ei tahtnud.

Seega on Ott vastuses rahandusministeeriumile varasemat väidet muutnud. Ta kinnitab, et infotunnis sai üteldud tingivalt, et "**kui** pakkuja eelistab kasutada DMSi, **siis** hankija on soovitanud kasutada CKAN platvormi". See pole aga tõsi, sest kõigis materjalides on CKAN kui andmehalduse süsteem ühemõtteliselt nõutud ja pole ühtegi kommunikatsioonikildugi sellest, et võiks kasutada midagi muud. Seda "kui"-d CKANi puhul ei kommunikeeri ega vihja sellele ainuski saadaolev dokument.

Isegi kui tagantjärele võib olla võimalik dokumendid niimoodi sättida, et CKANist loobumine pole juriidiliselt lubamatu, siis kindlasti on olnud suurem osa kommunikatsiooni hanke tutvustamisel eksitav. Ma olen üpris kindel, et CKANi asemel millegi muu kasutamine ei tulnud hanke korraldamise ajal pähe ühelegi mõistlikule valdkonna spetsialistile korrakski. Milleks siis need meelemuutused Oti poolt?

Aga isegi kui CKANi asemel kasutada midagi muud ja [juriidiliselt on kõik korrektne](https://et.wikipedia.org/wiki/Jokk), siis peaks see ilmselt vastama samadele nõudmistele, millele CKAN, mida läbivalt on esitatud näitena sellest, mida soovitakse. Vaaatame seda siis veidi täpsemalt ja nagu rahandusministeerium soovitab — mõistliku spetsialisti pilguga.

## Millest me ilma jääme?

Paneme tähele, et kuigi CMSi n-ö brändi valik oli vaba, siis olid selle juures kasutatavale tehnoloogiale "rangelt soovituslikud" nõudmised ja näitlikud soovitused, millega kindla peale minevad näited olid Drupal ning Wordpress. Kuigi DMSi valik polnud vaba ja CKAN on see DMS, mida infotunni ja selle protokolli järgi oli "nõutud kasutada", siis isegi kui juriidiliselt ei maksa infotunnis üteldu midagi ja võib väita, et CKAN oli ainult näide, siis seda näidet rõhutati tunduvalt tugevamini kui CMSi näiteid ja "rangelt soovituslikke" nõudeid. Ehk tuleb eeldada, et kui tellitakse teabevärav mõne muu DMSi põhjal kui CKAN, siis vastab see mitte ainult "rangelt soovituslikult", vaid lausa "rangelt nõutult" kõigile neile omadustele, mida on hankedokumentides CKANile omistatud.

Korjasin hankedokumentidest välja järgnevad nõudmised DMSile, millele peaks siis CKANi alternatiiv vastama (jätkuvalt eeldades, et infotunnis üteldud "nõutud kasutada" on võimalik lihtsalt niisama kõrvale jätta):

* Vaba litsentsiga avatud lähtekood ❌
* Arendajate rahvusvaheline ja aktiivne kogukond ❌
* Modulaarsus ja laiendatavus ❌
* Ühilduvus, vastavus kvaliteedi jm standarditele ❓
* Metaandmete esitamise kvaliteet ([DCAT](https://en.wikipedia.org/wiki/Data_Catalog_Vocabulary)) ❓
* Kasutajaliidese ajakohasus ja nõuetele vastavus ❓
* Tarkvara koormustaluvus ❓
* Kvaliteetne otsingusüsteem ❓
* Protsesside automatiseerimise võimalused ❓
* Mitmekeelsuse tugi ✅

Kõigepealt on selge, et kui CMSi osas oli nõutud laialt levinud süsteem, aktiivse kogukonna toe ja hea ühilduvusega, siis DMSi rätpsepatööna tellimisel need omadused pole garanteeritud või kaovad peaaegu kindlasti. Ometi on just DMS konkreetse süsteemi peamine osa ja selle suhtes esitati ka mõistetavalt rangeid nõudmisi. Tellides nullist rätsepatöö on need nõudmised lahjenenud aga madalamale tasemele kui CMSi puhul. Miks lahjendati pärast hankelepingu sõlmimist nõudmised nii madalale?

Võib eeldada, et hankedokumentide koostamisel ei osalenud üksainus inimene, vaid need vaadati läbi ning kinnitati. CKAN pole seejuures mingi kultusobjekt nagu kunagi [iPhone](https://en.wikipedia.org/wiki/IPhone) või vabavara maksimalistide jaoks [Gentoo Linux](https://en.wikipedia.org/wiki/Gentoo_Linux). CKAN on valdkonnas suur- ja väikeriikide valitsuste poolt tunnustatud standard, seda kasutab mh ülal mainitud suurriikidele ka põhjanaaber [Soome](https://www.avoindata.fi/) ning selle on omal ajal algatanud [Open Knowledge](https://en.wikipedia.org/wiki/CKAN) vabavaralise lahendusena ning see täidab oma rolli edukalt.

On selge, et kui tellida rätsepatööne DMS kui vägagi spetsiifiline tükk tarkvara ettevõttelt, kellel puudub valdkonnas koogemus ja kes keeldub ebapädevate põhjendustega (Pythoni toe puudumine, aredus seiskunud vmt) kasutamast tunnustatud ja hankes nõutud tarkvara, siis pole selge, kas võib oodata neilt tulemust, mis vastab kvaliteedi, ühilduvuse, koosvõime jmt standarditele. Kindel on aga, et kui tellida rätsepatöö, siis on kõrge [tootjaluku](https://en.wikipedia.org/wiki/Vendor_lock-in) oht, st tulevikus täienduste tellimisel on vähemasti eelisseisus kui mitte monopoolses seisus see ettevõte, kes tegi teabevärava algversiooni.

Kui hankedokumentides kinnitati, et plaan on realiseerida teabevärav CKANi ja laiendusmoodulite abil, siis rätsepatööna tellitaval DMSil pole ühtegi laiendusmoodulit, sest saadakse üks monoliitne tarkvara. Võib spekuleerida, kas konkreetse rätsepatöö lähtekood lõpuks avaldatakse, aga koodi litsentsi leheküljel praegu ei tooda ja paljude projektide puhul, kus algusest peale ei töötata avatud lähtekoodiga jääb kood ka hiljem avaldatamata isegi sõltumata hankenõuetest (halva praktika musternäide Eestist on [Volis](https://www.volis.ee/gvolis/?kid=14833)).

Mis on aga kindel, kui tundmatu Eesti ettevõte ei ole just loonud nii suurepärast tarkvara, et selle võtavad kasutusele suured avaandmete kogukonnad üle maailma, siis ei teki sellele aktiivset arendajate communityt, mida hankedokumendid soovivad. Või on tegu olukorraga, kus riik tundis ära suurepärase arendaja ning investeeris sellesse, et loodaks rahvusvaheliselt konkurentsivõimeline alternatiiv CKANile ja selle võtavad kasutusele nii UK, USA kui Soome?

Arvestades, et 2018. aasta sügisel toimus Ott Velsbergi juhtimisel põhjendamata üleminek JKANile, siis tundub pigem usutav, et nüüdne ebaõnnestunud naasmine valdkonnas standardiks olnud CKANi juurde kujuneb sarnaseks läbikukkumiseks. Või miks peaks uskuma, et kui seni pole suudetud eksootiliste ja põhjendamata valikutega asjad hästi käima saada, siis järjekordne kõrvalekalle headest praktikatest viib tulemusele?

## Viited

[1] [Arendustööde esimese etapi tehniline kirjeldus](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/documents/source-document?group=B&documentOldId=13417356)  
[2] [Re: Avaandmete portaali taassünnist](http://p6drad-teel.net/~p6der/ott-vastus.html)  
[3] [Järelevalvemenetluse alustamata jätmine](http://p6drad-teel.net/~p6der/avaandmedte-portaal-2021.pdf)  
[4]  [Protokoll "Teabevärava koosolek 23.03.2020"](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/communication/message/505231)  

