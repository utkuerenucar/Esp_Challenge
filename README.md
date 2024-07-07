# ESP32 Challenge

Bu proje, çeşitli ESP32 tabanlı uygulamaları içerir. Her görev, belirli bir problemi çözmeyi amaçlayan bağımsız bir projedir. Aşağıda her bir görev hakkında detaylı açıklamalar bulabilirsiniz.

## İçindekiler
1. [WiFi İle Durum Bildiren Trafik Lambası Dizisi](#wifi-ile-durum-bildiren-trafik-lambasi-dizisi)
2. [Ev Sıcaklık Bilgisi](#ev-sicaklik-bilgisi)
3. [220V AC Ampul Kablosuz Kontrolü](#220v-ac-ampul-kablosuz-kontrolu)
4. [Ultrasonik İnsan Sayacı](#ultrasonik-insan-sayaci)
5. [RFID Kapı Açma Sistemi](#rfid-kapi-acma-sistemi-bonus)
6. [MQTT İle Haberleşen Toprak Sulama Sistemi](#mqtt-ile-haberlesen-toprak-sulama-sistemi)

## Kurulum

Bu projeler için gerekli olan donanımlar ve yazılımlar:
- ESP32 Geliştirme Kartı
- Arduino IDE
- WiFi Modülü (ESP32 dahili)
- Sıcaklık Sensörü (DHT11 veya DHT22)
- Röle Modülü
- Ultrasonik Sensör (HC-SR04)
- RFID Modülü
- Toprak Nem Sensörü
- MQTT Broker (Mosquitto önerilir)
- Discord Bot (bonus görev için)

### Arduino IDE Kurulumu
1. Arduino IDE'yi [buradan](https://www.arduino.cc/en/Main/Software) indirip kurun.
2. Arduino IDE'yi açın ve `File -> Preferences` menüsüne gidin.
3. "Additional Boards Manager URLs" alanına `https://dl.espressif.com/dl/package_esp32_index.json` URL'sini ekleyin.
4. `Tools -> Board -> Board Manager` menüsüne gidin ve "ESP32"yi aratarak kurulumunu yapın.

## Görevler

### 1. WiFi İle Durum Bildiren Trafik Lambası Dizisi
Bu projede, basit bir trafik lambası uygulamasına ek olarak, ESP32 mikrodenetleyicisini kullanarak trafik lambasının durumunu WiFi üzerinden bildiren bir kod geliştirilmesi ve bunun simülasyonunun yapılması gerekmektedir.

### 2. Ev Sıcaklık Bilgisi
Bu projede, sıcaklık sensörü aracılığıyla topladığınız verileri kablosuz bir iletişim protokolü kullanarak aktarmanız gerekiyor.

### 3. 220V AC Ampul Kablosuz Kontrolü
ESP32 tabanlı bir ampul devresi tasarlayıp bu devreyi simüle ediniz. Bu tasarımda röle kullanmanız gerekmektedir. Görselde yer alan gerçek bir ürün örneği, tasarım sürecinize ilham verebilir.

### 4. Ultrasonik İnsan Sayacı
HC-SR04 sensörü kullanarak gerçekleştirdiğiniz insan sayma sisteminden elde edilen verilerin, kablosuz iletişim aracılığıyla gerçek zamanlı olarak bir merkeze aktarılması gerekmektedir.

### 5. RFID Kapı Açma Sistemi (BONUS)
RFID'den gelen bilgileri Discord botuna ileten ve bu Discord botu aracılığıyla belirli ID'li kartlara izin verme veya kaldırma yeteneğine sahip bir sistem tasarlayınız. Discord botuna ek olarak farklı özellikler ekleyebilirsiniz.

### 6. MQTT İle Haberleşen Toprak Sulama Sistemi
MQTT protokolü kullanarak toprak nem sensörlerinden alınan verileri uzaktan kontrol eden bir sistem tasarlayınız.

## Kullanım

1. Her bir görev için gerekli olan bağlantıları yapın ve ilgili kodu Arduino IDE'de açın.
2. Arduino IDE üzerinden ESP32 kartınızı seçin (`Tools -> Board -> ESP32 Dev Module`).
3. Kodunuzu ESP32'ye yükleyin (`Upload` butonuna basarak).
4. Her bir projenin detaylı kullanım kılavuzunu ve açıklamalarını ilgili kod dosyalarında bulabilirsiniz.

## Katkıda Bulunma

Bu projeye katkıda bulunmak için lütfen bir pull request gönderin. Sorularınız veya önerileriniz için [email@example.com](mailto:email@example.com) adresinden bize ulaşabilirsiniz.

## Lisans

Bu proje MIT Lisansı altında lisanslanmıştır - detaylar için LICENSE dosyasına bakınız.

---

Bu challenge'ı tamamlamak için başarılar dileriz!
