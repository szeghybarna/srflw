---
type: single
#{% if draft %}
draft: true
#{% endif %}
menu: main
audio: []
date: '2024-01-15'
description: 'Tempó/BPM alapú lejátszási lista gyalogláshoz, futáshoz, kerékpározáshoz, fogyáshoz.'
images: ['/images/feature-spotify.webp', '/images/cover-spotify.webp']
series: []
tags: ['spotify']
title: 'Spotify'
videos: []
featured_image: '/images/feature-spotify.webp'
cover_image: '/images/cover-spotify.webp'
translationKey: spotify
language: hu
---

Az elmúlt időszakban sok időt töltöttem ütemes dolgokkal, mint a futás és a biciklizés. Egész jól át tudom közben venni a zene ütemét, így elkezdtem programozóként gondolkodva a [Spotify API](https://developer.spotify.com/documentation/web-api "Spotify API")-jával kísérletezni (minden kísérlet, mondanom sem kell). Találtam egy érdekes adatot a zenékhez, az [audio-features](https://developer.spotify.com/documentation/web-api/reference/get-audio-features "audio-features") keretében a `tempo` mezőt, ami lefordítva:

> A zeneszám teljes becsült tempója percenkénti ütemben (BPM). A zenei terminológiában a tempó egy adott darab sebessége vagy tempója, és közvetlenül az átlagos ütemtartamból származik.

Fel is hívnám az "átlagos" szóra itt a figyelmet, mert ez tényleg átlag. Ha egy zene lassabb ütemben kezdődik, és később gyorsul fel például 160 BPM-re, akkor az átlag tempó kisebb lesz, mint 160 – attól függő mértékben, hogy mennyire volt hosszú az intró. Gép által megadott adatok, vannak hibahatárok – kérlek gondolj erre, amikor hallgatod a lejátszási listákat.

De a lényeg, az általam kedvelt számokból egy kis programocskával előállítom a saját ízlésem szerinti BPM listákat, amiket aztán publikus formában elérhetővé is teszek Spotify-on: [https://open.spotify.com/user/szeghybarna](https://open.spotify.com/user/szeghybarna)

Mire használhatók ezek a listák?

Amikor sétálsz, futsz vagy biciklizel és egy adott ütemet szeretnél tartani, akkor tudsz lépni/tekerni a zene ütemére. Én például 5 km/h (vagy 12 perc/km) sebességgel haladva 125 BPM-es ütemre elmegyek a végtelenbe és tovább is, mert ez a kényelmes ütemem. Hallgatom a zenéket, felveszem a ritmust és kikapcsolok.

Tekerésnél és futásnál ez már kicsit macerásabb, mert elindulok egy magasabb BPM-el, és ahogy emelkedik a pulzusom, úgy cserélgetem a lejátszási listákat egyre alacsonyabb BPM-re, de ott is általában beáll 20 perc után.

Ide is kiexportáltam a lejátszási listát, keresgélhetsz benne. Körülbelül hetente frissítem, mindig az újabb zenék kerülnek előre.

Egyébként azért vannak a MIX listák, mert kis odafigyeléssel a 60-as BPM-re és 120-as BPM-re is ugyanúgy lehet lépni, csak felezni vagy duplázni kell az ütemet – ezt az agyunk meg is teszi helyettünk, nem fogunk más ütemben futni.

Utoljára módosítva: {{ date }}, {{table|length}} szám

|BPM|Added|Playlists|Track|
|--:|-----|---------|:----|
{% for item in table %}| {{item.tempo}} | {{item.added_at[:10]}} | {{item.playlists}}| {{item.artists}}: [{{item.name}}]({{item.href}} "{{item.name}}") |
{% endfor %}{ .w-100 .mw8 .center id="spotify" data-toggle="table" data-search="true" }

{% raw %}
{{< table_sorter spotify >}}
{% endraw %}

Használjátok bátran!
