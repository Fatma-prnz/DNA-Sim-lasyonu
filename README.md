# DNA-Sim-lasyonu
`---
title: "DNA Simülasyonu ve Okuma Hataları"
author: "Fatma Nur Pırnaz"
date: "2025-04-16"
output: html_document
`
`
knitr::opts_chunk$set(echo = TRUE)
`

Dosya okuması yapabilmek için "seqinr" paketini indirelim.
`

library(seqinr)
`

Escherichia coli canlısına ait referans genoma ait dosyayı okuyalım.
`

genom <- read.fasta(file = "file_show.gz")
`

Şimdi yapmamız gereken şey bir pozisyon seçmek.
Çalışmak istediğim dizi uzunluğu 100 nükleotid.
`

# ilk kromozomu seçtim
dizi <- genom[[1]]

# genom uzunluğunu aldım
genom_uzunlugu <- length(dizi)

# başlangıç pozisyonunu seçtim
baslangıc_pozisyonu <- sample(1:(genom_uzunlugu-99),1)

# 100 nükleotidlik parçayı seçtim
fragment <- dizi[baslangıc_pozisyonu:(baslangıc_pozisyonu+99)]

# dizi
cat(paste(fragment, collapse = ""))

`