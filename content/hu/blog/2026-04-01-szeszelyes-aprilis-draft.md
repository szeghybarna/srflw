---
type: single
#{% if draft %}
draft: true
#{% endif %}
audio: []
date: '2026-04-01'
description: 'Kihívás, ahol a véletlen dönt'
images: ['/images/feature-fickle-april.webp', '/images/cover-fickle-april.webp']
series: []
tags: ['strava', 'kihívás']
title: 'Szeszélyes április'
videos: []
featured_image: '/images/feature-fickle-april.webp'
cover_image: '/images/cover-fickle-april.webp'
translationKey: fickle-april
slug: szeszelyes-aprilis
language: hu
mainsection: blog
---
Áprilisban nemcsak az időjárás szeszélyes, hanem a megtett távok is.

Ebben a kihívásban minden edzés számít... vagy épp nem.

Vajon melléd áll a szerencse? Hányszor húzod be a triplát, és hányszor viszi a bank a kilométereidet?

Nézzük a számolást!

Az adott aktivitás Strava activity ID-jének utolsó számjegye dönti el, mennyit ér az aznapi mozgás. Sajnos ez az azonosító csak számítógépen látszik: amikor rákattintasz az aktivitásodra, a linkben jelenik meg.

- 0 = nem számít
- 1, 4, 7 = normál táv
- 2, 5, 8 = dupla táv
- 3, 6, 9 = tripla táv

Vagyis lehet, hogy egy 4 km-es séta végül 12 km-t ér, de az is lehet, hogy egy hősies 10 km sajnos semmit sem ér. Pont ez benne az áprilisi szeszély.

A cél: gyűjtsünk össze 2.000 „szeszélyes kilométert” áprilisban!

**Itt lehet nyomon követni a kihívás állását:**

|Mikor|ActivityID|Sportoló|Eredeti KM|Módosító|Szeszélyes KM|
|-----|----------|--------|---------------:|:------:|------------:|
{% for item in activities %}|{{item.when_text}}|{{item.activity_id}}|{{item.athlete}}|{{item.distance_km}}|{{item.rule}}|{{item.ruledistance_km}} |
{% endfor %}{.mw8 id="spotify" data-toggle="table"}


**Itt van a „hagyományos” ranglista:**

|Sportoló|Távolság KM|
|--------|-------:|
{% for item in traditional %}|{{item.athlete}}|{{item.distance_km}}|
{% endfor %}{ .mw8 data-toggle="table" id="spotify"}


**Itt pedig a „szeszélyes” ranglista:**

|Sportoló|Távolság KM|
|--------|-------:|
{% for item in fickle %}|{{item.athlete}}|{{item.ruledistance_km}}|
{% endfor %}{.mw8 data-toggle="table" id="spotify"}

**A végére pedig egy összefoglaló:**

|Sportoló|Aktivitások|0x|1x|2x|3x|Eredeti KM|Szeszélyes KM|
|--------|-------:|-------:|-------:|-------:|-------:|-------:|-------:|
{% for item in summary %}|{{item.athlete}}|{{item.number_of_activities}}|{{item.count_0}}|{{item.count_1x}}|{{item.count_2x}}|{{item.count_3x}}|{{item.distance_km}}|{{item.rule_distance_km}}|
{% endfor %}{ .mw8 id="spotify" data-toggle="table"}


Csatlakozz kis közösségünkhöz:

- [SRFLW Facebook csoport](https://www.facebook.com/groups/1098348161611343 "SRFLW Facebook csoport")
- [SRFLW Facebook oldal](https://www.facebook.com/simple.rules.for.losing.weight "SRFLW Facebook oldal")
- [SRFLW Strava klub](https://www.strava.com/clubs/srflw "SRFLW Strava klub")



