---
type: single
#{% if draft %}
draft: true
#{% endif %}
menu: main
audio: []
date: '2024-01-15'
description: 'Tempo/BPM based playlist for walking, running, cycling, weight loss.'
images: ['/images/feature-spotify.webp', '/images/cover-spotify.webp']
series: []
tags: ['spotify']
title: 'Spotify'
videos: []
featured_image: '/images/feature-spotify.webp'
cover_image: '/images/cover-spotify.webp'
translationKey: spotify
language: en
---

Lately, I've been spending a lot of time doing fast-paced things like running and cycling. I'm pretty good at picking up the beat of music while I'm doing it. Hence, as I am a programmer, I started experimenting with the [Spotify API](https://developer.spotify.com/documentation/web-api "Spotify API"). I found an interesting piece of data for music, the `tempo` field in the [audio-features](https://developer.spotify.com/documentation/web-api/reference/get-audio-features "audio-features"):

> The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.

I would also call attention to the word "average" here because it is indeed average. If a track starts at a slower tempo and later speeds up to 160 BPM, the average tempo will be less than 160 – depending on how long the intro was. In machine-generated data, there are errors, too. Please think about this when listening to playlists.

But the point is, I use a little program to generate BPM lists of my own taste from the tracks I like, which I then make available in a public format on Spotify: [https://open.spotify.com/user/szeghybarna](https://open.spotify.com/user/szeghybarna)

What can these lists be used for?

When you are walking, running or cycling and want to keep a particular beat, you can step/thrust to the beat of the music. For example, I walk at 5 km/h (or 12 min/km) to a 125 BPM beat and go to infinity and beyond because that's my comfortable pace. I listen to the music, pick up the beat and switch off.

For jogging and running, it's a bit more hassle because I start at a higher BPM, and as my heart rate rises, I switch playlists to lower and lower BPM; it usually settles after 20 minutes.

I've exported the playlist here, too; you can search it. I update it every week or so, always with the newest tracks.

By the way, the MIX lists are there because, with a bit of attention, you can move to 60 BPM and 120 BPM in the same way; you just have to halve or double the beat - our brain does it for us, and we won't run at a different beat.


Last updated: {{ date }}, {{table|length}} tracks

|BPM|Added|Playlists|Track|
|--:|-----|---------|:----|
{% for item in table %}| {{item.tempo}} | {{item.added_at[:10]}} | {{item.playlists}}| {{item.artists}}: [{{item.name}}]({{item.href}} "{{item.name}}") |
{% endfor %}{ .w-100 .mw8 .center id="spotify" data-toggle="table" data-search="true" }

{% raw %}
{{< table_sorter spotify >}}
{% endraw %}

Feel free to use it!
