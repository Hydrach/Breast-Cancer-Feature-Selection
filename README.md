# Meme Kanseri Sınıflandırmasında Özellik Seçimi Yöntemlerinin Karşılaştırılması

Bu projede, **Breast Cancer Wisconsin (Diagnostic)** veri seti üzerinde farklı özellik seçimi yöntemlerinin meme kanseri sınıflandırma performansına etkisi karşılaştırılmıştır. Çalışma, özellik sayısını azaltırken sınıflandırma başarımının ne ölçüde korunabildiğini incelemektedir.

> **Not:** Bu çalışma, makine öğrenmesi yöntemlerinin karşılaştırılmasına yönelik akademik bir araştırmadır; klinik tanı amacıyla kullanılmamalıdır.

## Kullanılan Teknolojiler

- **Python**
- **Scikit-learn**
- Makine öğrenmesi ve örüntü tanıma
- Tabakalı çapraz doğrulama ve performans değerlendirme

## Veri Seti

| Özellik | Değer |
|---|---:|
| Veri seti | Breast Cancer Wisconsin (Diagnostic) |
| Toplam gözlem | 569 |
| Sayısal giriş özelliği | 30 |
| İyi huylu (benign) | 357 |
| Kötü huylu (malignant) | 212 |
| Eğitim / test ayrımı | %80 / %20 |
| Çapraz doğrulama | 5 katlı tabakalı |

Veriler sınıf dağılımları korunarak **455 eğitim** ve **114 test** örneğine ayrılmıştır. Standartlaştırma ve özellik seçimi işlemleri, veri sızıntısını önlemek için çapraz doğrulamanın her eğitim katı içinde gerçekleştirilmiştir.

## Karşılaştırılan Yöntemler

### Özellik seçimi

- **ANOVA F-Test:** Sınıflar arasındaki ayırt ediciliği istatistiksel olarak değerlendirir.
- **Mutual Information:** Özellikler ile hedef sınıf arasındaki bilgi ilişkisini ölçer.
- **Recursive Feature Elimination (RFE):** Daha az etkili özellikleri yinelemeli olarak eler.

Her yöntemde 30 özellik arasından **10 özellik** seçilmiştir. Ayrıca özellik seçimi yapılmayan 30 özellikli modeller de karşılaştırmaya dahil edilmiştir.

### Sınıflandırıcılar

- **k-En Yakın Komşu (k-NN)** (`k=5`)
- **Gaussian Naive Bayes**
- **Lojistik Regresyon** (`liblinear`, `max_iter=5000`)

Böylece **12 model kombinasyonu** değerlendirilmiştir.

## Değerlendirme Ölçütleri

Doğruluk (accuracy), duyarlılık (sensitivity), özgüllük (specificity), hassasiyet (precision), F1-skoru ve ROC-AUC kullanılmıştır. Pozitif sınıf, kötü huylu (malignant) olarak tanımlanmıştır.

## Öne Çıkan Sonuçlar

| Model | Test doğruluğu | ROC-AUC |
|---|---:|---:|
| Özellik seçimi olmadan Lojistik Regresyon | **%98,25** | — |
| RFE + Lojistik Regresyon | **%97,37** | **0,9967** |

**Sonuç:** Özellik seçimi her zaman doğruluğu artırmamıştır; ancak giriş özelliklerinin sayısını 30'dan 10'a indirirken yüksek sınıflandırma performansının korunabildiği görülmüştür.

## Proje Kapsamı

1. Veri setinin yüklenmesi ve eğitim/test olarak ayrılması
2. Eğitim verisi üzerinde standartlaştırma ve özellik seçimi
3. Üç farklı sınıflandırıcı ile model eğitimi
4. Beş katlı tabakalı çapraz doğrulama
5. Bağımsız test kümesinde performans karşılaştırması

## Araştırmacı

**Muhammed Kılıç**  
Zonguldak Bülent Ecevit Üniversitesi — Elektrik-Elektronik Mühendisliği

---

*Bu README, “Farklı Özellik Seçimi Yöntemlerinin Meme Kanseri Sınıflandırma Performansına Etkisinin Karşılaştırmalı Analizi” başlıklı araştırma raporuna dayanılarak hazırlanmıştır.*
