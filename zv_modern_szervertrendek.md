# 1. Az infrastruktúra tervezési követelmények modern szerverkörnyezetekben (MST 01 - Introduction diasor 3-14 dia)
## **Skálázhatóság**
A növekvő erőforrásigény kezelése, anélkül, hogy a teljesítményt, vagy a megbízhatóságot veszélyeztetné.

**Horizontális: „scale out” – több szerver vagy node hozzáadása a rendszerhez. Pl.: több webszerver hozzáadása egy weboldalhoz.**
- előnyök:
    - egyszerű implementálni hardver szinten;
    - költséghatékony a megnövekedett forgalom kezelésére
    - magas rendelkezésre állás
- hátrányok:
    - kompliáláltabb
    - network latency esélyes
    - magasabb menedzsment overhead-et igényel
- mikor használjuk:
    - ha kiszámíthatatlan a forgalom
    - nagy skálázhatóságú applikációknál
    - elosztott rendszereknél

**Vertikális: „scale up” – hardveres vagy szoftveres upgrade. Pl.: több RAM, CPU, storage, stb.**
- előnyök:
    - egyszerűbb menedzsment és megvalósítás szoftveres szinten
    - bizonyos leterheltségnél jobb teljesítmény
    - kisebb rendszereknél előnyösebb
    - rövid távon lehet költséghatékonyabb
- hátrányok:
    - limitált skálázhatóság
    - nagyfokú fejlesztésnél drága lehet
    - teljesítménybeli problémákat okozhat
- mikor használjuk:
    - kisebb rendszereknél specifikus rendszerkövetelményekkel
    - kiszámítható forgalom esetén
    - amikor a költség elsődleges szempont

**Skálázhatósági kihívások**
- Teljesítményszűk keresztmetszetek léphetnek fel, ha a rendszer egyes összetevői túlterheltek.
- Az adattárolás és -kezelés kihívást jelenthet a rendszerek növekedésével.
- A hálózati kapacitás korlátai a forgalom növekedésével akadályozhatják a teljesítményt.
- Az infrastruktúra nem megfelelő tervezése skálázhatósági problémákhoz vezethet.

## **Hatékonyság**
A hatékonyság azt jelenti, hogy egy rendszer képes a céljait az erőforrások minimális pazarlása mellett elérni.

**A hatékonyságot befolyásoló fő tényezők:**
- Infrastruktúra tervezés
    - Hálózatépítés: Hálózatok tervezése és konfigurálása a komponensek közötti hatékony kommunikáció biztosítása érdekében.
    - Hardver: A megfelelő hardver (szerverek, tárolók, hálózati eszközök) kiválasztása a teljesítménykövetelmények és a skálázhatósági igények alapján.
    - Szoftver: Az alkalmazás támogatásához megfelelő operációs rendszerek, adatbázisok és köztes szoftverek kiválasztása.
- Erőforrás-felhasználás
    - Méretezés: A szerverek és egyéb erőforrások megfelelő méretezése a jelenlegi és jövőbeli igények kielégítésére.
    - Automatikus skálázás: Az erőforrások elosztásának automatikus beállítása a munkaterhelés ingadozásai alapján a költségek optimalizálása érdekében.
    - Erőforrás-optimalizálás: A kihasználatlan erőforrások azonosítása és megszüntetése a hatékonyság javítása érdekében.
- A méretezhetőség és hatékonyság optimalizálása
    - Cache: A gyakran használt adatok tárolása a memóriában a gyorsabb lekérdezés érdekében, csökkentve az adatbázis- vagy hálózati keresések szükségességét.
    - Terheléskiegyenlítés: A munkaterhelés egyenletes elosztása több kiszolgáló vagy példány között a szűk keresztmetszetek elkerülése és a teljesítmény javítása érdekében.
    - Teljesítményhangolás: A kód, az adatbázis-lekérdezések és az infrastruktúra-összetevők optimalizálása a hatékonysági problémák azonosítása és kiküszöbölése érdekében.
    - Aszinkron feldolgozás: A feladatok aszinkron kezelése a reakciókészség javítása és a késleltetés csökkentése érdekében.

## **Rugalmasság**
A rugalmasság a rendszer azon képességére utal, hogy jelentős erőfeszítés nélkül képes alkalmazkodni a változásokhoz.

**A rugalmasságot befolyásoló fő tényezők:**
- Kihívások
    - Örökölt rendszerek: Az új rendszerek integrálása a meglévő, örökölt rendszerekkel kihívást jelenthet.
    - Szoros csatolás: A szorosan összekapcsolt rendszerek nehezen módosíthatók és adaptálhatók.
    - Forgalmazóhoz kötöttség: Az egyes szállítóktól való függés korlátozhatja a rugalmasságot.
    - Technikai adósság: A rossz tervezési döntések és a technikai adósságok akadályozhatják a rugalmasságot.
- Technikák
    - Moduláris tervezés: A rendszerek kisebb, független modulokra bontása.
    - Mikroszolgáltatási architektúra: Az alkalmazások apró, független szolgáltatásokra bontása.
    - Felhőalapú környezetek: A skálázhatóság és az igény szerinti rendelkezésre bocsátás miatt eredendően rugalmasak.
    - DevOps gyakorlatok: Az automatizálás és a folyamatos szállítás lehetővé teszi a változások gyors telepítését.

## **Konvergens infrastruktúrák**
**Több informatikai funkció egyetlen, integrált platformon történő egyesítése**
- Hálózatok: Az adat-, tároló- és számítási hálózatok egyetlen hálózatba történő egyesítése.
- Tárolás: A tárolási erőforrások (SAN, NAS, DAS) egységes poolba történő integrálása.
- Compute: Számítási erőforrások (szerverek, virtuális gépek) konszolidálása egy közös platformon.
- Management: Az összes komponens központosított kezelése az egyszerűsített adminisztráció érdekében.
- Virtualizáció: A virtualizációs technológia kihasználása virtualizált erőforrások létrehozásához és kezeléséhez.

**A konvergencia szintjei**
- Konvergens infrastruktúra (CI): A kiszolgálók, a tárolás és a hálózat egyetlen integrált platformban történő egyesítése.
- Hiper-konvergens infrastruktúra (HCI): A számítás, a tárolás és a hálózat egyetlen, szoftveresen definiált eszközbe történő integrálása.
- Előnyök:
    - Jobb hatékonyság: Csökkentett összetettség és jobb erőforrás-kihasználás.
    - Fokozott rugalmasság: Skálázhatóság és alkalmazkodóképesség a változó üzleti igényekhez.
    - Egyszerűsített irányítás: Központosított irányítás és kezelés.

---

# 2. A mikroszolgáltatás-architektúra, API-vezérelt interfészek és aszinkron feldolgozás jellemzői, kihívásai (MST 01 - Introduction diasor 15-24 dia)
A mikroszolgáltatási architektúra olyan tervezési megközelítés, amely az alkalmazásokat kisebb, független szolgáltatásokra bontja.

## **Fő jellemzők:**
- Korlátozott kontextus: Minden mikroszolgáltatás egy adott üzleti területre vagy képességre összpontosít.
- Más néven: területvezérelt tervezés (DDD - domain driven design).
- Laza csatolás: A mikroszolgáltatások jól definiált API-kon keresztül kommunikálnak, minimalizálva a függőségeket.
    - Az API-knak egyértelműnek, jól dokumentáltnak és könnyen hozzáférhetőnek kell lenniük
    - Adattulajdonlás: A mikroszolgáltatások rendelkeznek a saját adat- és perzisztencia-mechanizmusokkal.
    - Hibaelszigetelés: Egy mikroszolgáltatás hibája nem befolyásolhatja az egész alkalmazást.
    - Függetlenül telepíthető: Minden egyes mikroszolgáltatás önállóan telepíthető és frissíthető.

**Előnyök**
- Jobb skálázhatóság: Minden egyes mikroszolgáltatás önállóan skálázható az egyedi igényeknek megfelelően.
- Fokozott rugalmasság: Egy mikroszolgáltatás hibája nem érinti az egész alkalmazást.
- Gyorsabb fejlesztés és telepítés: A kisebb, koncentrált csapatok hatékonyabban fejleszthetik és telepíthetik a mikroszolgáltatásokat.
- Technológiai rugalmasság: A mikroszolgáltatások különböző technológiák és programozási nyelvek felhasználásával építhetők.
- Könnyebb karbantartás: Egy mikroszolgáltatáson változtatásokat lehet végrehajtani anélkül, hogy az egész alkalmazást érintené.

**Kihívások**
- Megnövekedett komplexitás: Több mikroszolgáltatás kezelése összetettebb lehet, mint egy monolitikus alkalmazásé.
- Elosztott rendszerek kihívásai: Olyan problémák kezelése, mint az elosztott tranzakciók, az adatkonzisztencia és a hálózati késleltetés.
- Tesztelés és hibakeresés: Az elosztott rendszerek tesztelése és hibakeresése kihívást jelenthet.
- Orchestrálás és koreográfia: A mikroszolgáltatások közötti kölcsönhatások koordinálása.

## **Főbb mikroszolgáltatás-tervezési területek**
**Technológia Stack**
- Konténerizáció: Konténerek (pl. Docker) használata mikroszolgáltatások és függőségeik csomagolására.
- Orchestrálás: Olyan eszközök használata, mint a Kubernetes a mikroszolgáltatások kezelésére és telepítésére.
- Szolgáltatási háló: A mikroszolgáltatások közötti kommunikáció kezelésére szolgáló dedikált infrastrukturális réteg.
- API Gateway: Központi belépési pont az API-forgalom és a biztonság kezelésére.

**Kommunikáció**
- RESTful API-k: HTTP és JSON a kommunikációhoz
- gRPC API-k: nagy teljesítmény és alacsony késleltetés
- Message várólisták: Aszinkron kommunikáció és szétválasztás
- Eseményvezérelt architektúra: Események alapján történő akciók indítása

**Adatkezelés**
- Decentralizáció: minden mikroszolgáltatás a saját adataihoz tartozik.
    - Adatintegráció: Több mikroszolgáltatásból származó adatok integrálása szükség esetén.
- Tranzakciók: 
    - Végleges konzisztencia: idővel minden replika végül ugyanazt a frissített adatot fogja tartalmazni.
    - kétfázisú commit (2PC): előkészítési fázis, commit vagy abort fázis.

## **RESTful APIs**
**REST:** ***RE***presentational ***S***tate ***T***ransfer – more than „JSON over HTTP”

**Állapot nélküli kommunikáció:**
- Minden ügyféltől a kiszolgálóhoz érkező kérésnek tartalmaznia kell minden olyan információt, amely szükséges ahhoz, hogy a kiszolgáló teljesíteni tudja a kérést.
- A kérések között az ügyfélkörnyezet nem tárolódik a kiszolgálón, ami egyszerűbb kiszolgálótervezést és jobb skálázhatóságot tesz lehetővé.

**Egységes interfész:**
- A szabványosított rendszerinterakciókat egységes műveletsorozat és konvenciók segítik elő.
- A HTTP-módszereket, például a GET, POST, PUT, DELETE kéréseket használja az erőforrásokkal végzett műveletek végrehajtásához.

**Erőforrás-alapú:**
- Egy RESTful API-ban minden erőforrásnak minősül, amelyet egy egyedi URI (Uniform Resource Identifier) azonosít.
- Az erőforrások közé tartozhatnak objektumok, adatbejegyzések és valós entitások virtuális reprezentációi.

**Idempotens**
- Az idempotens művelet többszöri végrehajtás esetén is ugyanazt az eredményt adja.
- Biztosítja a biztonságos API-interakciókat; például a PUT és DELETE kérések általában idempotensek.

**Cache-elhető**
- A kiszolgálótól érkező válaszok implicit vagy explicit módon cache-elhetőnek vagy nem cache-elhetőnek vannak definiálva.

**Verziózott**
- Több API-verziót támogat a visszafelé kompatibilitás és az iteratív frissítések megkönnyítése érdekében.
- URI-k, egyéni fejlécek vagy médiatípus verziókezelési stratégiák segítségével érhető el.

**Reprezentáció-orientált**
- Az erőforrások függetlenek a reprezentációjuktól, lehetővé téve különböző formátumok, például JSON, XML vagy HTML használatát.
- Az ügyfél a HTTP fejlécek, például az Accept és a Content-Type segítségével konkrét médiatípusokat kérhet.

**Rétegelt**
- Az architektúra hierarchikus rétegekre tagolódik a skálázhatóság és a kezelés javítása érdekében.
- Rétegeket lehet hozzáadni olyan dolgok kezeléséhez, mint a biztonság, a terheléselosztás és a megosztott gyorsítótárak.

**Támogatja a HATEOAS-t (Hypermedia as the Engine of Application State).**
- Az ügyfelek a HTTP-válaszban található hipermédia linkeken keresztül navigálnak az alkalmazásban.
- Drasztikusan csökkenti a szerverrel való interakcióra vonatkozó, hard-kódolt információk szükségességét.

## **gRPC - Remote Procedure Calls**

**Protokoll és szállítás:**
- A gRPC a HTTP/2-t használja szállítási protokollként, lehetővé téve a bináris átvitelt és a multiplexelést.
- A RESTful API-k jellemzően a HTTP/1.1-re támaszkodnak, és szövegalapú formátumokat, például JSON-t vagy XML-t használnak az adatcseréhez.

**Adatok szerializálása:**
- A gRPC kihasználja a protokollbuffereket (Protobuf), amelyek az adatokat kompakt bináris formátumba szerializálják, ezzel növelve a teljesítményt.
- A RESTful API-k gyakran használnak JSON-t, amely szövegalapú és ember által olvasható, de a bináris formátumokhoz képest nagyobb méretű.

**Kommunikációs stílus:**
- A gRPC különböző kommunikációs típusokat támogat, beleértve az unáris, az ügyfél-, a kiszolgáló- és a kétirányú streaminget.
- A RESTful API-k elsősorban egy állapotmentes kérés-válasz modellt használnak, és többnyire szinkron interakciókra támaszkodnak.

**Szolgáltatás meghatározása:**
- proto fájlokat használ a szolgáltatási szerződések definiálására, lehetővé téve az automatikus kódgenerálást.
- A RESTful API-k gyakran manuális dokumentációt és definíciót igényelnek, például az OpenAPI specifikációk használatával.

**Biztonsági jellemzők:**
- A gRPC eredendően támogatja a TLS-t használó biztonságos kapcsolatokat, és képes integrálni másfajta hitelésítési eljárásokat, mint pl. az OAuth.
- A RESTful API-kat szintén lehet TLS-szel biztosítani, de a hitelesítési mechanizmusok kifejezettebb beállítást igényelhetnek.

**Felhasználási esetek:**
- A gRPC jól alkalmazható mikroszolgáltatási architektúrákhoz, alacsony késleltetésű környezetekhez és valós idejű kommunikációs igényekhez.
- A RESTful API-kat általában webszolgáltatásokhoz, nyilvános API-khoz és olyan alkalmazásokhoz használják, ahol az egyszerűség és az olvashatóság az elsődleges szempont.

---

# 3. Automatizálás és DevOps jellemzői, kihívásai, koncepciói modern szerverkörnyezetekben (MST 01 - Introduction diasor 25-31 dia)
Az **automatizálás** magában foglalja a technológia használatát a feladatok minimális emberi beavatkozással történő elvégzésére.
**Jelentőssége:**
- Hatékonyság: Csökkenti a kézi munkát és felgyorsítja a folyamatokat.
- Következetesség: Biztosítja, hogy a feladatokat mindig ugyanúgy hajtsák végre, csökkentve a hibák számát.
- Skálázhatóság: Lehetővé teszi a folyamatok egyszerű növelését vagy csökkentését.

A **DevOps** olyan gyakorlatok összessége, amely a szoftverfejlesztést (Dev) és az IT-üzemeltetést (Ops) egyesíti a fejlesztési életciklus lerövidítése és a kiváló minőségű szoftver folyamatos szállítása érdekében.
**Jelentőssége:**
- Együttműködés: Elősegíti a fejlesztési és üzemeltetési csapatok közötti együttműködés kultúráját.
- Folyamatos szállítás: Lehetővé teszi a gyakori és megbízható szoftverkiadásokat.
- Javított minőség: Automatizált tesztelést és felügyeletet integrál a kiváló minőségű szoftver biztosítása érdekében.

## **DevOps kihívások**

**Kulturális váltás:**
- Ellenállás a változással szemben: A csapatok ellenállhatnak az új gyakorlatok és eszközök átvételének.
- Együttműködés: A hagyományosan elszigetelt csapatok közötti együttműködés ösztönzése nehéz lehet.

**Eszközök integrálása:**
- Kompatibilitási problémák: A különböző eszközök és technológiák integrálása összetett lehet.
- Karbantartás: Az eszközök frissítése és egymással való kompatibilitásának fenntartása folyamatos erőfeszítést igényel.

**Biztonsági aggályok:**
- Sebezhetőségkezelés: Az automatizált folyamatok új biztonsági réseket vezethetnek be.
- Megfelelés: Az ipari szabványoknak és szabályozásoknak való megfelelés biztosítása kihívást jelenthet.

**Készségbeli hiányosságok:**
- Képzés: Az automatizálás és a DevOps gyakorlatok bevezetéséhez és kezeléséhez szükséges készségek hiányozhatnak a csapatokból.
- Felvétel: Nehéz lehet a megfelelő készségekkel rendelkező, képzett személyzetet találni.

**Komplexitás:**
- Infrastruktúra-menedzsment: Az összetett infrastruktúra és környezetek kezelése megterhelő lehet.
- Monitoring és naplózás: A hatékony felügyeleti és naplózási megoldások bevezetése gondos tervezést igényel.

**Költségek:**
- Kezdeti beruházás: Az automatizálás és a DevOps-gyakorlatok bevezetésének kezdeti költségei magasak lehetnek.
- Folyamatos költségek: A folyamatos karbantartás és frissítések folyamatos költségekkel járhatnak.

## **Kulcsfontosságú automatizálási és DevOps-technikák**

**Infrastruktúra mint kód (IaC):**
- A számítástechnikai infrastruktúra kezelése és rendelkezésre bocsátása fizikai hardverkonfiguráció helyett gépileg olvasható szkriptek segítségével.
- Előnyök: Az infrastruktúra verzióvezérelt, skálázható és megismételhető környezetbeállítások, kevesebb kézi konfiguráció.

**Folyamatos felügyelet:**
- Az alkalmazások és az infrastruktúra teljesítményének, hibáinak és biztonsági problémáinak valós idejű nyomon követésére szolgáló eszközök alkalmazása.
- Előnyök: Proaktív problémaérzékelés, gyorsabb válaszidő, megelőző karbantartás automatikus figyelmeztetések révén.

**Automatizált tesztelés:**
- Szkriptek vagy eszközök használata előre meghatározott tesztek ismételt végrehajtására a kód funkcionalitásának ellenőrzése érdekében.
- Tesztelési típusok: Unit tesztek, integrációs tesztek, funkcionális tesztek és teljesítménytesztek.
- Előnyök: Csökkenti az emberi hibákat, felgyorsítja a tesztelési folyamatokat és növeli a kód megbízhatóságát.

## **CI/CD**

**Folyamatos integráció (CI):**
- A kódváltozások automatikus integrálása és tesztelése egy megosztott tárolóban.
- Cél: A problémák korai felismerése, a kódminőség javítása és a fejlesztési munkafolyamatok egyszerűsítése.
- Közös eszközök: Jenkins, Travis CI, GitLab CI. 
- Előnyök: Csökkenti az integrációs kockázatokat, megkönnyíti a gyors visszajelzést és biztosítja a kód stabilitását.

**Folyamatos szállítás (CD):**
- A tesztelt kód folyamatos szállítása a termeléshez hasonló környezetekbe.
- Cél: Biztosítani, hogy a szoftver bármikor telepíthető legyen.
- Közös eszközök: Spinnaker, Argo CD, GitLab.
- Előnyök: Minimális telepítési kockázatok, gyorsítja a piacra kerülési időt, lehetővé teszi a gyors visszaállítási stratégiákat.

## **Támogató eszközök és szolgáltatások**
- Felhőplatformok (pl. AWS, Azure, GCP)
- Konténerizáció (pl. Docker, Kubernetes)
- Orchestrálás (pl. Kubernetes, Apache Mesos)
- Konfigurációkezelés (pl. Ansible, Puppet, Chef)
- CI/CD pipelines (pl. Jenkins, GitLab CI/CD)

---

# 4.	Virtualizációs megoldások és lehetőségek modern szerverkörnyezetekben (MST 02 - Virtualization and Containerization diasor 3-15 dia)
## **Virtualizáció**

**A virtualizáció a hardveres erőforrások, például a CPU-k, a tárolók és a hálózatok virtuális példányait hozza létre.**
- Ezek a virtuális gépek (VM-ek) elszigetelt környezetként futnak egyetlen fizikai kiszolgálón.
- Ez csökkenti a szerverek kihasználatlanságát és csökkenti a hardverköltségeket az adatközpontokban.

**Hypervisor-technológiák:**
- A hipervizor a VM-eket a rendszer erőforrásainak kiosztásával és az elszigetelés biztosításával kezeli.
- Gyakori hipervizorok:
    - 1. típus (bare metal, önálló)
    - 2. típus (hosztolt, hoszt-vendég)

## **A virtualizáció előnyei**
**A virtualizáció típusai:**
- Szerver virtualizáció,
- Hálózati virtualizáció,
- Tároló virtualizáció.

**Mindegyik típus az IT-infrastruktúra egy adott aspektusát célozza meg a jobb skálázhatóság, rugalmasság és erőforrás-kezelés érdekében.**

**Előnyök:**
- A modern szerverarchitektúrák előnyeit a gyorsabb rendelkezésre bocsátás és a dinamikus skálázás jelenti.
- A virtualizáció a katasztrófa utáni helyreállítást is támogatja azáltal, hogy lehetővé teszi a VM-ek gyors migrációját alternatív hosztokra.

## **VMware**
**VMware ESXi**
- hipervizor, amely közvetlenül a szerver hardveren fut, host operációs rendszer nélkül.

**Virtuális gépek (VM-ek)**
- Az ESXi kiszolgálókon futó VM-ek elszigeteltek, de megosztják a mögöttes hardver erőforrásokat.

**Adattárolók**
- a VM-fájlok, -képek és -konfigurációk tartós tárolására használt tárolók.
- lehetnek helyi lemezeken, hálózati tárolókon (NAS) vagy tárolóhálózatokon (SAN).

**vSphere Suite**
- kezeli a teljes virtualizációs infrastruktúrát (több fizikai szerver)
- központosított VM-kezelés
- erőforrás-optimalizálást biztosít

**vMotion**
- lehetővé teszi a futó VM-ek élő migrációját az ESXi hosztok között a szolgáltatás megszakítása nélkül.
- kulcsfontosságú a VMware-környezetek rendelkezésre állásának és rugalmasságának fokozásához

## **Kernel-alapú virtuális gép (KVM)**
**KVM**
- nyílt forráskódú, a Linux kernelbe épített hypervisor

**QEMU (Quick Emulator)**
- A QEMU a hardverkomponenseket emulálja, míg a KVM hardverbővítésekkel gyorsítja a teljesítményt.
- A KVM-et gyakran használják a QEMU mellett a teljes körű virtualizáció biztosítására.

**Virtuális gépek (VM-ek)**
- dedikált virtuális CPU-kkal, memóriával, hálózattal és tárolóval rendelkeznek, amelyeket a hoszt kezel.

**Libvirt**
- egy magasabb szintű menedzsment API a KVM-mel való interakcióhoz
- absztrahálja a virtualizációs menedzsmentet, és általában olyan feladatokra használják, mint a VM telepítés és erőforrás kiosztás.
- az olyan eszközök, mint a virt-manager és a virsh a Libvirt-et használják a VM-ek egyszerű vezérlésére.

**Tárolási poolok és kötetek**
- a tároló poolok olyan tárolási erőforrásokat aggregálnak, mint a nyers lemezpartíciók, SAN vagy NAS.

## **Proxmox VE (Virtual Environment)**
**Ingyenes, nyílt forráskódú platform a virtuális gépek (VM-ek) és konténerek kezelésére.**
- KVM (Kernel-alapú virtuális gép) a teljes virtualizációhoz
- LXC (Linux Containers) a konténeralapú virtualizációhoz

**Webalapú kezelőfelület**
- lehetővé teszi a rendszergazdák számára a VM-ek, konténerek és tárolókonfigurációk létrehozását, rendelkezésre bocsátását és felügyeletét.

**Klaszterkezelés**
- több csomópont központosított kezelése egyetlen felületről
- VM-ek kiegyensúlyozása és migrálása a csomópontok között

**Biztonsági mentés/visszaállítás**
- lehetővé teszi a rendszeres, inkrementális vagy teljes VM biztonsági mentést.

**Nagyfokú rendelkezésre állás (HA)**
- A HA cluster-ek biztosítják, hogy a VM-ek hardverhibák esetén automatikusan egészséges csomópontokra vándoroljanak.

**Többféle hálózati modell**
- virtuális hálózatok, VLAN-ok és bridge-ek
- összetett és elszigetelt hálózati konfigurációk VM-ek és konténerek számára

## **Egyéb virtualizációs megoldások**
**Hyper-V**
- A Microsoft által kifejlesztett Hyper-V közvetlenül a hardveren fut, host operációs rendszer réteg nélkül.
- Szorosan integrálódik a Windows Server környezetekbe, ideális a vállalati szintű Windows-munkaterhelésekhez.
- A funkciók közé tartozik a dinamikus memóriaelosztás és az élő migráció a fokozott skálázhatóság és rugalmasság érdekében.

**Xen**
- A Xen egy nyílt forráskódú hipervizor, amelyet általában a vállalati felhőkörnyezetekben, például az AWS-ben használnak.
- Paravirtualizálást biztosít, lehetővé téve a vendég operációs rendszer módosítását a nagyobb teljesítmény érdekében.
- Támogatja a teljes hardveres virtualizációt is a HVM (Hardware Virtual Machine) segítségével, lehetővé téve a kompatibilitást a nem módosított vendég operációs rendszerekkel.
- A Xen az izolációs képességeiről (domU a felhasználói tartományokhoz, dom0 a menedzsmenthez) és a robusztus biztonságáról ismert.

**VMware Workstation**
- A VMware Workstation egy Windows és Linux rendszereken történő asztali virtualizációra tervezett hosztolt hipervizor.
- Ismert a gazda- és a vendég operációs rendszer közötti zökkenőmentes integrációról, beleértve a megosztott mappákat és a drag-and-drop funkciót.

**VirtualBox**
- Az Oracle által karbantartott VirtualBox egy hosztolt hipervizor, amely egy hagyományos operációs rendszeren fut.
- Platform független, támogatja a Linuxot, a Windows-t és a macOS-t gazda- és vendégrendszerként egyaránt.

**Parallels Desktop**
- Ismert a teljesítményoptimalizálásáról és a Mac rendszerekkel való szoros hardverintegrációjáról, például a Retina kijelzők támogatásáról.

## **Egy VM anatómiája**
**Hypervisor: a VM-ek létrehozását és kezelését végzi**
- absztrahálja a hardveres erőforrásokat, és kiosztja azokat a virtuális környezethez.
- futhat egy operációs rendszeren (2. típus) vagy közvetlenül a hardveren (1. típus).

**Virtuális CPU (vCPU): A VM-hez rendelt virtuális processzor.**
- Szimulálja a fizikai CPU-erőforrásokat, és feldolgozási feladatokat végez a VM számára.
- a vCPU-k száma a teljesítményigénynek megfelelően állítható be.
- a vCPU-k túlellátása akkor következik be, amikor több virtuális CPU-t rendelnek a virtuális gépekhez (VM), mint amennyi fizikai processzormag rendelkezésre áll az állomáson.

**Virtuális memória: A VM számára rendelkezésre álló RAM mennyiségét jelenti.**
- Ez a memória el van szigetelve a többi VM-től, és a hypervisor kezeli.
- a hipervizor figyeli a memóriahasználatot a túlzott rendelkezésre bocsátás elkerülése érdekében.

**Virtuális tárolás: Egy virtuális merevlemez, amely a VM lemezes tárolóját képviseli.**
- létezhet fizikai lemezen vagy hálózati tárolón lévő fájlokként.
- a virtuális tároló lehet dinamikusan kiosztott (thin/sparse) vagy fix méretű (előre kiosztott).

**Virtuális hálózati interfészkártyák (vNIC): A VM-hez rendelt hálózati adapterek.**
- VM-eket a fizikai hálózathoz csatlakoztathatja, vagy virtuális hálózatban elszigetelheti őket.
- a VM a vNIC-et használja a hálózati kapcsolaton keresztül történő adattovábbításra.

**Vendég operációs rendszer: A VM-környezetbe telepített operációs rendszer.**
- vezérli a VM erőforrásait, valamint hosztolja az alkalmazásokat és szolgáltatásokat.
- kölcsönhatásba lép a hypervisorral az erőforrás-kezelés érdekében (speciális illesztőprogramokra lehet szükség).

## **VM tárolási koncepciók**
**Klónozás: a VM tárolóhelyének pontos másolatának létrehozása.**
- A *teljes klónozás* mind a VM-et, mind annak teljes tárolóját lemásolja,
- a *kapcsolt klón* bizonyos adatok esetében az eredeti VM tárolójára támaszkodik.

**Pillanatképek készítése: a tároló aktuális állapotának rögzítése egy adott időpontban.**
- nem teljes biztonsági mentések - az állapotot úgy mentik, mint egy azonnali kikapcsolás esetén

**Dinamikus kiosztás (Thin Provisioning): olyan tárolóoptimalizálási módszer, ahol a tárhelyet csak igény szerint osztják ki, amikor a VM adatokat ír.**
- minimalizálja a pazarolt tárhelyet azáltal, hogy nem osztja ki előre a fel nem használt helyet
- teljesítménycsökkenést és tárhely-túllépést eredményezhet

**Statikus kiosztás (Thick Provisioning): A teljes tárolókapacitás előre kiosztásra kerül egy VM számára, így a hely akkor is fenntartásra kerül, ha az kihasználatlanul marad.**
- kiszámítható teljesítményt biztosít
- a tárolási erőforrások kihasználatlanságát okozhatja

**Átméretezés: A VM virtuális lemezének méretének beállítása, növelve vagy csökkentve a rendelkezésre álló tárhelyet.**
- VM kikapcsolt állapotában is elvégezhető (offline méretezés).
- bizonyos esetekben dinamikusan a VM futása közben (online méretezés), elkerülve az üzemzavarokat.

**Trimmelés: Olyan folyamat, amely tájékoztatja a mögöttes tárolót, hogy mely adatblokkokat nem használja már a VM.**
- Segít a hosztnak tárhely visszanyerésében és a teljesítmény optimalizálásában.
- különösen hasznos a vékony rendelkezésre bocsátású (*thin provisioned*) környezetekben

**Verziókezelés: A tároló által támogatott VM különböző verzióinak fenntartása különböző időpontokban.**
- Lehetővé teszi a korábbi tárolási állapotok helyreállítását,
- a biztonsági mentési és katasztrófa utáni helyreállítási stratégiák támogatása

**Copy on Write (COW): Olyan tároláskezelési technika, amelynél a lemezblokkok módosításai csak akkor íródnak ki, amikor a módosítások megtörténtek.**
- elkerülve a változatlan adatok duplikálásának szükségességét
- megőrzi a hatékonyságot a klónozás és a pillanatfelvételek készítése során az írási műveletek jelentős csökkentésével

## **Gyakori VM műveletek**
**Indítás/Boot**
- A virtuális gép bekapcsolása az operációs rendszer és az alkalmazások elindításához.
- Ez a folyamat aktiválja a VM erőforrásait, lehetővé téve a feladatok elvégzését és a szolgáltatások elérését.

**Leállítás**
- A VM kíméletes kikapcsolása, az adatok integritásának biztosítása.
- A vendég operációs rendszer leáll, és a kiosztott erőforrások visszaadódnak a hypervisornak.
- Szükség lehet *támogató ügynökre* (support agent) a vendég operációs rendszerben.

**Suspend/Resume**
- A VM műveleteinek szüneteltetése és állapotának mentése a memóriába/lemezre.
- Folytatáskor a VM pontosan a felfüggesztett ponttól folytatódik.
- Váratlan eseményeket eredményezhet

**Pillanatkép**
- A VM állapotának rögzítése egy adott időpontban.
- A pillanatfelvételek lehetővé teszik a rendszergazdák számára a visszaállítást, ha a jövőbeli változások problémákat vagy hibákat okoznak.
- Ide tartozhat a RAM (memória) pillanatkép

**Klónozás**
- Egy VM konfigurációjának és állapotának azonos másolatának létrehozása.
- Ezt a műveletet gyakran használják tesztelési vagy staging környezetekben.

**Migráció**
- Egy futó VM áthelyezése egyik állomásról egy másikra.
- Az élő migráció ezt leállási idő nélkül teszi lehetővé, biztosítva az üzletmenet folytonosságát.

**Átméretezés**
- A virtuális erőforrások (pl. vCPU-k, memória) beállítása, miközben a VM offline állapotban van.
- Egyes hypervisorok korlátozottan támogathatják a működés közbeni dinamikus méretváltoztatást.

## **VM *gazda-vendég* (host-guest) interakció és adatátvitel**
**OS illesztőprogramok**
- Standard illesztőprogramok
    - Fizikai hardver emulálása
    - Nagyobb overhead, kevésbé hatékony
    - Univerzális kompatibilitás a vendég operációs rendszerrel
- Paravirtualizált illesztőprogramok
    - Közvetlenül együttműködnek a hoszt interfészekkel
    - Alacsonyabb késleltetés, jobb teljesítmény
    - OS-specifikus; vendégtámogatást igényel
    - Virtualizációs környezetekhez tervezték
    - Proxmox példa: A qm set 100 lemezekhez virtio használata - scsi0 virtio0

**Hálózati csatolások**
- Megosztott könyvtárak virtuális hálózati kapcsolatokon keresztül
- Fájlrendszer-hozzáférés az állomás és a vendég között
- Közös protokollok: NFS, SMB/CIFS a csatoláshoz
- Proxmox példa: A pvesm használata az NFS-hez a `pvesm add nfs <id> <kiszolgáló> -export <elérési útvonal>` segítségével.

**Guest agents**
- A host-guest közti kommunikációra szolgál
- Kibővített funkciók (pl. biztonsági mentések, kíméletes leállítás, automatikus mountok) lehetővé tétele
- A vendég operációs rendszer teljesítményének és kulcsfontosságú attribútumainak (például IP-címek) felügyelete és jelentése.
- Lehetővé teheti a fejlett vendégvezérlést, például a parancsok végrehajtását.
- Proxmox példa: A QEMU vendégügynök telepítése `apt install qemu-guest-agent` segítségével a vendég operációs rendszerben.

**Vágólap-megosztás**
- Adatok másolása-beillesztése a hoszt és a vendég között
- Szöveg, grafika és fájlmegosztási lehetőségek
- Alapvető fontosságú a zökkenőmentes asztali munkafolyamathoz
- Proxmox példa: Vágólap-szinkronizálás SPICE-on keresztül asztali VM-ek számára

**Zökkenőmentes mód**
- Vendégalkalmazások integrálása a gazdaterületen
- Dinamikus ablakbeállítások
- Fokozott felhasználói élmény és termelékenység
- Proxmox példa: `qm start 100 --spice` a SPICE-kompatibilis zökkenőmentes alkalmazási módhoz

---

# 5.	Konténerizációs megoldások és lehetőségek modern szerverkörnyezetekben (MST 02 - Virtualization and Containerization diasor 16-26 dia)
## **Konténerizáció**

- A konténerizáció egy alkalmazást a függőségekkel együtt egy szabványosított egységbe csomagol.

**Könnyű virtualizáció:**
    - A konténerek az operációs rendszer szintjén virtualizálnak, és kevesebb erőforrást használnak, mint a teljes virtuális gépek.
    - Ez gyorsabb telepítési időt és jobb teljesítményt eredményez.
    - A konténerek könnyűek és hordozhatók különböző rendszereken és környezetekben.

- A konténerek leegyszerűsítik a szoftverek szállítását és csökkentik a telepítési költségeket.

**Főbb jellemzők:**
- **Könnyűsúly:** A konténerek kevésbé erőforrás-igényesek, mint a virtuális gépek, mivel megosztják a host OS kernelét, és csak a felhasználói területet igénylik.
- **Hordozhatóak:** Konzisztensen futtathatók különböző környezetekben, a helyi fejlesztőgépektől a termelési szerverekig.
- **Elszigetelt:** Különálló környezetet biztosít az alkalmazások és függőségeik számára, a rendszerben lévő más alkalmazások zavarása nélkül.

**Előnyök:**
- **Konzisztencia a különböző környezetekben:** Biztosítja, hogy az alkalmazás ugyanúgy fusson, függetlenül attól, hogy hol telepítik - fejlesztési, tesztelési vagy termelési környezetben.
- **Egyszerűsített telepítés:** Lehetővé teszi az egy kattintással történő telepítést és visszaállítást, megkönnyítve a gyors frissítéseket és a verzióvezérlést.
- **Hatékony erőforrás-kihasználás:** A host kernel megosztásával minimalizálja az overhead-et, így több alkalmazás futtatható ugyanazon a hardveren.
- **Gyors skálázhatóság:** Az alkalmazások igény szerint gyorsan fel- vagy leskálázhatók konténerpéldányok hozzáadásával vagy eltávolításával.

## **Főbb konténerizációs technikák**

**Image-ek létrehozása és kezelése**
- **Alapképek:** A konténerkép létrehozásának első lépése egy optimalizált alapképre való építés. Ez csökkenti a kép méretét, valamint javítja a konténer teljesítményét.
- **Rétegezés:** A konténerképek rétegezése lehetővé teszi a gyakran használt rétegek újrafelhasználását. Ez hatékonyabb tárhely- és erőforrás-kezelést tesz lehetővé több konténer esetén is.
- **Verziókezelés:** A képek verziószámokkal való ellátása (taggelése) segíti a különböző verziók nyomon követését, és megkönnyíti a frissítések, valamint a telepítések pontos kezelését.

**Erőforrás-kezelés és korlátozás *(Resource allocation and limitation)***
- **Névtér (Namespace)**: Elkülöníti az alkalmazásokat és azok erőforrásait, így megakadályozza a konténerek közötti kölcsönös zavaró hatásokat.  
- **Csoportok (Cgroups)**: Korlátozza és nyomon követi a konténerizált alkalmazások erőforrás-felhasználását (pl. CPU, memória), ezáltal biztosítva a kiegyensúlyozott erőforráselosztást.

**Hálózatkezelés és biztonság *(Networking and Security)***
- **Hálózati elkülönítés (Network Isolation)**: Virtuális hálózatok alkalmazásával elválasztható a konténerek közötti kommunikáció, ami növeli a biztonságot és lehetővé teszi a forgalom szabályozását.  
- **Titkos adatok kezelése (Secrets Management)**: Biztonságos módszerek használatával tárolhatóak és kezelhetőek az érzékeny adatok, például jelszavak és titkos kulcsok a konténereken belül.

**Adatállandóság *(Data Persistence)***
- **Kötetek (Volumes)**: Külső kötetek használatával biztosítható, hogy az adatok a konténer életciklusán túl is megmaradjanak, ezáltal növelve az adatok tartósságát és megbízhatóságát.  
- **Bind Mounts**: A hosztrendszer fájlrendszerének közvetlen összekapcsolása a konténerrel lehetővé teszi a zökkenőmentes adatelérést és a közös konfigurációk használatát.

## **Docker és alternatívái *(Docker and Alternatives)***

- **Docker konténerek**:  
  - Az alkalmazásokat és azok függőségeit kapszulázzák be, így biztosítva a hordozhatóságot és a konzisztens futtatási környezetet.

- **Docker képek (Docker Images)**:  
  - **Megváltoztathatatlan sablonok**: A konténerek ezekre az írásvédett sablonokra épülnek.  
  - **Réteges felépítés**: A képek több rétegből állnak, így lehetővé válik a meglévő rétegek újrafelhasználása, ami hatékonyabb frissítést és tárhelykezelést eredményez.

- **Docker Hub**:  
  - **Központosított tároló**: Előre elkészített képek könyvtárát kínálja, amelyek könnyen kereshetők és megoszthatók.  
  - **Képverzió-kezelés**: Támogatja a verziókövetést, amely lehetővé teszi a változások nyomon követését és a korábbi verziókra való visszatérést.

**Alternatív konténertechnológiák *(Alternative Container Technologies)***

- **LXC (Linux Containers)**  
  - Rendszerkonténerek: Operációs rendszer szintű virtualizációt kínál, amely hasonló a könnyűsúlyú virtuális gépekhez. Több izolált Linux rendszer futtatását teszi lehetővé egy hoszton.

- **OpenVZ / Virtuozzo**  
  - Kernel megosztás: Közös kernel környezetet igényel, ezért csak Linux alapú hosztokon futtatható, ami bizonyos alkalmazások esetén korlátozó lehet.

- **Podman**  
  - Daemon nélküli működés: Központi daemon nélkül működik, ami növeli a biztonságot azáltal, hogy a konténereket felhasználói jogosultságokkal futtatja.  
  - Docker kompatibilitás: Docker-kompatibilis parancssori felületet (CLI) kínál, így megkönnyíti a Docker felhasználók számára az átállást.

- **CRI-O**  
  - Kubernetes kompatibilitás: Kifejezetten könnyűsúlyú és Kubernetes-hez optimalizált konténerfuttató, amely szorosan integrálódik a Kubernetes Container Runtime Interface-ével (CRI).

## **Gyakori konténer műveletek**

- **Konténerek létrehozása**  
  - **Képekből**: A konténerek előre elkészített képekből jönnek létre, biztosítva az egységes futtatási környezetet.  
  - **Testreszabás**: A létrehozás során környezeti változók és fájlok konfigurálhatók az adott igényeknek megfelelően.

- **Konténerek indítása és leállítása**  
  - **Futtatás / Indítás**: A konténer elindítására használt parancs, amely inicializálja a folyamatokat a konténeren belül.  
  - **Leállítás / Kikapcsolás**: A konténer biztonságos leállítása, amely megőrzi az állapotot és megakadályozza az adatvesztést.

- **Konténerek eltávolítása**  
  - **Konténerek törlése**: Nem használt vagy elavult konténerek törlése a források felszabadítása érdekében, rendszeres takarítással.  
  - **Prune műveletek**: Prune parancsokkal hatékonyan lehet eltávolítani a nem használt képeket, konténereket és hálózatokat.

- **Parancsok futtatása konténerekben**  
  - Futtassunk további folyamatokat vagy parancsokat egy már futó konténeren belül.  
  - **Interaktív végrehajtás**: Shell hozzáféréssel interaktívan léphetünk be a konténerbe hibakeresés vagy menedzsment céljából.

- **Hálózatkezelés**  
  - **Hálózati konfiguráció**: A konténerek hálózatokhoz való csatlakoztatása a konténerek közötti és külső kommunikáció megkönnyítése érdekében.  
  - **Porttérképezés (Port Mapping)**: A konténerportok hozzárendelése a hoszt gép portjaihoz, ezáltal biztonságosan kezelve a hozzáférést és a kapcsolódást.

- **Kötetkezelés**  
  - **Állandó tárolás**: Kötetek használata az adatok megőrzésére a konténer életciklusán túl, ezzel biztosítva az adatok megbízhatóságát.  
  - **Megosztott kötetek**: Közös kötetek csatolásával lehetőség nyílik az adatok megosztására konténerek között, támogatva az együttműködő műveleteket.

- **Képkezelés**  
  - **Képek építése**: Új képek létrehozása a konténerekből a változtatások rögzítésével, ami következetes telepítéseket tesz lehetővé.  
  - **Kép letöltése és feltöltése**: Képek letöltése tárolókból vagy helyi képek feltöltése a szélesebb körű használathoz és terjesztéshez.

## **Dockerfile**

**Konténer-tervrajz *(Blueprint for Containers)***
- A Dockerfile-ok olyan szkriptek, amelyek meghatározzák a konténer felépítésének lépéseit és folyamatokat, ezáltal automatizálva a konténerkép elkészítését.

**Reprodukálhatóság *(Reproducibility)***
- Biztosítja az egységes beállítást és konfigurációt különböző környezetek között, ezáltal csökkentve a „nálam működik” típusú problémákat.

## **Alternatív nyilvános konténerkép-tárolók *(Alternate Public Container Image Repositories)***

**Azure Container Registry (ACR)**
- Áttekintés: A Microsoft által kezelt, skálázható képtárolást biztosít, amely integrált az Azure szolgáltatásokkal.  
- Jellemzők: Támogatja a földrajzi replikációt, átfogó kép sebezhetőség-ellenőrzést és build funkciókat.

**Google Container Registry (GCR)**
- Áttekintés: A Google biztonságos, nagy teljesítményű képtárolója, amely integrált a Google Cloud Platformmal.  
- Jellemzők: Finomhangolt hozzáférés-szabályozást, sebezhetőség-ellenőrzést és regionális tárolási lehetőségeket kínál.

**Amazon Elastic Container Registry (ECR)**
- Áttekintés: Az Amazon által teljesen menedzselt Docker konténerregiszter, amely mélyen integrált az AWS szolgáltatásokkal.  
- Jellemzők: Élettartam-kezelési szabályokat, automatikus képellenőrzést és zökkenőmentes használatot támogat az Amazon ECS és EKS szolgáltatásokkal.

**Quay.io**
- Áttekintés: A Red Hat tulajdonában lévő konténerregiszter, amely erős funkciókat kínál a képek kezelésére.  
- Jellemzők: Növeli a biztonságot képellenőrzéssel, és lehetővé teszi nyilvános és privát tárolók használatát.

**GitHub Container Registry (gchr.io)**
- Áttekintés: A GitHub csomagtárolója, amely natív tárolást biztosít a GitHub repozitóriumok mellett.  
- Jellemzők: Finomhangolt jogosultságokat és integrációt kínál a GitHub Actions-szal CI/CD folyamatokhoz.

**JFrog Artifactory**
- Áttekintés: Univerzális artefakt-tárkezelő, amely más formátumok mellett Docker-képeket is támogat.
- Jellemzők: Erőteljes metaadat-kezelés, széleskörű integrációs lehetőségek és erős biztonsági szabályozás.

**Harbor**
- Áttekintés: Egy nyílt forráskódú, cloud-native regiszter, amely szabályokkal és szerepkör-alapú hozzáférésvezérléssel biztosítja az artefaktumokat.  
- Jellemzők: Képességei közé tartozik a sebezhetőség elemzés, tartalom aláírás, audit naplók, és támogatja a Docker képeket és OCI artefaktumokat is.

---

# 6. Klaszterezés céljai és lehetőségei modern szerverkörnyezetekben (MST 03 - Clusterization, Configuration Management, and Orchestration diasor 3-12 dia)
## **Klaszterezés *(Clusterization)***

### **A klaszterezés definíciója és kulcsfogalmai *(Definition and Key Concepts of Clusterization)***

- **Klaszterezés definíciója**: Erőforrások csoportosítása úgy, hogy egyetlen egységként működjenek.  
- **Terheléselosztás (Load Balancing)**: A munkaterhelések elosztása a klaszter csomópontjai között.  
- **Hibatűrés (Fault Tolerance)**: A folyamatos működés biztosítása csomópont kiesése esetén is.  
- **Magas rendelkezésre állás (High Availability, HA)**: Minimalizált leállási idő biztosítása.  
- **Skálázhatóság (Scalability)**: Egyszerű csomópont hozzáadás vagy eltávolítás igény szerint.  
- **Erőforrás megosztás (Resource Pooling)**: Közös CPU, memória és tárhely használata a klaszterben.  
- **Redundancia (Redundancy)**: Adatok és fájlok replikálása több csomóponton.  
- **Vezetőválasztás (Leader Election)**: A vezérlés koordinálása a csomópontok között.  
- **Konzisztencia és partícionálás (Consistency & Partitioning)**: Az adatok következetességének kezelése elosztott erőforrások között.


### **Klaszterezés példái *(Examples of Clusterization)***

- **Számítási klaszterek (Compute Clusters)**: Elosztott CPU erőforrások (pl. HPC, AWS EC2 Auto Scaling)  
- **Tárolási klaszterek (Storage Clusters)**: Közös adattárolás több csomóponton (pl. Ceph, GlusterFS)  
- **Adatbázis klaszterek (Database Clusters)**: Elosztott adatbázisok a skálázhatóságért (pl. Cassandra, MySQL Cluster)  
- **Terheléselosztó klaszterek (Load Balancer Clusters)**: Forgalomelosztás webszolgáltatásokhoz (pl. HAProxy, NGINX)  
- **Kubernetes klaszterek**: Konténerizált munkaterhelés-kezelés  
- **Hálózati klaszterek (Network Clusters)**: Hibatűrő hálózati szolgáltatások (pl. Cisco IOS routerekhez)  
- **Nagyteljesítményű számítási klaszterek (HPC Clusters)**: Összetett számítások megoldása (pl. MPI-alapú klaszterek)  
- **Gyorsítótár klaszterek (Cache Clusters)**: Gyors adatlekérés (pl. Redis, Memcached klaszter módban)

## **A klaszterezés fő kihívásai és kezelési stratégiái *(Main Challenges & Management Strategies of Clusterization)***

- **Csomópont kiesések (Node Failures):**  
  - Stratégia: Replikáció, automatikus átállás (failover) és redundancia alkalmazása.

- **Terheléselosztás bonyolultsága (Load Balancing Complexity):**  
  - Stratégia: Dinamikus terheléselosztók használata állapotellenőrzéssel (health checks).

- **Hálózati késleltetés (Network Latency):**  
  - Stratégia: Hálózati topológia optimalizálása, élcsomópontok (edge nodes) telepítése.

- **Adatkonzisztencia (Data Consistency):**  
  - Stratégia: Konszenzus protokollok alkalmazása (pl. Paxos, Raft).

- **Skálázhatósági szűk keresztmetszetek (Scalability Bottlenecks):**  
  - Stratégia: Vertikális skálázás, sharding, horizontális skálázás.

- **Klaszterkezelési többletterhelés (Cluster Management Overhead):**  
  - Stratégia: Automatizálás orkestrációs eszközökkel (pl. Kubernetes).

- **Erőforrás-konfliktus (Resource Contention / Starving):**  
  - Stratégia: Erőforrás-kvóták és korlátok (limit ranges) bevezetése.

- **Biztonsági aggályok (Security Concerns):**  
  - Stratégia: Adatok titkosítása átvitel közben, szigorú IAM (Identitás- és Hozzáférés-kezelés) szabályok érvényesítése.

- **Monitorozás és naplózás (Monitoring & Logging):**  
  - Stratégia: Központosított naplózás és valós idejű monitorozás beállítása (pl. Prometheus, ELK stack).

## **Elosztott döntéshozatal egy klaszterben *(Distributed Decisions in a Cluster)***

- **Vezetőválasztás (Leader Election):**  
  - Egyetlen csomópontot választ koordinátornak (pl. Raft, Paxos algoritmusok).

- **Split-Brain helyzet:**  
  - Probléma:  
    - Hálózati partíció miatt az állapot eltérő lehet a partíciók között.  
    - Több vezető is megválasztható egyszerre.  
  - Megoldás:  
    - Kvórum alapú döntéshozatal alkalmazása (pl. többségi szavazás).

- **Kvórum konszenzus (Quorum Consensus):**  
  - Biztosítja, hogy a változtatások csak akkor kerüljenek elfogadásra, ha a többség egyetért.

- **CAP tétel:**  
  - Nem lehet egyszerre garantálni a következőket: konzisztencia (Consistency), rendelkezésre állás (Availability) és partíciótűrés (Partition tolerance) – ez egy inherent kompromisszum.

## **Klaszter konszenzus *(Cluster Consensus)***

- **Kétfázisú commit (Two-Phase Commit, 2PC):**  
  - Biztosítja, hogy vagy az összes csomópont elkötelezi a tranzakciót, vagy egyik sem; lassabb a koordináció miatt.  
  - Hibák esetén a koordinátor kiesése végtelen blokkolást eredményezhet.

- **Konszenzus algoritmusok (Consensus Algorithms):**  
  - **Paxos:** Hibakezelés a többségi egyetértés érdekében, de bonyolult megvalósítani.  
  - **Raft:** Egyszerűsített konszenzus, gyakran használják vezetőválasztásra (pl. Kubernetes, etcd).

- **Nézetváltó protokoll (View Change Protocol):**  
  - Stratégia a vezető cseréjére hibák esetén.

## **A Raft konszenzus protokoll *(The Raft Consensus Protocol)***

- **Fő komponensek (Core Components):**  
  - **Vezető (Leader):** Koordinálja a replikációt és vezérli a napló konzisztenciáját.  
  - **Követők (Followers):** Passzív állapotban vannak, a vezetőtől fogadják a parancsokat.  
  - **Jelöltek (Candidate):** Ideiglenesen átveszik a vezetői szerepet a választások alatt.

- **Vezetőválasztás (Leader Election):**  
  - A követő jelöltté válik, ha egy választási időkorláton belül nem hall vezetőről.  
  - A vezetővé váláshoz többségi szavazat szükséges.

- **Napló replikáció (Log Replication):**  
  - A vezető elküldi a naplóbejegyzéseket a követőknek.  
  - A bejegyzések akkor kerülnek elkötelezésre, ha a csomópontok többségén replikálódtak.

- **Heartbeat mechanizmus:**  
  - A vezető rendszeresen küld üres "AppendEntries" üzeneteket, hogy megőrizze hatalmát.

| **Szempont**         | **Raft konszenzus protokoll**                                                                 | **Kétfázisú commit (2PC)**                                                                                   |
|----------------------|-----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **Cél**              | Konszenzus elérése elosztott rendszerekben, fókuszálva a vezető alapú replikációra és állapot-egyeztetésre | Több rendszer közötti tranzakciók atomi elkötelezésének koordinálása                                        |
| **Vezető szerepe**   | Egy kiválasztott vezető szükséges a naplóbejegyzések javaslatára és replikációjára             | Nincs vezető; a koordinátor felügyeli a tranzakció elkötelezését                                            |
| **Hibatűrés**        | Bár a vezető kieshet, gyorsan választanak új vezetőt                                          | A koordinátor egyetlen hibapont; kiesése végtelen blokkolást okozhat                                        |
| **Algoritmus típusa**| Konszenzus algoritmus, többségi kvórummal működik (elosztott állapot-egyeztetés)               | Atomi commit protokoll, minden résztvevőnek egyet kell értenie a commit/abort döntésen                       |
| **Kommunikáció fázisai**     | Folyamatos kommunikáció vezető és követők között heartbeat mechanizmusokkal; vezetőválasztás, napló replikáció, heartbeat fenntartás            | Két fő fázis: előkészítés (Prepare) és commit/abort; atomi commit protokoll, amely megköveteli az összes résztvevő egyetértését          |
| **Hiba kezelése**    | Vezető kiesése új választást vált ki, a követők folytatják a napló fogadását                   | Koordinátor kiesése végtelen blokkolást okozhat, résztvevők várnak                                          |
| **Elkötelezés modellje** | Folyamatos; a naplóbejegyzések replikálódnak, és a commit-hoz többségi megerősítés szükséges                      | Bináris döntés, amely az összes résztvevő egyhangú "commit" vagy "abort" döntésén alapul                                         |
| **Skálázhatóság**    | Jobban skálázható, mivel több csomóponton tud naplókat replikálni nagy elosztott klaszterekben| Kevésbé skálázható, hálózati terhelés nő a résztvevők számával                                             |
| **Kvórum**           | Többségi kvórumon alapul (többségi szavazás)                                                | Egyhangú egyetértést igényel az összes résztvevőtől                                                        |
| **Használati területek** | Elosztott állapotgépek, vezető alapú replikáció, pl. Kubernetes (etcd), konszenzus elérés   | Elosztott adatbázis tranzakciók, atomi tranzakciók biztosítása                                            |
| **Teljesítmény**     | Hatékony normál körülmények között, de lehet késés a vezetőválasztáskor                      | Lassabb a több fázis és a nagyobb hálózati terhelés miatt                                                  |


## **Klaszterezés bemutatása: etcd**

- **Áttekintés:**
  – Elosztott, megbízható kulcs-érték tároló, amely erős konzisztenciát és magas rendelkezésre állást biztosít  
  – Gyakran használják elosztott rendszerek koordinálására  

- **Fő jellemzők:**
  – Konzisztens: Lineárizálható olvasásokat/írásokat garantál a klaszteren belül  
  – Magas rendelkezésre állás: Több csomóponton replikálja az adatokat, biztosítva a hibatűrést  
  – Skálázható: Több ezer csomóponton képes futni  
  – Raft konszenzus algoritmus: Biztosítja a hibatűrő vezetőválasztást és adat-egyezséget  

- **Fő alkalmazási területek:**
  – Szolgáltatás-felfedezés: Alkalmazások önregisztrációjára és más szolgáltatások felderítésére használják  
  – Konfiguráció menedzsment: Alkalmazáskonfiguráció tárolása klasztereken keresztül (pl. Kubernetes a klaszter állapotát tárolja az etcd-ben)  

- **Kulcsfogalmak:**
  – Kulcs-érték párok: Adatok tárolása hierarchikus névterű kulcs-érték párok formájában  
  – Watches (megfigyelők): A kliensek figyelhetik a kulcsokat, és értesítést kapnak az adatok változásáról  
  – Leases (bérletek): Az adatok automatikusan lejárnak egy meghatározott idő után  

---

# 7.	Infrastruktúra mint kód fő jellemzői, kihívásai, stratégiái (MST 03 - Clusterization, Configuration Management, and Orchestration diasor 14-16 dia)
## **Infrastructure as Code (IaC)**

- **Definíció:** Az IT-infrastruktúra kezelése és kiépítése gép által olvasható konfigurációs fájlok segítségével, nem pedig hagyományos, fizikai hardveres beállításokon keresztül.  
- **Automatizálás és Orkesztráció:**
  – Lehetővé teszi az ismételhető, automatizált kiépítést szkriptek vagy deklaratív konfigurációk segítségével (pl. Terraform, Ansible).  

- **Verziókövetett infrastruktúra:**
  – Az infrastruktúra konfigurációk verziókezelő rendszerben (pl. Git) vannak tárolva, így nyomon követhetőek a változások és visszaállítás is lehetséges.  

- **Idempotencia:**
  – Ugyanazon kód többszöri alkalmazása ugyanazt az állapotot eredményezi negatív mellékhatások (pl. duplikált erőforrások) nélkül.  

- **Deklaratív vagy Imperatív megközelítés:**
  – Deklaratív: A kívánt állapot megadása (pl. Terraform)  
  – Imperatív: A kívánt állapot eléréséhez szükséges lépések részletes meghatározása (pl. Ansible szkriptek)  

- **Skálázhatóság:**
  – A szkriptek könnyen alkalmazkodnak az infrastruktúra dinamikus felskálázásához vagy leépítéséhez felhőalapú környezetekben (AWS, GCP, Azure).  

- **Konzisztencia és szabványosítás:**
  – Elősegíti a következetes infrastruktúra-telepítéseket, csökkenti az emberi hibákat a konfigurációk szabványosításával.  

- **Infrastruktúra absztrakció:**
  – Magasabb szintű fogalmakon keresztül absztrahálja az infrastruktúra-összetevőket (szerverek, hálózat, adatbázisok), így platformfüggetlenné téve a kezelést.  

- **Újrafelhasználhatóság és modularitás:**
  – Lehetővé teszi a kód újrahasználatát modulokon vagy sablonokon keresztül különböző rendszerek vagy szolgáltatások között, növelve a hatékonyságot és karbantarthatóságot.  

- **Tesztelés és validálás:**
  – Lehetővé teszi az infrastruktúrakód előzetes tesztelését eszközökkel, mint például a `terraform plan`, biztonságosabb élesítés érdekében.  

- **Környezeti egységesség:**
  – Biztosítja a konzisztenciát a fejlesztői, tesztelői és éles környezetek között az azonos konfigurációs kód használatával.  

### **IaC – Kihívások és Kezelési Stratégiák**

- **Konfigurációs drift:** Manuális változtatások az infrastruktúrán (IaC-en kívül) inkonzisztenciát okoznak a futó állapot és a kód között.  
  – **Stratégia:** Használj folyamatos monitorozó eszközöket (pl. Driftctl), és vezess be szigorú protokollokat (pl. csak IaC pipeline-on keresztüli változtatás engedélyezése).

- **Állapotkezelés:** Az erőforrások állapotának kezelése (pl. Terraform state file-ok) bonyolult lehet nagy, elosztott környezetekben.  
  – **Stratégia:** Tárold az állapotfájlokat távoli, megosztott helyeken (pl. AWS S3, Terraform Cloud), és alkalmazz backend lockolást az egyidejű módosítások elkerülésére.

- **Biztonsági kockázatok:** Érzékeny adatok (API kulcsok, jelszavak) véletlenül bekerülhetnek a konfigurációs fájlokba.  
  – **Stratégia:** Használj titkos adatkezelő eszközöket (pl. HashiCorp Vault, AWS Secrets Manager) az érzékeny információk biztonságos kezelésére és injektálására.

- **Hozzáférés és szerepkörök kezelése:** Az IaC kódhoz való kontrollálatlan hozzáférés jogosulatlan módosításokhoz vagy hibás konfigurációkhoz vezethet.  
  – **Stratégia:** Vezess be RBAC (Role-Based Access Control) rendszert és részletes IAM (Identity and Access Management) szabályokat az infrastruktúra kezeléséhez és a telepítési jogosultságokhoz.

- **Függőségkezelés:** Komplex függőségek az egyes komponensek között (pl. adatbázisnak előbb kell indulnia, mint az alkalmazáskiszolgáló) sikertelen telepítésekhez vezethetnek.  
  – **Stratégia:** Használj deklaratív függőségkezelést támogató eszközöket (pl. Terraform `depends_on`), és építs lépésenkénti pipeline-t a helyes sorrend biztosításához.

- **Tesztelés és validálás:** Biztosítani kell, hogy az IaC módosítások ne okozzanak problémát az éles környezetben.  
  – **Stratégia:** Használj előzetes tesztelő keretrendszereket (pl. `terraform validate`), állíts be staging környezetet és automatizált tesztpipeline-t a változások validálására.

- **Változáskövetés és auditálás:** Az infrastruktúra változások és azok szerzőinek nyomon követése elengedhetetlen.  
  – **Stratégia:** Alkalmazz verziókezelő rendszert (pl. Git), kötelező pull request jóváhagyással, és integráld CI/CD rendszerrel. Vezess be naplózást és monitorozást a telepítésekre.

- **Tooling széttagoltság:** Több IaC eszköz együttes használata (pl. Terraform az infrastruktúrához, Ansible a konfigurációhoz) kezelhetetlenné válhat.  
  – **Stratégia:** Konszolidáld az eszközöket, ahol lehetséges, vagy integráld őket egy közös orchestrációs platformmal (pl. Terraform + Ansible). Építs egységes CI/CD pipeline-t, amely lefedi az összes eszközt.

---

# 8.	Terraform fő jellemzői, workflow, ökoszisztéma, fő nyelvi elemek (MST 03 - Clusterization, Configuration Management, and Orchestration diasor 17-23 dia)
## **Terraform**

- **Egy nyílt forráskódú* Infrastructure as Code (IaC) eszköz**, amelyet a **HashiCorp** fejlesztett ki  

- Lehetővé teszi az infrastruktúra **definiálását, provisionálását és kezelését** egy magas szintű konfigurációs nyelv, a **HashiCorp Configuration Language (HCL)** segítségével.

### **Terraform – Fő Jellemzők**

- **Infrastructure as Code (IaC):**  
  – Infrastruktúra-erőforrások, mint például virtuális gépek, adatbázisok, hálózati elemek stb., kóddal kezelhetők, ami megkönnyíti a verziókezelést, együttműködést és automatizálást.

- **Deklaratív konfiguráció:**  
  – A felhasználók megadják az infrastruktúra kívánt végállapotát.  
  – A Terraform kiszámítja, hogyan érje el ezt az állapotot, így átlátható folyamatot biztosít a környezetek kiépítéséhez.

- **Multi-Cloud és szolgáltatófüggetlen működés:**  
  – Támogatja a legtöbb felhőszolgáltatót, pl. AWS, Azure, Google Cloud, valamint helyszíni megoldásokat (VMware, OpenStack).  
  – Lehetővé teszi az infrastruktúra egyszerre több felhőplatformon és környezetben történő kezelését egyetlen konfigurációs fájl használatával.

- **Állapotkezelés (State Management):**  
  – A Terraform egy állományban tárolja az infrastruktúra aktuális állapotát.  
  – Ez segít nyomon követni a változásokat és felismerni, mi létezik már és mi nem a későbbi futások során.

- **Provisionálás és Orkesztráció:**  
  – A Terraform nemcsak erőforrásokat hoz létre, hanem képes a köztük lévő függőségek orkesztrálására is (pl. adatbázis létrehozása az alkalmazás előtt, amely azt használja).

### Terraform – Alapvető Működési Lépések

- **Konfiguráció írása:**  
  – Az infrastruktúrát `.tf` fájlokban kell definiálni HCL vagy JSON formátumban.

- **Provider pluginek inicializálása:**  
  – A `terraform init` paranccsal inicializálható a munkakönyvtár, és letölthetők a szükséges szolgáltatói pluginek.

- **Végrehajtási terv generálása:**  
  – A `terraform plan` paranccsal előnézet kérhető arról, hogy a Terraform milyen változtatásokat fog végrehajtani az infrastruktúrán.  
  – Megjeleníti, hogy mi fog történni (pl. létrehozás, módosítás, törlés), anélkül hogy ténylegesen alkalmazná a változásokat.

- **Konfiguráció alkalmazása:**  
  – A `terraform apply` futtatásával a rendszer létrehozza, módosítja vagy törli az erőforrásokat a konfiguráció alapján.

- **Állapotkezelés:**  
  – A Terraform az infrastruktúra állapotát `.tfstate` állományokban tárolja, ezzel követi nyomon a meglévő erőforrásokat.

- **Infrastruktúra eltávolítása (teardown):**  
  – A `terraform destroy` parancs segítségével az összes létrehozott erőforrás tisztán eltávolítható, ha már nincs rájuk szükség.

### **Terraform ökoszisztéma**

- **Szolgáltatók (Providers):**  
  – A Terraform a különféle felhőszolgáltatók API-jával a szolgáltatói pluginjein keresztül kommunikál (pl. AWS, Azure, GCP, Kubernetes stb.).  
  – *Példa:* Az AWS provider segítségével létrehozhatók és kezelhetők AWS erőforrások, mint például EC2 példányok, S3 tárolók, vagy VPC-k.

- **Erőforrások (Resources):**  
  – Az infrastruktúra építőelemei, melyek fizikai vagy logikai objektumokat reprezentálnak, például virtuális gépeket, tárolókat, vagy hálózatokat.

- **Modulok (Modules):**  
  – Újrafelhasználható konfigurációs egységek, amelyeket egy egységként lehet kezelni. Segítik a konzisztenciát és a hatékony kódhasználatot.  
  – *Példa:* Egy modul, amely egy teljes VPC-t hoz létre, benne publikus/privát alhálózatokkal, útválasztó táblákkal és internetkapukkal.

- **Terraform State:**  
  – A Terraform a telepített infrastruktúra állapotát egy állapotfájlban követi nyomon. Ez az állapot biztosítja, hogy a Terraform tudja, milyen erőforrások léteznek, így pontosan tudja alkalmazni a változtatásokat.  
  – Az állapot tárolható távolról is (például egy S3 bucketben), hogy csapatok között együttműködést biztosítson.  
  – Az állapot tárolható helyileg is.

- **Backend:**  
  – A backend határozza meg, hogy hol tárolja a Terraform az állapotát (például S3, Consul).  
  – A távoli back-endek állapotzárolást is biztosítanak, hogy elkerüljék a párhuzamos változtatásokat.


### **A Terraform HCL kulcsfontosságú nyelvi elemei**

**Szolgáltatók (Providers)**
- Felelősek az infrastruktúra erőforrásainak életciklus-kezeléséért.
- A szolgáltatók az infrastruktúra platformok API-jaival kommunikálnak, mint például AWS, Azure, GCP vagy Docker.

```json
provider "aws" {
  region = "us-west-2"
}
```

**Erőforrások (Resources)**
- Az infrastruktúra komponenseit képviselik (például virtuális gépek, tárolók, adatbázisok).

```json
resource "docker_container" "nginx" {
  image = "nginx:latest"
  name  = "my_nginx_container"
  ports {
    internal = 80
    external = 8080
  }
}
```

**Adatforrások (Data Sources)**
- Lehetővé teszik a már meglévő infrastruktúra lekérdezését, amelyet nem a Terraform kezel.
  
```json
data "aws_ami" "latest_ami" {
  most_recent = true
  owners      = ["amazon"]
  filter {
    name   = "name"
    values = ["amzn2-ami-hvm-*"]
  }
}
```

**Változók (Variables)**
- Értékek megadására szolgálnak, melyek testreszabhatók.
- Támogatják a kód újrafelhasználhatóságát és rugalmasságot biztosítanak.

```json
variable "instance_type" {
  description = "Indítandó példány típusa"
  type        = string
  default     = "t2.micro"
}

resource "aws_instance" "example" {
  ami           = "ami-123456"
  instance_type = var.instance_type
}
```

**Outputs (Kimenetek)**
- Értékek kinyerése a Terraform futásából, amelyek megjeleníthetők vagy továbbadhatók más folyamatoknak.

```json
output "instance_ip" {
  description = "Publikus IP cím"
  value       = aws_instance.i.public_ip
}
```

**Locals (Lokális változók)**
- Lokális változók, amelyek köztes értékeket tárolnak.
- A definíció sorrendjében értékelődnek ki.

```json
locals {
  instance_count = 3
  instance_name  = "my-server"
}
```

**Functions (Függvények)**
- Beépített függvények adatmanipulációhoz.  
- Szövegátalakítások, matematikai műveletek, kollekciók kezelése és egyebek.

```json
locals {
  my_list    = ["apple", "banana"]
  first_item = element(local.my_list, 0) # Visszaadja az "apple" értéket
}
```

**Conditionals (Feltételek)**
- Dinamikus érték-meghatározás feltételek alapján.

```json
resource "aws_instance" "example" {
  ami           = "ami-123456"
  instance_type = var.is_production ? "t3.large" : "t2.micro" # A környezet alapján választ instance típust
}
```

**Count**
- Több erőforrás példány létrehozása egyetlen blokk alapján.

```json
resource "aws_instance" "servers" {
  count         = 3   # 3 példány létrehozása
  ami           = "ami-123456"
  instance_type = "t2.micro"
  tags = {
    Name = "server-${count.index + 1}"
  }
}
```

**For Loops (Ciklusok)**
- Adatszerkezetek átalakítása és végigiterálása.

```json
variable "zones" {
  default = ["us-west-1a", "us-west-1b"]
}

output "availability_zones_map" {
  value = {
    for zone in var.zones : zone => length(zone)
  }
}
```

**Modul**
- Újrahasználható, önálló Terraform konfigurációs egységek.

```json
module "module_name" {
  source    = "./path/to/module"  # A forrás lehet helyi útvonal vagy külső regisztráció
  variable1 = var.value1
  variable2 = var.value2
}
```

**Depends On**
- Biztosítja, hogy egy erőforrás csak egy másik létrehozása után jöjjön létre.

```json
resource "type" "name" {
  depends_on = [resource.type.other_resource]  # Függőség deklarálása
}
```

---

# 9.	Ansible fő jellemzői, workflow, ökoszisztéma, parancsok (MST 03 - Clusterization, Configuration Management, and Orchestration diasor 24-29 dia)
## Ansible

**Nyílt forráskódú automatizációs eszköz**

– Elsősorban a következőkre használják:  
  - konfigurációkezelés,  
  - alkalmazástelepítés,  
  - orkesztráció,  
  - infrastruktúra provisioning (erőforrások biztosítása).

- **Agent nélküli:**
  – Nem igényel szoftver telepítését a kezelt node-okon (ügynököket).  
  – Távoli node-okkal SSH (Linux/BSD esetén) vagy WinRM (Windows esetén) protokollon keresztül kommunikál.  

- **Deklaratív és idempotens:**
  – Deklaratív nyelvet használ a rendszer kívánt állapotának meghatározására.  
  – Automatikusan biztosítja, hogy az állapot alkalmazva legyen anélkül, hogy ismételné a műveleteket, hacsak nem szükséges.

### **Ansible fogalmak**

**Playbook**
- A konfigurációk YAML fájlokban íródnak, melyeket Playbooknak nevezünk.  
- A Playbook több playből áll, amelyek meghatározzák a végrehajtandó feladatokat távoli gépeken.

**Példa Playbook részlet:**

```yaml
- name: Web szerver telepítése
  hosts: webservers
  tasks:
    - name: NGINX telepítése
      apt:
        name: nginx
        state: present

    - name: NGINX indítása
      service:
        name: nginx
        state: started
```

**Task (Feladat)**
– Egy adott műveletet ír le (pl. csomag telepítése, szolgáltatás indítása)
– A feladatok egymás után hajtódnak végre

**Inventory**
– Az inventory fájl határozza meg, mely hosztokat kell kezelni
– A hosztok logikai egységekbe csoportosíthatók (pl. web szerverek, adatbázisok)

```csharp
[webservers]
web1.example.com
web2.example.com

[databases]
db1.example.com
db2.example.com
```

**Modules (Modulok)**
– Konfigurációs képességeket biztosítanak (feladatok)  
– Példák:  
  - apt/yum: Csomagkezeléshez  
  - copy: Fájlok másolásához  
  - user: Felhasználók létrehozásához/kezeléséhez  
  - service: Szolgáltatások vezérléséhez (indítás, leállítás, újraindítás)  
  - ec2, azure_rm, gcloud: Felhőszolgáltatások kezeléséhez  
– Egyedi modulok is írhatók Python, Bash vagy más nyelveken  

**Roles (Szerepek)**  
– A playbookokat újrahasznosítható komponensekre szervezik  
– Letölthetők az Ansible Galaxy tárolóból  

**Variables (Változók)**  
– Lehetővé teszik a konfigurációk vagy feladatok dinamikus testreszabását  
– Meghatározhatók playbookban, inventoryban, vagy dinamikusan átadhatók  
– Használhatók sablonozással, például:  

```yaml
- name: Open port 80
  ufw:
    port: "{{ http_port }}"
    rule: allow
    state: enabled
```

## **Alapvető Ansible munkafolyamatok *(Core Ansible Workflow)***

**Control Node:**  
– Ez az a gép, amelyre az Ansible telepítve van, és ahonnan az Ansible playbookokat írod és futtatod (innen küldi a parancsokat a hosztoknak).

**Managed Hosts/Nodes:**  
– Ezek a célszámítógépek (pl. webszerverek, adatbázisok), amelyeket az Ansible konfigurál. Az Ansible SSH-n keresztül kommunikál a Linuxos hosztokkal, WinRM-en keresztül pedig a Windowsos gépekkel.

**Execution Model:**  
– Push-alapú modell: Az Ansible push-modellt használ, vagyis az utasításokat a vezérlő gépről (control node) tolják (küldik) a kezelt hosztokra.

**Idempotence:**  
– Az Ansible biztosítja, hogy ugyanaz a playbook többször is biztonságosan lefuttatható legyen. Ha a rendszer már a kívánt állapotban van, nem történik további változtatás, így idempotens.

## **Ansible parancsok *(Ansible Commands)***

**Ad-hoc Parancsok:**  
– Egyetlen feladat végrehajtása egy vagy több kezelt hoszton anélkül, hogy playbookot írnánk:  
```bash
# Pingeld meg az összes webszervert a kapcsolat ellenőrzéséhez  
ansible webservers -m ping  

# Telepítsd az NGINX csomagot az összes hosztra az inventory-ban  
ansible all -m apt -a "name=nginx state=present"
```

**Playbook futtatása:**
```bash
ansible-playbook my-playbook.yml
```

**Ansible Galaxy:**  
– Közösségi központ előre megírt Ansible szerepkörök (roles) megosztására és újrafelhasználására.  
– Szerepkör letöltése:  
```bash
ansible-galaxy install gguy.apache
```
- Szerepkör használata playbookban:
```bash
- hosts: webservers
  roles:
    - gguy.apache
```

---

# 10.	Kubernetes fő jellemzői, koncepciók, architektúra, erőforrás típusok (MST 03 - Clusterization, Configuration Management, and Orchestration diasor 30-40 dia)

## **Miért Kubernetes?**

- **Kihívások orchestration nélkül:**  
  – Olyan problémák, mint a kézi skálázás, a konfigurációkezelés nehézségei és az alkalmazás kiesései.

- **A Kubernetes előnyei:**  
  – Hatékonyan kezeli a bonyolult alkalmazásokat.  
  – Javítja a skálázhatóságot és az alkalmazás ellenálló képességét.  
  – Egyszerűbbé teszi a telepítést több környezetben.

## **Kubernetes architektúra**

- **Master node:**  
  – **API szerver:** A Kubernetes vezérlő síkjának front-endje.  
  – **Scheduler:** A Pod-ok erőforrásait a meghatározott szabályok alapján osztja ki.  
  – **Controller Manager:** Felügyeli a működést, és biztosítja, hogy a rendszer a kívánt állapotban legyen.  
  – **etcd:** Elosztott kulcs-érték adatbázis az összes klaszteradat tárolására.

- **Worker node-ok:**  
  – **Kubelet:** Biztosítja, hogy a konténerek futnak a Pod-ban.  
  – **Kube-proxy:** Kezeli a klaszter hálózatát és a terheléselosztást.

## **Kulcsfogalmak**

**Podok:**  
– A legkisebb telepíthető egység a Kubernetes-ben. Egy Pod általában egyetlen alkalmazáskonténert vagy szorosan összekapcsolt konténercsoportot foglal magába.  
– Célja: Olyan konténerek számára biztosítja ugyanazt a hálózati névteret, mintha ugyanazon a gazdagépen futnának.  

**Szolgáltatások**

- **Cél:** Egy Pod-csoportot hálózati szolgáltatásként tesz elérhetővé.  
- **Szolgáltatás típusai:**  
  – **ClusterIP:** Belső szolgáltatás a klaszteren belül.  
  – **NodePort:** Megnyit egy adott portot az összes Node-on külső hozzáféréshez.  
  – **LoadBalancer:** Felhőszolgáltató terheléselosztóját használja külső szolgáltatáshoz.  
- **Előnyök:** Terheléselosztást és szolgáltatás-felfedezést biztosít.

**Deploymentek**

- **Cél:** Kezeli a Pod-ok replikációját, lehetővé teszi az egyszerű frissítéseket, valamint a szolgáltatások leállás nélküli skálázását.  
- **Jellemzők:**  
  – **Rolloutok:** Verziók fokozatos frissítése.  
  – **Rollbackek:** Hibás frissítés esetén visszatérés az előző verzióhoz.  
- **Parancs példa:** `kubectl apply -f deployment.yaml`

**ConfigMapek**

- Nem bizalmas konfigurációs adatokat tárol kulcs-érték párokban.  
- Példa: Alkalmazás konfigurációs fájlok.

**Secret-ek**

- Érzékeny információk biztonságos tárolása és kezelése.  
- Példa: Adatbázis jelszavak, API kulcsok.

## **Skálázás és Önjavítás**

- **Automatikus skálázás:**  
  - Horizontal Pod Autoscaler: A Pod-ok számát igazítja a deployment-ben CPU vagy egyéb egyedi metrikák alapján.

- **Önjavítás:**  
  - Automatikusan helyettesíti a meghibásodott Pod-okat.  
  - Betartja és fenntartja a kívánt állapotú konfigurációkat.

## **Tartós tárolás**

- **Volumes:**  
  - Átmeneti tároló, amely a Pod életciklusához kötött.

- **Persistent Volumes (PVs) és Persistent Volume Claims (PVCs):**  
  - PV-k: Az aktuális tárolóhely absztrakciója.  
  - PVC-k: Felhasználók által kezdeményezett tárolóigény.  
  - Az elkülönítés rugalmasságot biztosít a tárolás kezelésében.

## **Hálózatkezelés Kubernetes-ben**

- **Podok közötti kommunikáció:**  
  - Minden Pod egyedi IP-címet kap a Kubernetes klaszterben.

- **Pod és szolgáltatás közötti kommunikáció:**  
  - A szolgáltatások hidat képeznek az külső kliensek és a Pod hálózat között.

- **Hálózati szabályok (Network Policies):**  
  - Az IP-cím szintjén szabályozzák a forgalom áramlását.

## **Kubectl Parancssori Felület**

**Célja:**  
- A Kubernetes klaszterekkel való interakció fő parancssori eszköze.

**Gyakori parancs példák:**  
  - `kubectl get pods` – Listázza az összes Podot.  
  - `kubectl describe svc <szolgáltatás_neve>` – Leírja a megadott Kubernetes szolgáltatást.  
  - `kubectl logs <pod_neve>` – Lekéri egy Pod naplóit.

---