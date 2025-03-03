# Poglavlje X: Konstrukcijski elementi robota

## 1. Uvod
Robotika je interdisciplinarno područje koje objedinjuje mehaniku, elektroniku i računarstvo kako bi se stvorili inteligentni sustavi sposobni za autonomno ili poluautonomno djelovanje. Konstrukcija robota podrazumijeva pažljivo planiranje i integraciju ključnih elemenata koji omogućuju kretanje, percepciju, interakciju s okolinom i obavljanje specifičnih zadataka. Cilj ovog poglavlja je detaljno opisati osnovne konstrukcijske elemente robota, pružajući studentima temeljno razumijevanje njihove funkcionalnosti i primjene.

## 2. Glavne komponente robota
Razvoj robota zahtijeva integraciju više različitih komponenti, pri čemu svaka ima svoju specifičnu ulogu. Ove komponente mogu se podijeliti u nekoliko glavnih kategorija:

### 2.1. Mehanička struktura
Mehanička struktura robota čini njegovu osnovu i omogućuje fizičku interakciju s okolinom. Ključni dijelovi uključuju:
- **Okvir i tijelo robota** – Nosiva konstrukcija robota izrađena od materijala poput aluminija, čelika ili kompozitnih materijala, koji pružaju potrebnu čvrstoću i fleksibilnost.
- **Zglobovi i veze** – Komponente koje omogućuju kretanje robota, obuhvaćajući rotacijske (revolutivne) i translacijske (prizmatične) zglobove.
- **Krajnji efektor** – Završni element robota koji obavlja određeni zadatak, poput hvataljke, alata za zavarivanje ili 3D pisača.

### 2.2. Aktuatori
Aktuatori su komponente koje omogućuju pokretanje robota pretvarajući električnu, hidrauličku ili pneumatsku energiju u mehaničko gibanje.
- **Električni motori** – DC, servo i koračni motori koriste se za precizno upravljanje pokretima.
- **Hidraulički i pneumatski aktuatori** – Pogodni za sustave koji zahtijevaju veliku snagu i brzinu odziva.
- **Pametni aktuatori** – Integriraju senzore i upravljačke sustave radi povećanja preciznosti i autonomije.

### 2.3. Senzori
Senzori omogućuju robotima percepciju okoline, prikupljanje podataka i donošenje odluka na temelju njih.
- **Senzori položaja** – Enkoderi i potencijometri koriste se za mjerenje kuta rotacije ili translacije.
- **Senzori sile i dodira** – Pomažu robotima u prilagođavanju sile prilikom manipulacije objektima.
- **Vizualni senzori** – Kamere i LiDAR sustavi omogućuju robotsku viziju i mapiranje okoline.
- **Senzori okoline** – Uključuju ultrazvučne, temperaturne i infracrvene senzore za detekciju prepreka i uvjeta rada.

### 2.4. Upravljački sustav
Upravljački sustav robota sastoji se od računala i mikrokontrolera koji obrađuju podatke i donose odluke.
- **Mikroprocesori i mikrokontroleri** – Ključne komponente za obradu signala i izvršavanje algoritama.
- **Upravljačke jedinice u stvarnom vremenu** – Omogućuju brzo i precizno upravljanje kretanjem robota.
- **Operacijski sustavi za robotiku** – Sustavi poput ROS-a omogućuju razvoj modularnih i skalabilnih robotskih aplikacija.

### 2.5. Napajanje
Napajanje je ključno za autonomni rad robota, a odabir izvora energije ovisi o zahtjevima aplikacije.
- **Baterijski sustavi** – Litij-ionske (Li-Ion) i nikal-metal-hidridne (NiMH) baterije koriste se za napajanje mobilnih robota.
- **Alternativni izvori energije** – Solarni paneli i hidraulički sustavi koriste se u specijaliziranim robotskim primjenama.
- **Upravljanje potrošnjom energije** – Optimizacija potrošnje energije ključna je za povećanje autonomije robota.

### 2.6. Komunikacija i povezanost
Komunikacija između komponenti i s vanjskim sustavima ključna je za koordinaciju rada robota.
- **Ožičena komunikacija** – CAN bus, EtherCAT i USB omogućuju stabilnu razmjenu podataka unutar robota.
- **Bežična komunikacija** – Wi-Fi, Bluetooth i Zigbee koriste se za daljinsku kontrolu i umrežavanje robota.
- **Umreženi roboti i IoT integracija** – Povezivanje robota s cloud sustavima omogućuje naprednu analitiku i optimizaciju rada.

## 3. Mobilni roboti
Mobilni roboti su autonomni sustavi sposobni za kretanje u prostoru bez fiksne infrastrukture. Ovisno o načinu kretanja, dijele se na:

### 3.1. Kotačni roboti
Najčešće korišteni oblik mobilnih robota zbog jednostavne kontrole i energetske učinkovitosti. Ključni tipovi uključuju:
- **Diferencijalni pogon** – Roboti s dva nezavisna pogonska kotača koji omogućuju rotaciju i kretanje u svim smjerovima.
- **Omnidirekcijski roboti** – Koriste Mecanum kotače ili kuglične kotače za kretanje u bilo kojem smjeru bez potrebe za okretanjem.
- **Autonomna vozila** – Vozila opremljena senzorima (LIDAR, GPS, IMU) za navigaciju u stvarnom okruženju.

### 3.2. Hodajući roboti
Inspirirani prirodnim kretanjem, koriste noge umjesto kotača, što im omogućuje rad na nepristupačnim terenima.
- **Dvogodi roboti** – Antropomorfni roboti s dvije noge (npr. humanoidni roboti poput ASIMO-a).
- **Četveronožni roboti** – Stabilniji od dvonožnih, koriste se za istraživanje teških terena (npr. Boston Dynamics' Spot).
- **Višenožni roboti** – Hexapodi i drugi insektoidni roboti koji nude visoku stabilnost u pokretu.

### 3.3. Plutajući i zračni roboti
- **Podvodni autonomni roboti (AUVs)** – Koriste se za istraživanje oceana i podvodnih infrastruktura.
- **Dronovi (UAVs)** – Leteći roboti koji se koriste u nadzoru, isporuci i kartiranju terena.

Mobilni roboti imaju široku primjenu u industriji, logistici, medicini i vojnoj upotrebi, te su ključni u razvoju autonomnih sustava budućnosti.

## 4. Zaključak
Razumijevanje konstrukcijskih elemenata robota ključno je za razvoj naprednih autonomnih sustava. Svaka komponenta ima specifičnu ulogu u cjelokupnom radu robota, a njihova integracija omogućuje širok spektar primjena u industriji, medicini, logistici i istraživanju. Studenti koji ovladaju ovim temeljnim principima bit će spremni za daljnje proučavanje i razvoj inovativnih robotskih sustava.

