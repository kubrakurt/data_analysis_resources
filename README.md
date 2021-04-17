<h1 align="center"> Veri Analizi </h1>

* ## Örnek Veri Analizleri

  * [Aykırı Gözlem Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main/%C3%96rnek%20Analizler/Ayk%C4%B1r%C4%B1%20G%C3%B6zlem%20Analizi.ipynb)
  * [Eksik Veri Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main/%C3%96rnek%20Analizler/Eksik%20Veri%20Analizi.ipynb)
  * [Kategorik Değişkenlerde Eksik Veri Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main Örnek%20Analizler/Kategorik%20Değişkenlerde%20Eksik%20Veri%20Analizi.ipynb)
  * [Python ile Veri Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main/%C3%96rnek%20Analizler/Python%20ile%20Veri%20Analizi.ipynb)

<!-- TOC -->

* ## Droplama İşlemleri
  * [Tekrar Eden Satırları Silmek](#tekrar-eden-satırları-silmek)
* ## Eksik Değer (NaN)
  * [Eksik Değer Elde Etmek](#eksik-değer-elde-etmek)
* ## İstatistik
  * [Ortalama](#ortalama)
* ## Veri Oluşturmak
  * [İki Listeyi Veri Olarak Birleştirmek](#iki-listeyi-veri-olarak-birleştirmek)
* ## Veri Tipleri
  * [Birden Fazla Değişken Tipini Değiştirmek](#birden-fazla-değişken-tipini-değiştirmek)
* ## Zaman
  * [Kod Çalışma Süresi](#kod-çalışma-süresi)

<!-- /TOC -->

## Tekrar Eden Satırları Silmek

```python
df.drop_duplicates()
```

## Eksik Değer Elde Etmek

Bu işlevlerin hepsi birbirine eş değerdir. O yüzden birbirlerinin yerine kullanabilirsiniz.

```python
float("nan")
math.nan
np.nan

>>> math.isnan(np.nan), np.isnan(math.nan)
(True, True)
```

## Ortalama

```python
x.mean()
np.mean(x)
np.nanmean(x) # NaN değer varsa göz ardı edilir.
statistics.mean(x)
statistics.fmean(x)
```

## İki Listeyi Veri Olarak Birleştirmek

```python
df = pd.merge(liste1, liste2, on = "NEYE GÖRE BİRLEŞECEK (örn. liste1.index)")
```

## Birden Fazla Değişken Tipini Değiştirmek

```python
df = pd.DataFrame({"A": [1, 2, 3, 4, 5],
                   "B": ["a", "b", "c", "d", "e"],
                   "C": [1.1, "1.0", "1.3", 2, 5]})
    
# Sözlük aracılığı ile değiştirilebilir.

convert_dict = {"A": int,
                "C": float}
                
df = df.astype(convert_dict)

# Apply fonksiyonu ile değiştirilebilir.

df[["A","C"]] = df[["A","C"]].apply(pd.to_numeric)

# infer_objects() fonksiyonu ile değiştirilebilir.
# Sadece numerik tipe dönüştürülebilecekleri dönüştürüyor.

df = df.infer_objects()
```

## Kod Çalışma Süresi

```python
start_time = datetime.now() 

#Kodlarınız

time_elapsed = datetime.now() - start_time
print("Time Elapsed:", "{}".format(time_elapsed))
```

## Kaynaklar

* [RealPython](https://realpython.com/)
* [GeeksforGeeks](https://www.geeksforgeeks.org/)
* [Data Analysis with Python](https://www.coursera.org/learn/data-analysis-with-python)
* [Python ile Makine Öğrenmesi](https://www.udemy.com/course/python-ile-makine-ogrenmesi/)
