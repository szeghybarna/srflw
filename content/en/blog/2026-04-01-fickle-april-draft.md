---
type: single
#{% if draft %}
draft: true
#{% endif %}
audio: []
date: '2026-04-01'
description: 'A challenge where chance makes the call'
images: ['/images/feature-fickle-april.webp', '/images/cover-fickle-april.webp']
series: []
tags: ['challenge', 'strava']
title: 'Fickle April'
videos: []
featured_image: '/images/feature-fickle-april.webp'
cover_image: '/images/cover-fickle-april.webp'
translationKey: fickle-april
slug: fickle-april
language: en
mainsection: blog
---

In April, it is not just the weather that is unpredictable, but your mileage too.

In this challenge, every workout counts... or maybe it does not.

Will luck be on your side? How many times will you hit triple, and how often will the bank take your kilometres?

Here is how the scoring works.

The last digit of a Strava activity ID determines how much that day’s activity is worth. Unfortunately, this ID is only visible on a computer: when you click on your activity, it appears in the link.

- 0 = does not count
- 1, 4, 7 = normal distance
- 2, 5, 8 = double distance
- 3, 6, 9 = triple distance

So a 4 km walk might end up being worth 12 km, while a heroic 10 km effort could unfortunately count for nothing at all.
That is exactly what makes it feel so perfectly April-like.

The goal: collect 2,000 “fickle kilometres” during April.

**You will be able to track the challenge here:**

|When|ActivityID|Athlete|Original km|Modifier|Fickle km|
|----|----------|-------|----------------:|:---------------:|--------:|
{% for item in activities %}|{{item.when_text}}|{{item.activity_id}}|{{item.athlete}}|{{item.distance_km}}|{{item.rule}}|{{item.ruledistance_km}} |
{% endfor %}{ .mw8 id="spotify" data-toggle="table"}



**Here is the “traditional” leaderboard:**

|Athlete|Distance km|
|-------|-------:|
{% for item in traditional %}|{{item.athlete}}|{{item.distance_km}}|
{% endfor %}{ .mw8 data-toggle="table" id="spotify"}


**And here is the „fickle” leaderboard:**

|Athlete|Distance km|
|-------|-------:|
{% for item in fickle %}|{{item.athlete}}|{{item.ruledistance_km}}|
{% endfor %}{ .mw8 data-toggle="table" id="spotify"}

**A summary:**

|Athlete|Activities|0x|0x km|1x|1x km|2x|2x km|3x|3x km|Original km|Fickle km|
|--------|-------:|-------:|-------:|-------:|-------:|-------:|-------:|-------:|-------:|-------:|-------:|
{% for item in summary %}|{{item.athlete}}|{{item.number_of_activities}}|{{item.count_0}}|{{item.km_0}}|{{item.count_1x}}|{{item.km_1x}}|{{item.count_2x}}|{{item.km_2x}}|{{item.count_3x}}|{{item.km_3x}}|{{item.distance_km}}|{{item.rule_distance_km}}|
{% endfor %}{ .mw8 id="spotify" data-toggle="table"}


Join our little community:

- [SRFLW Facebook Group](https://www.facebook.com/groups/1098348161611343 "SRFLW Facebook Group")
- [SRFLW Facebook page](https://www.facebook.com/simple.rules.for.losing.weight "SRFLW Facebook page")
- [SRFLW Strava Club](https://www.strava.com/clubs/srflw "SRFLW Strava Club")

