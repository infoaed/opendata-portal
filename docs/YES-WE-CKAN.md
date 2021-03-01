# Teabevärava sulgemine anno 2021

Eesti esimene, n-ö "katse"-teabevärav loodi 2011. aasta lõpus [piloodina majandusministeeriumi eestvedamisel](https://joinup.ec.europa.eu/sites/default/files/document/2014-04/Estonian%20Open%20Data%20Greenbook_0.pdf) ning põhines [CKAN-tarkvaral](README.md#ckan), piloodi põhjal [hangiti 2014-2015 mõnevõrra kiirustades](https://riigihanked.riik.ee/rhr-web/#/procurement/609229) 39 100 euro eest üldkasutuseks mõeldud teabevärav. Selle ajakohastamiseks tellis ministeerium 2017-2018 mult omakorda 9200 euro eest teabevärava keelemoodulite tööleseadmise (pidin fiksima [kogu lõhutud modulaarsuse](README.md#hinnang-portaali-tarkvara-seisundile), tulemus on [seesama GitHubi repo siin](https://github.com/infoaed/opendata-portal)).

Sisuliselt samal ajal võitis [avaandmete valdkonna edendamise riigihanke](https://riigihanked.riik.ee/rhr-web/#/procurement/718616) ühing nimega [Open Knowledge Estonia](https://et.wikipedia.org/wiki/Open_Knowledge_Estonia), kus olin toona juhatuse liige, ning 2018. aasta sügisest lülitati hanke tulemusel ja [koostöös ministeeriumiga](https://foto.piletid.eu/konverents/events/2018-tarkeriik/Ott-Velsberg-ettekanne.pdf) teabevärav [väga väga väga segastel asjaoludel](https://www.facebook.com/groups/openestdata/permalink/1918100995150930) [JKAN-tarkvara](https://github.com/timwis/jkan) peale.

## CKANi uuesti hankimine...

Loetud kuude jooksul sai ministeerium ilmselt tehtud veast aru, sest juba märtsis 2020 kuulutati välja [järjekordne riigihange](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292) veel aasta eest olemas olnud CKAN-portaali uuesti hankimiseks eeldatava hinnaga 138 000 eurot:

> "Teabevärav on kavas välja arendada ja juurutada kasutades olemasolevat vabavaralist lahendust [CKAN](https://ckan.org/) ning kasutades maksimaalselt ära selles olemas olevaid funktsionaalsuseid. Lisafunktsionaalsused on kavas välja arendada paigaldatavate lisamoodulitena." [1](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/documents/source-document?group=B&documentOldId=13417356)

Suur oli minu üllatus, kui märgates 2. detsembril [teadet uue teabevärava valmimisest](https://www.facebook.com/groups/openestdata/permalink/2445342005760157/) ei paistnud CKAN-i kusagilt ja minu pärimise peale vastas ministeeriumis 2018. aasta hilissuvest avaandmete eest vastutav Ott Velsberg:

> "Avaandmete teabevärava puhul oleme tegelikult loobunud CKANi kasutamisest, seda ka jätkuarenduste puhul. Uuenenud teabevärav avalikustatakse juba peatselt, kõigi eelduste kohaselt järgmine nädal. Samas kindlasti ka jätkame teabevärava arendustega." [2]

## ...seda siiski saamata!

Palusin Otilt selgitust, mis kaalutlustel on riigihanke algsetest nõudmistest loobutud, mis on alternatiivi spetsifikatsioon ja kuidas põhjendatakse selle eelistamist. Hanke aluseks olnud [arendustööde tehnilises kirjelduses](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/documents/source-document?group=B&documentOldId=13417356) on nimelt ühemõtteliselt kirjas, et hangitakse CKAN-tarkvaral põhinev lahendus (tsitaat ülal), pakkujatele korraldatud [infotunni protokoll](https://riigihanked.riik.ee/rhr-web/#/procurement/1706292/communication/message/505231) ja [selle audiosalvestus](https://zoom.us/rec/share/5NQqE7vTx1pIG4not3qDGY8eD635eaa81XUZ-fcImkYxQjNgvRbVdOsVmJKX1EQq) ([5 min lühiversioon](https://soundcloud.com/ornoobikkuhutottadsa/ott-infotund)) kinnitavad, et on "nõutud kasutada" just CKAN-i andmete haldamise süsteemi (DMS), aga sisuhalduse funktsioonide (CMS) realiseerimisel on valik vaba, kuid on "rangelt soovituslik" kasutada laialt levinud, aktiivse toe ja hea ühilduvusega süsteeme (sj mainitakse Wordpressi ja Drupalit ja React esitluskihti).

Sain nädal hiljem pärast omapoolset meeldetuletust lõpuks telefonikõne, kus Ott väitis, et CKAN-ist loobuti, kuna see ei ühildunut arendaja väitel Python 3 versiooniga (tegelikult arendusversioonis [tugi olemas jaanuaarist 2020](https://github.com/ckan/ckan/issues/4801), ametlikult pakendatud [augustis](https://github.com/ckan/ckan/releases/tag/ckan-2.9.0)), selle jõudlus ei vastavat nõudmistele (aga vastab [UK](https://data.gov.uk/), [USA](https://www.data.gov/), [Kanada](https://open.canada.ca/en/open-data) jpt omadele), selle arendus oli toppama jäänud ja muud riigid olid sellest loobumas või loobunud (nt USA pani uue CKAN-portaali laivi [veebruaris 2021](https://www.infodocket.com/2021/02/06/new-version-of-the-data-gov-catalog-goes-live/)) ja kokkuleppel hanke võitjaga otsustati kirjutada kogu DMS-i nullist (kui olemasoleva vabavara kasutuselevõtmine ja uue kirjutamine maksavad sama palju, siis on kuskil midagi põhimõtteliselt valesti). Põhjendused hanke aluspõhimõtete muutmisele pidid olema kirjas "detailanalüüsis", mis olevat hanke tehnilise kirjelduse osa ja see pidi olema üleval hankedokumentide hulgas. Palusin Otil selle mulle meilile saata, et saaksin nende põhjendustega tutvuda ja veenduda, et hangitakse tõepoolest seda, mida plaaniti. Kuna dokumenti järgmiseks päevaks ei saabunud, siis tegin selle saamiseks teabenõude, millele sain 22. detsembril eitava vastuse, sest kuna hange polevat lõppenud, siis on see dokument sisekasutuseks ja mul pole võimalik põhjendustega tutvuda.

Sellega minu erivõimed dokumentidega tutvumiseks piirdusid. Delegeerisin hanke veidruste ja vastustest hoidumisega tegelemise [rahandusministeeriumile](https://www.rahandusministeerium.ee/et/eesmargidtegevused/riigihangete-poliitika/jarelevalve), kes vastas mulle 18. jaanuaril, et kuna hankeleping on juba sõlmitud, siis ei saa enam järelevalvet alustada, aga nad siiski uurisid ning Ott vastas neile selgituseks, viidates korraldatud koosoleku audiosalvestisele:

> "Salvestusest selgub, et hankijal ei ole kokkulepet CKANiga ja et koosoleku
toimumise hetkel olemasoleva teabe alusel kasutab CKAN platvormi Euroopa avaandmete portaal, UK,
Kanada jt valitsused sh USA data.gov. Kui pakkuja eelistab kasutada DMSi (andmete haldamise süsteem),
siis on hankija soovitanud kasutada CKAN platvormi. Hankija ütles infotunnis, et tal ei ole eelistusi ega
piiranguid missugust platvormi peaks pakkuja soovima kasutada, sest pakkujal on valiku vabadus." [3]

Kuulates üle infotunni [audiosalvestist](https://soundcloud.com/ornoobikkuhutottadsa/ott-infotund) (5 min ekstrakt), on seal korduvalt osutatud CKANile kui soovitud ja välja käidud DMS-ile ehk andmehalduse süsteemile, seejärel uurib küsija, kas "CKAN on mõeldud peamiselt andmete enda jaoks", aga portaali sisuhaldus võib olla ükskõik, mis CMS-i peal, mille peale Ott esmalt vastab, et "ei, me plaaniksime kasutada ikkagi sedasama CKANi, aga ta on sisuliselt ikkagi andmete jaoks", mille peale küsitakse üle, et kuna CKANi enda lehel on toodud näidetena CKAN koos Drupaliga ja/või Wordpressiga, siis kas CMS ei võiks ikkagi olla ükskõik milline, millega on Ott "täiesti nõus". Selguse mõttes palutakse veelkord kinnitada, et "CKAN on andmete poole peal, aga CMSi osas on käed vabad", mille peale kinnitab Ott taas, et "CKANi poole pealt on andmed", aga siis täpsustatakse, et CMSi puhul on eelistatud üldlevinud Wordpress või Drupal, et poleks "imeplatvorm", millega tekib pärast peavalu. Seda soovitatakse osaleja poolt hankesse selgelt sisse kirjutada, korraldajad kinnitavad, et protokolli saab see info sisse. Kinnitatakse veelkord üle, et CMS pole ette antud rangelt, et valikuvabadus peab olema ja see oligi nii plaanitud. Audiosalvestise lõpetuseks tänab Ott osalejaid, et "CMSi pool on nüüd üle käidud", sest nende endi jaoks oli ka ebaselge see.

## Mõistlik valdkonna spetsialist

Rahandusministeeriumi vastuses üteldakse väga ilusti, et "riigihanke alusdokumentide tingimusi kui avalikkusele suunatud tahteavaldust tuleb tõlgendada nii nagu mõistlik isik seda tahteavaldust mõistma pidi" ja "sealjuures lähtub mõistliku isiku arusaama sisustamine sellest, kuidas saavad hanketingimustest aru hanke esemega seonduva valdkonna spetsialistid". Infotunnis selgus, et hanke esmega seotud valdkonna spetsialistid said aru, et DMS on rangelt CKAN ja CMS on vabalt valitav, aga eelistatud on levinumad nagu Drupal või Wordpress. Niimoodi kinnitab ka infotunni protokoll:

> "Tehnilised nõuded (kasutatavate tehnoloogiate valik peab olema põhjendatud, rangelt soovituslik on valida levinud platvorm, millel on community tugi, mis ühildub süsteemidega ning mille kvaliteedis saab kindel olla):
>  
> 1. CKAN – nõutud kasutada antud DMS’i (andmete haldamise süsteemi).
> 2. Drupal, WordPress – võib kasutada vabaltvalitud laialt levinud CMSi (sisuhaldussüsteemi).
>  
> Riigil ei ole CKANiga otseseid kokkuleppeid, kuid kuna CKAN on kasutusel ka teiste riikide avaandmete portaalides, siis võib eeldada, et tegu on hea koostööpartneriga, jättes kõrvale nende veebilehe väikese aktiivsuse." [4]

Kui vaadata seda protokolli, siis CKANi on "nõutud kasutada" DMSi ehk andmehalduse süsteemina. Mitte ühtegi reservatsiooni. Drupal või Wordpress on eelistatud CMSi ehk sisuhalduse rollis (aga valik on vaba, kuid "rangelt soovituslik" on levinud, toega ja ühilduvusega tehnoloogia). Protokoll kajastab infotunni audiosalvestut igati täpselt ja CKANist loobumine on leidnud aset pärast hankelepingu sõlmimist nagu Ott mulle telefonis ütles.

Seega on Ott vastuses rahandusministeeriumile valetanud, et infotunnis on üteldud tingivalt, et "**kui** pakkuja eelistab kasutada DMSi, **siis** hankija on soovitanud kasutada CKAN platvormi". Sest kõigis materjalides on CKAN kui andmehalduse süsteem ühemõtteliselt nõutud ja pole ühtegi kommunikatsioonikildugi sellest, et võiks kasutada midagi muud.

## Millest me ilma jääme?

...