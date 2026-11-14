# Jev: karar sinyali olarak kullanım ve kanıt sınırları

**Kaynak kontrolü:** 14 Kasım 2026. Bağlantılardaki değişken bilgiler ve model sürümü uygulamadan önce yeniden kontrol edilmelidir. [Kaynak kaydı](KAYNAKLAR.md) erişim ve hak sınırlarını gösterir.

## Arayüzün anlattığı

TypeSafe dokümanı, bir durum girdisi üzerinde sorulan sorular için `Noul` (ikili olay olasılığı), `Choice` (seçenek ve dağılım), `Score` (sıralı düzey) ve ayrıca görüntü konumlamaya yönelik `Box` yanıtlarını tanımlar. Hangi modelin hangi tipi veya girdiyi desteklediği ayrıca doğrulanmalıdır. [K1]

Önerilen uygulama deseni: uygulama girdiyi sınırlar, modelden dar bir karar sinyali ister ve son eylemi ayrı kurallarla belirler. Bu, dokümanlardan türetilmiş bir tasarım önerisidir; burada çalışan entegrasyon sunulmamaktadır. [K1][K3]

## Duyuru, örnek ve gerçek test ayrımı

- **Sağlayıcı önerisi:** TypeSafe kullanım haritası destek yönlendirme, belge işleme ve ajan kontrolü gibi örnekler listeler. Bunlar müşteri üretim başarısının veya bağımsız güvenlik testinin kanıtı değildir. [K3]
- **Üçüncü taraf deney raporu:** `jev-spam-eval` bir spam ve phishing değerlendirmesi ve karşılaştırma tanımlar. Depo, sonuçların keşif amaçlı olduğunu ve açık veri kümelerinin ön eğitimde görülüp görülmediğinin belirlenemediğini söylüyor. Sonuçları bu çalışma kapsamında yeniden çalıştırmadık; başka verilere genellenemez. [K4]
- **Yerel test ve üretim kullanımı:** Bu çalışmada yeni API testi veya kapsamlı üretim vakası taraması yapılmadı. Yerel araştırmadaki test kaydı ve üretim vakası araması kamuya açık bağımsız kanıtla doğrulanamadığından burada sonuç olarak sunulmaz.

## Sınırlar ve değerlendirme önerisi

Sağlayıcı, sayısal hesap, tarih karşılaştırması, çok adımlı dolaylama, ilgisiz uzun bağlam ve yönlendirmeye çalışan içerik gibi durumlarda hata olasılığına dikkat çekiyor. Seçenek sırası da yanıtı etkileyebilir. Bu, sağlayıcı beyanıdır; bu çalışmada hata oranları bağımsız ölçülmedi. [K2]

Olasılık biçiminde bir yanıt kendi başına kalibrasyon kanıtı değildir. Kalibrasyon eğrisi, tahmin gruplarındaki olay sıklığını tahminlerle karşılaştırır; Brier veya log kaybı tek başına yalnız kalibrasyonu ölçmez. [K5] Pilot yapılacaksa ayrı tutulan etiketli veride dil, hata maliyeti ve kritik sınıflar için ölçüm yapılması bir öneridir, mevcut test sonucu değildir.

**Önerilen sınır:** Başlangıçta sonucu eylemi değiştirmeyen gölge ölçümde tutmak; kritik yetkileri deterministik kontroller ve insan incelemesinde bırakmak. Sağlayıcı hatasında güvenli alternatif belirlenmeden otomatik işlem yapılmamalıdır. Bunlar araştırma çıkarımlarıdır, doğrulanmış ürün özellikleri değildir.

## Bilinmeyenler

Bu görevde Türkçe başarımı, bağımsız gecikme, üretim güvenliği, veri saklama koşulları, SLA ve toplam maliyet ölçülmedi. Eski fiyat, kota ve endpoint bilgileri güncel sözleşme gibi aktarılmadı. Gizli veya kişisel veri herhangi bir servise gönderilmedi; yeni ücretli çağrı yapılmadı.

Kaynak kimlikleri ve bağlantılar: [KAYNAKLAR.md](KAYNAKLAR.md).
