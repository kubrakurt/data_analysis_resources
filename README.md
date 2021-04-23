<h1 align="center"> Veri Analizi </h1>

* ## Örnek Veri Analizleri

  * [Aykırı Gözlem Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main/%C3%96rnek%20Analizler/Ayk%C4%B1r%C4%B1%20G%C3%B6zlem%20Analizi.ipynb)
  * [Değişken Dönüşümleri](https://github.com/kubrakurt/data_analysis_resource/blob/main/Örnek%20Analizler/Değişken%20Dönüşümleri.ipynb)
  * [Eksik Veri Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main/%C3%96rnek%20Analizler/Eksik%20Veri%20Analizi.ipynb)
  * [Kategorik Değişkenlerde Eksik Veri Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main/Örnek%20Analizler/Kategorik%20Değişkenlerde%20Eksik%20Veri%20Analizi.ipynb)
  * [One-Hot Dönüşümü ve Dummy Değişken Tuzağı](https://github.com/kubrakurt/data_analysis_resource/blob/main/Örnek%20Analizler/One-Hot%20Dönüşümü%20ve%20Dummy%20Değişken%20Tuzağı.ipynb)
  * [Python ile Veri Analizi](https://github.com/kubrakurt/data_analysis_resource/blob/main/%C3%96rnek%20Analizler/Python%20ile%20Veri%20Analizi.ipynb)
  * [Tahmine Dayalı Değer Atama Yöntemleri](https://github.com/kubrakurt/data_analysis_resource/blob/main/Örnek%20Analizler/Tahmine%20Dayalı%20Değer%20Atama%20Yöntemleri.ipynb)
  * [Veri Standardizasyonu](https://github.com/kubrakurt/data_analysis_resource/blob/main/Örnek%20Analizler/Veri%20Standardizasyonu.ipynb)

<!-- TOC -->

* ## Droplama İşlemleri
  * [Tekrar Eden Satırları Silmek](#tekrar-eden-satırları-silmek)
* ## Eksik Değer
  * [Eksik Değer Elde Etmek](#eksik-değer-elde-etmek)
* ## İstatistik
  * [Ortalama](#ortalama)
* ## Veri Biçimlendirmek
  * [f-Strings](#f-Strings)
* ## Veri Oluşturmak, Birleştirmek & Ayırmak
  * [İki Listeyi Veri Olarak Birleştirmek](#iki-listeyi-veri-olarak-birleştirmek)
  * [Verileri Satır Bazında Birleştirmek](#verileri-satır-bazında-birleştirmek)
  * [Verileri Satır Bazında Gruplayarak Birleştirmek](#verileri-satır-bazında-gruplayarak-birleştirmek)
  * [Verileri Sütun Bazında Birleştirmek](#verileri-sütun-bazında-birleştirmek)
  * [Verileri Sütun Bazında Eksik Değerli Satırları Almadan Birleştirmek](#verileri-sütun-bazında-eksik-değerli-satırları-almadan-birleştirmek)
  * [Verileri Sütun Bazında Eksik Değerleri Azaltacak Şekilde Birleştirmek](#verileri-sütun-bazında-eksik-değerleri-azaltacak-şekilde-birleştirmek)
  * [DataFrame Tipteki Verilerin Sütun Değerlerini Birleştirmek](#dataframe-tipteki-verilerin-sütun-değerlerini-birleştirmek)
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

## f-Strings

```python
counter = 5

print(f"this is counter {counter}")
>>> this is counter 5

print(f"this is counter {0}".format(counter))
>>> this is counter 5
```

## İki Listeyi Veri Olarak Birleştirmek

```python
df = pd.merge(liste1, liste2, on = "NEYE GÖRE BİRLEŞECEK (örn. liste1.index)")
```

## Verileri Satır Bazında Birleştirmek

```python
frames = [df1, df2, df3]
pd.concat(frames)
```
<p align="left"> <img src="https://pandas.pydata.org/pandas-docs/stable/_images/merging_concat_basic.png" /> </p>

## Verileri Satır Bazında Gruplayarak Birleştirmek

```python
pd.concat(frames, keys=["x","y","z"])
```
<p align="left"> <img src="https://pandas.pydata.org/pandas-docs/stable/_images/merging_concat_keys.png" /> </p>

## Verileri Sütun Bazında Birleştirmek

```python
frames = [df1,df4]
pd.concat(frames, axis=1)
```
<p align="left"> <img src="https://pandas.pydata.org/pandas-docs/stable/_images/merging_concat_axis1.png" /> </p>

## Verileri Sütun Bazında Eksik Değerli Satırları Almadan Birleştirmek

```python
pd.concat(frames, axis=1, join="inner")
```
<p align="left"> <img src="https://pandas.pydata.org/pandas-docs/stable/_images/merging_concat_axis1_inner.png" /> </p>

## Verileri Sütun Bazında Eksik Değerleri Azaltacak Şekilde Birleştirmek

```python
pd.concat(frames, axis=1).reindex(df1.index)
```
<p align="left"> <img src="https://pandas.pydata.org/pandas-docs/stable/_images/merging_concat_axis1_join_axes.png" /> </p>

## DataFrame Tipteki Verilerin Sütun Değerlerini Birleştirmek

```python
df["New Column Name"] = df["1st Column Name"] + df["2nd Column Name"]
df["New Column Name"] = df["1st Column Name"].map(str) + df["2nd Column Name"].map(str)
df["Full Date"] = df["Day"].map(str) + "-" + df["Month"].map(str) + "-" + df["Year"].map(str)
```
<p align="left"> <img src="https://datatofish.com/wp-content/uploads/2018/09/00_combined_values.png" /> </p>

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
* [Pandas Documentation](https://pandas.pydata.org/pandas-docs/stable/index.html)
* [Data to Fish](https://datatofish.com)
