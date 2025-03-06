# Konstrukcijski elementi robota

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

### 2.7. Radni prostor robota

Radni prostor robota odnosi se na volumen unutar kojeg se njegov krajnji efektor može kretati. 

![image](https://github.com/user-attachments/assets/a09c856b-9fb3-474c-bf12-91934e8f14b3)


Ovisno o vrsti robota, radni prostor može imati različite oblike:

![image](https://github.com/user-attachments/assets/5690b9e7-7cf5-4f22-b146-920f2277c7c7)


- **Kartezijski radni prostor** – Pravokutni oblik, karakterističan za robote s prizmatičnim zglobovima.

- **Cilindrični radni prostor** – Nastaje kada robot koristi kombinaciju translacijskih i rotacijskih osi.

- **Sferni radni prostor** – Omogućuje velik domet i fleksibilnost, tipičan za robote s više rotacijskih zglobova.

- **Zglobni radni prostor** – Fleksibilan, ali ograničen zbog geometrije robotskih ruku.

Faktori koji utječu na radni prostor uključuju:

- **Broj stupnjeva slobode** – Više stupnjeva slobode omogućuje veći i složeniji radni prostor.

- **Geometrija zglobova** – Prizmatični zglobovi omogućuju linearno proširenje radnog prostora, dok rotacijski dodaju fleksibilnost.

- **Fizičke prepreke** – Okolina može ograničiti puni potencijal radnog prostora.

- **Programska ograničenja** – Upravljački sustavi mogu postaviti virtualne granice kako bi spriječili sudare i osigurali sigurnost rada.

Razumijevanje radnog prostora ključno je za dizajn robotskih sustava kako bi se optimizirala njihova funkcionalnost i efikasnost u specifičnim primjenama.

# Zglobovi robota

## Translacijski: Omogućava kretanje u jednoj osi.

![image](https://github.com/user-attachments/assets/b16891a9-f11e-454b-b18e-87835d7195e0)


## Rotacijski: Omogućava kretanje oko okomite osi.

![image](https://github.com/user-attachments/assets/46f483cb-1291-472e-b5c6-85cabe03e31b)


## Torzijski: Rotacija bez promjene relativnog položaja.

![image](https://github.com/user-attachments/assets/a1399842-2e99-4574-a4fa-8729ddae494d)


## Revolucijski: Rotacija oko osi koja je paralelna jednom članku.

![image](https://github.com/user-attachments/assets/8efb3584-15e0-49b6-bf2d-ac20a031dd93)


# Konfiguracije robota

Roboti se mogu konfigurirati na različite načine, ovisno o njihovoj namjeni i radnim zahtjevima. Različite konfiguracije omogućuju specifične prednosti u pogledu mobilnosti, stabilnosti, radnog prostora i primjene. Svaka konfiguracija prilagođena je određenim industrijskim procesima i uvjetima rada.

## Kartezijska konfiguracija

![image](https://github.com/user-attachments/assets/5f11ebcf-4334-411a-bb9e-f691601d3d04)


Tri translacijska zgloba, pravolinijsko kretanje.

- Tri translacijska zgloba
- Okomite osi
- Pravolinijsko kretanje
- Radni prostor je prizma
- Jednostavnost i robusnost
- Ograničeno kretanje i ograničeni doseg
- Izložene vodilice
- Primjena u aplikacijama pokupi i ostavi
- Sklapanje
- Rukovanje alatima


## Cilindrična konfiguracija

![image](https://github.com/user-attachments/assets/d7a04cf3-6735-4231-b205-2db0fd6eda5b)


- Prvi zglob torzijski, radni prostor između koncentričnih valjaka.

- Prednosti: Dobra čvrstoća, jednostavno podmazivanje.

- Nedostaci: Manja točnost, nemogućnost dosezanja objekata iznad sebe.

- Primjena: Lijevanje u kalupe, sklapanje.

## Polarna konfiguracija

![image](https://github.com/user-attachments/assets/eba63a7c-2a75-4b3b-9a27-ac5a2b6fac4f)


- Radni prostor između dviju koncentričnih sfera.

- Prednosti: Zaštićen pogon.

- Nedostaci: Složeno programiranje, niska točnost.

- Primjena: Lučno i točkasto zavarivanje.

## Artikulirana konfiguracija

![image](https://github.com/user-attachments/assets/83529632-4e0a-4944-b31f-742413c9bd27)


- Svi rotacijski zglobovi.

- Radni prostor kugla.

- Prednosti: Visoka upravljivost.

- Nedostaci: Složeno upravljanje.

- Primjena: Sklapanje, bojanje, zavarivanje.

## SCARA konfiguracija

![image](https://github.com/user-attachments/assets/56510146-b3bd-418b-a628-6c97c02948ed)


- Jedan translacijski zglob, paralelni rotacijski zglobovi.

- Prednosti: Visoka čvrstoća na vertikalnoj osi.

- Primjena: Montiranje, slaganje.

Komponente robotskih manipulatora

- Krajnji djelovatelj (End Effector)

- Hvataljke: Mehaničke, usisne, magnetske.

- Mehaničke: Realizirane s dva ili tri prsta.

- Usisne: Rad pomoću vakuuma.

- Magnetske: Samo za feromagnetske materijale.

- Alati: Bušenje, bojanje, zavarivanje.

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

