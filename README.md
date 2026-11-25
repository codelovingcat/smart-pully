# Smart Pully 🐣

**Smart Pully**, Türkçe matematik öğretimi için geliştirilen deneysel bir yapay zekâ öğretmen asistanı (Puli) araştırma deposudur.

> **Durum:** Araştırma ve prototipleme aşamasında. Bu depo henüz çalışır bir uygulama, üretim servisi veya eğitilmiş model ağırlıkları içermez.

## Amaç

Puli'nin hedefi yalnızca matematik sorularının sonucunu bulmak değil; öğrencinin gönderdiği metin veya soru fotoğrafını anlayarak **doğru, açıklanabilir ve seviyeye uygun** bir çözüm sunmaktır.

Çalışmaların odakları:

- Türkçe matematik sorularını ve matematiksel gösterimleri anlama
- Fotoğraflarda birden fazla soru, soru numarası ve sınav yönergelerini ayırt etme
- Kesir, köklü ifade, tablo ve şekilleri doğru yorumlama
- Problemlerdeki koşulları uydurmadan matematiksel çözüm üretme
- Öğrenciye uygun, sade bir öğretmen üslubu geliştirme
- MEB öğretim programındaki öğrenme çıktılarıyla uyumlu anlatım hazırlama

## Model ve deney altyapısı

| Bileşen | Durum / yaklaşım |
| --- | --- |
| Temel model | Qwen3.5-4B (ilk prototip ve görsel testleri) |
| Diğer adaylar | Qwen3.5-9B ve alternatif açık ağırlıklı modeller |
| Deney ortamı | Kaggle Notebooks / Google Colab |
| İnce ayar | LoRA / SFT deneyleri |
| Görsel değerlendirme | Soru fotoğrafından okuma ve çözme testleri |
| Müfredat | MEB öğrenme çıktıları; ileride RAG ile erişim |
| Uygulama entegrasyonu (plan) | .NET servisleri + Python AI servisi |

### Pilot çalışmadan notlar

- 32 örneklik bir matematik pilot veri kümesi ile **24 eğitim / 8 test** ayrımı denendi.
- Qwen3.5-4B üzerinde kısa bir LoRA eğitimi gerçekleştirildi.
- Görsel deneylerde bazı sorular doğru okunup çözülebilirken, soru sayısı tespiti, problem koşullarını yorumlama ve gereksiz uzun cevaplar gibi hatalar gözlemlendi.
- **Prompt iyileştirmesi, model ağırlıklarının kalıcı olarak eğitildiği anlamına gelmez.**
- Bu depoda **henüz LoRA adapter dosyası veya model checkpoint'i bulunmuyor**.

## Önerilen depo yapısı

Notebook ve analizler eklendikçe aşağıdaki yapı kullanılabilir:

```text
smart-pully/
├── README.md
├── notebooks/       # Kaggle / Colab deney notebook'ları
├── evaluations/     # Test sonuçları ve hata analizleri
├── prompts/         # Deneysel sistem ve kullanıcı istemleri
└── docs/            # Mimari ve model araştırma notları
```

## Değerlendirme ilkeleri

Görsel matematik testlerinde aşağıdaki beceriler **ayrı ayrı** ölçülmelidir:

1. Görselde gerçekten bulunan soruları ve numaralarını tespit etme
2. Metin, seçenek ve matematiksel ifadeleri doğru aktarma
3. Verilen koşulları doğru yorumlama
4. İşlemleri doğrulama ve doğru seçeneği bulma
5. Çözümü Türkçe, anlaşılır ve öğrenci seviyesinde açıklama

**Önemli:** MEB dokümanları, yayımlanmış sınav soruları ve üçüncü taraf eğitim içerikleri kullanılırken telif, lisans ve kullanım izinleri ayrıca kontrol edilmelidir. Kişisel öğrenci verileri herkese açık depoya yüklenmemelidir.

## Sonraki adımlar

- Kaggle/Colab notebook'larını sürümleyerek bu depoya kaydetmek
- Görsel testleri için kontrol edilmiş bir değerlendirme seti hazırlamak
- MEB müfredat verisini model eğitiminden bağımsız bir bilgi kaynağı olarak bağlamak
- Qwen3.5-4B ve daha büyük aday modelleri aynı testlerle karşılaştırmak
- Doğrulanmış öğretmen yanıtlarıyla yeni LoRA deneyleri yapmak

---

*Smart Pully / Puli — deneysel eğitim yapay zekâsı projesi.*
