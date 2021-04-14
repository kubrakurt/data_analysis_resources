# Veri Analizi

<!-- TOC -->

- ## İstatistik
  - [Ortalama](#ortalama)    
- ## Eksik Değer (NaN)
  - [Eksik Değer (NaN) Elde Etmek](#nan-değer-elde-etmek)
- ## Veri Tipleri
  - [Birden Fazla Değişken Tipini Değiştirmek](#birden-fazla-değişken-tipini-değiştirmek)

<!-- /TOC -->

## Ortalama

```python
x.mean()
np.mean(x)
np.nanmean(x) # NaN değer varsa göz ardı edilir.
statistics.mean(x)
statistics.fmean(x)
```

## Eksik Değer (NaN) Elde Etmek

Bu işlevlerin hepsi birbirine eş değerdir. O yüzden birbirlerinin yerine kullanabilirsiniz.

```python
float("nan")
math.nan
np.nan

>>> math.isnan(np.nan), np.isnan(math.nan)
(True, True)
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

df[["A", "C"]] = df[["A", "C"]].apply(pd.to_numeric)

# infer_objects() fonksiyonu ile değiştirilebilir.
# Sadece numerik tipe dönüştürülebilecekleri dönüştürüyor.

df = df.infer_objects()
```

## Kaynaklar

* [RealPython](https://realpython.com/)
* [GeeksforGeeks](https://www.geeksforgeeks.org/)
