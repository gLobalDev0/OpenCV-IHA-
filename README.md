Otonom İHA Hedef Tespit ve Takip Sistemi

Bu proje, otonom İHA'lar için gerçek zamanlı bir bilgisayarlı görü hattı (pipeline) olarak geliştirilmiştir. Sistem, otonom yük bırakma görevi öncesinde yerdeki hedefleri renk ve geometri bazlı tanımlayıp takip eder. Düşük kaynaklı gömülü donanımlar üzerinde yerel (local) çalışacak şekilde optimize edilmiştir.

**Teknoloji Yığını ve Donanım**

    Kütüphane: OpenCV (Python)

    Nesne Tespit Modeli: YOLOv8 (Özelleştirilmiş/Hafifletilmiş mimari)

    Hedef Mantığı: Özel kontur analizi, geometrik şekil doğrulaması, HSV renk maskeleme.

    İşlemci: Raspberry Pi 5

    Sensör: Raspberry Pi Camera Module 3 (IMX708)

**Sistem Analizi (Demo)**

Aşağıda, gerçek zamanlı tespit sisteminin çalışma analizi yer almaktadır. Bu görsel, algoritmanın ulaştığı temel başarıları göstermektedir:
Görseldeki Temel Metrikler:

    Anlamsal Sınıflandırma: Nesneler, HSV renk uzayı segmentasyonu ile "mavi hedef" ve "kırmızı hedef" olarak doğru şekilde ayırt edilir.

    Özgün Nesne Takibi: Takip algoritması her hedefe özel bir ID (örn: ID=42, ID=57) atar. Bu sayede İHA hareket ederken hedefler karıştırılmaz.

    Durum Onayı: Geometrik kararlılık kriterlerini karşılayan hedefler "confirmed" (onaylandı) olarak işaretlenir.

    Öznitelik Çıkarımı: Gerçek zamanlı Alan (area) hesabı yapılarak mesafe tahmini ve yük bırakma zamanlaması için veri sağlanır.


<img width="456" height="367" alt="Screenshot from 2026-05-11 00-58-56" src="https://github.com/user-attachments/assets/6c81b7d9-5a4b-4071-97a5-9ea2b39cd725" />
<img width="569" height="393" alt="Screenshot from 2026-05-11 00-58-35" src="https://github.com/user-attachments/assets/59e7e89c-b5c6-4f7c-bea4-1ae1f998ee92" />
