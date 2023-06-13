<h3>Yapay Sinir Ağları Hakkında</h3>
<p>Yapay sinir ağları, biyolojik sinir hücrelerinin yapısından ve çalışmasından esinlenerek oluşturulan bir yapay zeka tekniğidir. 
Yapay sinir ağları, birbirleriyle bağlantılı katmanlardan oluşur. Her katman bir dizi yapay sinir hücresi nöronlardan oluşur. Bu nöronlar, ağırlıklı bağlantılar aracılığıyla birbirine bağlanır. Ve her bir nöron kendi belleğine sahip işlem elemanlarından oluşan paralel ve dağıtılmış bilgi işleme yapılarıdır. 
Yapay sinir ağlarında bilgilerin işlenmesi paralel olarak gerçekleşir. Bu sebeple taşınan bilgiler birbirinden bağımsızdır. Paralel çalışma nöronlar arasında bilgi akış hızını da arttırmaktadır.
Yapay sinir ağları sahip olduğu çeşitli özellikler sayesinde bir çok farklı yönteme göre daha etkin süreçler geçirir. Tabi ki bunun neticesinde geniş bir kullanım alanına sahiptir ve birçok farklı problemin çözümünde etkili olabilir. Örneğin, Görünte ve Ses işlemede, Doğal Dil İşleme, Robotik ve Kontrol Sistemlerinde, Sınıflandırma ve Tahminleme gibi birçok problem için kullanılabilir.
</p>

<p>Yapay sinir ağlarının birbirine bağlı katmanlardan oluştuğunu söylemiştik. Genellikle üç temel katmandan oluşan yapısı vardır. Bu katmanlar hakkında biraz bilgi edinelim.</p>
<ul>
  <li>
    <p>
      Girdi katmanı, verilerin sinir ağımıza girdi olarak verildiği katmandır. Bu katmandaki nöron sayısı verilerimizdeki toplam özellik sayısı adetindedir.      </p>      
 </li>
 <li>
   <p>
     Gizli katman, oluşturulan mimariye göre birden fazla gizli katman bulunabilir ve her katmanda farklı sayıda nöron bulunabilir.
     Giriş katmanından gelen veri bu katmanda çeşitli işlemler geçirir. Her katmanın çıktısı, bir  önceki katmanın çıktısının o katmanın ağırlıkları ile          çarpılır ve bias değeri eklenir. Daha sonra ağa non-lineerlik özelliği getiren aktivasyon fonksiyonu ile hesaplanır.
   </p>
   <p>
     Aktivasyon fonksiyonları hakkında kısaca bilgi vermeyi istiyorum.
     Aktivasyon fonksiyonları modelimizin öğrenme aşamasında çok önemli yer tutar. Bu fonksiyonlar sinir ağımıza nonlineerlik özelliği kazandırır. Aktivasyon
     fonksiyonları, nöronlar arasında gerçekleşen işlemleri standardize eder. Örneğin aktivasyon fonksiyonundan önce gerçekleşen ağırlıklar ile çarpıp bias
     değeri eklendikten sonra oluşan sonuç -∞ ile +∞ arasında olur. Bu sonucu örneğin sigmoid aktivasyon fonksiyonundan geçirdiğimizde sonuç 0 ile 1 arasında       bir değer alır. 
   </p>  
  </li>  
  <li>
    <p>
      Çıktı katmanı, 	yapay sinir ağının son katmanıdır ve genellikle probleme bağlı olarak farklı yapılar ve sayıda nöron içerebilir. Eğer sinir ağımız           sınıflandırma yapıyorsa sınıf sayısı kadar nöron bulunur. Veya bir regresyon probleminde tek bir çıkış nöronu olabilir.
    </p>  
  </li>  
</ul>  

<h3>Yapay Sinir Ağları İçin Optimizasyon Algoritmaları</h3>
<p>Optimizasyon algoritmaları temel olarak oluşturduğumuz modelin performansını ve tahmin yeteneklerini arttırmak için kullanılır. Bu algoritmalar hedef fonksiyonunu (genellikle maliyet fonksiyonu) minimize etmek için modelin parametrelerini günceller. Burada en yaygın optimizasyon algoritmalarını anlattım.</p>
<ul>
  <li>
    <h4>Gradient Descent</h4>
    <p>
      Gradient Descent algoritması, en temel ve en çok kullanılan optimizasyon algoritmasıdır. Sınıflandırma ve lineer regresyon gibi birçok alanda                 kullanılır. Gradient Descent temel olarak bir hedef fonksiyonunun birinci dereceden türevine bağlı olan bir optimizasyon algoritmasıdır.
      Bu algoritmanın amacı fonksiyonun parametrelerini devamlı güncelleyerek fonksiyonun minimum noktasına ulaşmaktır. Algoritma, hedef fonksiyon üzerinde         rastgele bir noktadan başlayarak fonksiyonun global minimum noktasına ulaşıncaya kadar adım adım ilerleyen yinelemeli bir algoritmadır. Buradaki adım         adım   ilerleme, öğrenme katsayısı ile ilişkilidir.
    </p>  
    <p>
      <b>Öğrenme Oranı (Learning Rate)</b>, hedef fonksiyonun global optimum noktasını arama sürecinde modelin öğrenme işlemi için adım büyüklüğünü ve bunun       sonucunda ağırlıklarda yapılacak değişiklik miktarını etkileyen bir sayıdır. Öğrenme oranının çok yüksek veya çok düşük olmasının bazı avantajları ve         dezavantajları bulunmaktadır. Öğrenme oranının çok yüksek olması öğrenme sürecinde sapmalara, çok düşük olması gereksiz iterasyonlar ile modelin             öğrenme süresini uzatabilir hatta bu yıllar alabilir.
    </p>
  </li>
  <li>
    <h4>Stokastik Gradyan (Stochastic Gradient Descent)</h4>
    <p>
      Gradient Descent’ in bir çeşididir. Model parametreleri her eğitim iterasyonunda hesaplanan kayıptan sonra değiştirilir. Bu nedenle Gradient Descent’ e       göre daha sık model parametrelerini günceller. Bu da modelin eğitilme süresini pozitif etkiler diyebiliriz.
    </p>
  </li>
   <li>
    <h4>Adagrad</h4>
    <p>
      Şu ana kadarki optimizasyon algoritmalarının en büyük dezavantajı öğrenme oranının tüm parametreler ve her döngü için sabit olmasıydı. Adagrad ile bu         sorun artık ortadan kalkıyor. Bu algoritma öğrenme katsayısını her iterasyonda güncelleyerek daha uygun sonuçlar verir.
    </p>
  </li>
  <li>
    <h4>Adam</h4>
    <p>
      Adam algoritması, Gradient Descent’in geliştirilmiş bir versiyonudur. Bu algoritma parametrelerin optimize edilmesi için adaptif öğrenme hızlarını           kullanır ve momentumu dikkate alır. Bu sayede hızlı bir şekilde minimum noktaya ulaşır. Diğer algoritmalardan en önemli farkı yön bilgisine de sahiptir
    </p>
  </li>
</ul> 

