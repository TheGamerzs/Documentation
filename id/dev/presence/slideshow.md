---
title: Kelas Slideshow
description:
published: true
date: 2020-12-25T00:47:38.111Z
tags:
editor: markdown
dateCreated: 2020-12-25T00:44:42.803Z
---

# Kelas Slideshow

## Perkenalan

Kelas `Slideshow` digunakan untuk mengatur beberapa `PresenceData` dan "slide" melewatinya setiap x milidetik (minimal: 5000).

Lihat metode [`createSlideshow`](/dev/presence/class#createslideshow) di kelas [`Presence`](/dev/presence/class) di bagian bagaimana cara membuat `Slideshow`.

## Properti

### `currentSlide`

Mengembalikan objek [`PresenceData`](/dev/presence/class#presencedata-interface) dari apa yang ditampilkan presence/slide saat ini.

```typescript
const currentSlide = slideshow.currentSlide
console.log(currentSlide.details) // Akan mencatat rincian dari PresenceData
```

## Metode

### `addSlide(String, PresenceData, Number)`

Menambahkan slide baru ke `Slideshow` sesuai data yang diberikan.

Parameter pertama membutuhkan `String` yang akan digunakan sebagai identifier unik untuk slide.

Second parameter requires a [`PresenceData` interface](/dev/presence/class#presencedata-interface) to get all information that you want to display in the slide.

Third parameter requires a `Number` which is the amount of time in milliseconds (minimum: 5000) that this slide will show.

### `getSlides()`

Returns all slides saved in the `Slideshow` as an `Array` of [`SlideshowSlide`](#slideshowslide-class).

### `updateSlide(String, PresenceData, Number)`

Updates the slide of the given `id` according to provided data.

First parameter requires a `String` that is the unique identifier of the slide you want to update.

Second parameter requires a [`PresenceData` interface](/dev/presence/class#presencedata-interface) to get all information that you want to display in the slide.

Third parameter requires a `Number` which is the amount of time in milliseconds (minimum: 5000) that this slide will show.

### `hasSlide(String)`

Mengembalikan `Boolean` yang manyatakan apakah slide ditambahkan ke `Slideshow`.

### `deleteSlide(String)`

Menghapus slide dengan `id` yang diberikan, dari `Slideshow`.

First parameter requires a `String` that is the unique identifier of the slide you want to delete.

### `deleteAllSlides()`

Menghapus semua slide dari `Slideshow`.

# Kelas SlideshowSlide

## Perkenalan

`SlideshowSlide` adalah representasi internal dari setiap slide di `Slideshow`.

## Properti

### `id`

Mengembalikan `String` dari id slide.

### `data`

Mengembalikan objek [`PresenceData`](/dev/presence/class#presencedata-interface) dari `PresenceData` yang disimpan di slide.

## Metode

### `updateData(PresenceData)`

Menetapkan slide data berdasarkan data yang tersedia.

You must provide a `PresenceData` interface to get all information that you ultimately want to display in your profile.

### `updateInterval(Number)`

Mengatur interval dari slide sesuai data yang diberikan.

You must provide a `Number` which is the amount of time in milliseconds (minimum: 5000) that this slide will show.