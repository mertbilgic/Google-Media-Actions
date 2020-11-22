# Media Actions

## İçindekiler

1. [Feed Yapısına Genel Bakış](#feed-yapısına-genel-bakış)
2. [Collect information](#collect-information)
3. [Feed file requirements](#feed-file-requirements)
4. [Entity Türleri Arasındaki İlişki](#entity-türleri-arasındaki-ilişki)
5. [Kaynakça](#kaynakca)

#### Feed Yapısına Genel Bakış

Media Actions feed'i bir entity koleksiyonu içeren JSON ve entity katoloğunuzdaki bir öğeyi temsil eden bir schema.org nesnesidir:TVEpisode, TVSeries, film, şarkı, album, ve daha fazlasıdır.

#### Collect Information

Media Actions entegrasyonu entity feed gerektirir.Bir sağlayıcı olarak dikkat etmeniz gereken adımlar bulunmaktadır:

* Katalogdaki her entity'nin ayrıntılarını içeren JSON bir feed oluşturulmalıdır.
* Feed'i google'un düzenli olarak fetch edebileceği bir sunucuda veya bulut depolama hizmetinde bulundurulmalıdır.
* Kataloğunuz güncellendikçe feed'i güncel tutun.
* [Kalite kontrol](https://developers.google.com/actions/media/tools/quality-checklist) listesindeki tüm öğelerin tanımlandığından emin olun.

Öncelikle içeriğimizin entity tipini belirlememiz gerekir.Her entity tipinin farklı gereksinimleri vardır.

#### Feed File Requirements

Bir feed dosyası aşağıdaki gereksinimleri karşılamalıdır.

* Dosya uzantsı .json olmalıdır.
* Feed file şifrelenmelidir.
* Feed dosyası UTF-8 olarak encode edilmedilidir.
* Feed dosyası 1GB dan büyükse birden çok dosyaya bölünmelidir.(örneğin, tvepisodes_01.json, tvepisodes_02.json, vb.)
* Entity türüne göre dosyası oluşturması önerilmektedir.(tvseries.json, tvseasons.json, tvepisodes.json, movies.json, vb.)
* Dosya boyutu 1 GB'dan olduğu sürece istediğimiz kadar entity ekleyebiliriz

#### Entity Türleri Arasındaki İlişki

Bazı entity türleri, feed arasındaki ilişkiyi sağlamanızı gerektirir. Bu bilgiler, Google'ın içeriğinizin doğru sırasını ve yapısını kullanıcılara göstermesine ve bir kullanıcının sorgusu belirsiz olduğunda doğru içeriği belirlemesine yardımcı olur.

##### TvShow

* TVEpisode - Bir TV dizisinin tek bölümü
* TVSeries - Bir dizi bölüm içeren bir televizyon programı
* TVSeason - Bir TV dizisinin tek sezonu; bir sezon, aynı çalıştırmada yayınlanan bir grup bölüm içerir.

PartOfSeries ve partOfSeason özellikleri, TVShow entity türlerini birbirine bağlar.

##### Kaynakça
* https://developers.google.com/actions/media
