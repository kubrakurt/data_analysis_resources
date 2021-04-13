# Veri Analizi

<!-- TOC -->

- ## İstatistik
  - [Ortalama](#ortalama)    
- ## Eksik Değer (NaN)
  - [Eksik Değer (NaN) Elde Etmek](#nan-değer-elde-etmek)

<!-- /TOC -->

## Ortalama

```python
>>> statistics.mean(x)
```

## Eksik Değer (NaN) Elde Etmek

Bu işlevlerin hepsi birbirine eş değerdir. O yüzden birbirlerinin yerine kullanabilirsiniz.

```python
>>> float("nan")
>>> math.nan
>>> np.nan

>>> math.isnan(np.nan), np.isnan(math.nan)

(True, True)
```

## Kaynaklar

[Real Python](https://realpython.com/)
