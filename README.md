<div align="center">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQV_kyuXXaKw0AoIVpBkgtMk_9tFt8wWchunb_NwyRFJQ&s=10" alt="Vitess Logo" width="200">
  
  # Vitess-Docs
  
  [![CNCF Graduated](https://img.shields.io/badge/CNCF-Graduated-blue.svg)](https://cncf.io)
  [![Language](https://img.shields.io/badge/Language-Turkish-red.svg)](#)
</div>

---

### 📖 Hakkında

Vitess, **YouTube** ekibinin karşılaştığı MySQL ölçeklenebilirlik sorunlarını çözmek için 2010 yılında oluşturuldu.

Vitess, YouTube’un bu mantığı uygulama kaynak kodundan kaldırmasına ve uygulama ile veritabanı arasında bir proxy yerleştirerek veritabanı etkileşimlerini yönlendirmesine ve yönetmesine olanak sağladı. O zamandan beri YouTube, kullanıcı tabanını 50 kattan fazla büyüttü ve sayfa sunma, yeni yüklenen videoları işleme ve daha fazlasını yapma kapasitesini büyük ölçüde artırdı. Daha de önemlisi, Vitess ölçeklenmeye devam eden bir platformdur. 

Şubat 2018'de Teknik Gözetim Komitesi (*Technical Oversight Committee - TOC*), Vitess’i bir **CNCF kuluçka (CNCF incubation)** projesi olarak kabul etme kararı aldı. Vitess, Kasım 2019'da Kubernetes, Prometheus, Envoy, CoreDNS, containerd, Fluentd ve Jaeger’e katılarak **CNCF’den mezun olan (Graduated) sekizinci proje** oldu. 

> 💡 **Not:** Bu doküman Vitess'in resmi sitesindeki teknik dökümanın tarafımca Türkçe'ye çevirimi yapılan versiyonudur. Sürekli olarak yeni versiyonlar eklenecektir.

🎯 **Amaç:** Bu platformu kendi özel ağında kurup database sharding operasyonlarını yürütmek isteyen kişi ve kurumların teknolojiye hakim olabilmesi için oluşturulmaktadır.

---

### 🛠️ Ön Gereksinimler (Teorik Konular)

Bu teknolojiye hakim olmadan önce tam olarak kavramış olmanız gereken teorik mimari konular aşağıda şematize edilmiştir. Belirtilen teorik konuları Designing Data Intensive Application Kitabının 2. Kısmını okuyarak bu konulara hakimiyet ve derinlemesine bir bakış açısı kazanabilirsiniz.

```mermaid
graph LR
    Root[Teorik Konular] --> Rep[Database Replication]
    Root --> Shard[Database Sharding]
    Root --> Trans[Transactions]

    Rep --> R1(Single-lead Replication)
    Rep --> R2(Multi-lead Replication)
    Rep --> R3(Leaderless Replication)
    Rep --> R4(The Trouble With Replication Lag)

    Trans --> T1(Atomicity)
    Trans --> T2(Consistency)
    Trans --> T3(Isolation)
    Trans --> T4(Durability)

    style Root fill:#f9f,stroke:#333,stroke-width:2px
    style Rep fill:#bbf,stroke:#333,stroke-width:1px
    style Trans fill:#bbf,stroke:#333,stroke-width:1px
    style Shard fill:#bfb,stroke:#333,stroke-width:1px