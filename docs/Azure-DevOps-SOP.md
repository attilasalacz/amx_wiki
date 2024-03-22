# 1. Általános információk
Az Azure DevOps egy adott szolgáltatás - jelen esetben a CargoWise - és a hozzá kapcsolódó szolgáltatások tervezését, fejlesztését, ezek kivitelezését és üzemeltetését segítő eszköz.

## 1.1 Tartalom
[[_TOC_]]

## 1.2 A szolgáltatás főbb elemei
- MS Azure DevOps teljes dokumentáció [itt](https://learn.microsoft.com/hu-hu/azure/devops/?view=azure-devops).

|Funkció|Leírás|Státusz|Bővebben|
|-|-|-|-|
|Dashboard|A folyamat és a funkciók egészére betekintést nyújtó, igény szerint testreszabható felület|Használjuk|https://learn.microsoft.com/hu-hu/azure/devops/report/dashboards/quick-ref?view=azure-devops
|Boards|Csapatok bevonásával történő tervezés, nyomon követés és |Használjuk (igény szerint)|https://learn.microsoft.com/hu-hu/azure/devops/boards/get-started/what-is-azure-boards?view=azure-devops|
|Repos|A CargoWise, vagy a hozzá kapcsolódó szolgáltatások fejlesztése során keletkezett akár egyszer használatos kódok gyűjteménye; későbbi, automatizált rendszerek kódjait tartalmazó kódbázis|Használjuk|https://learn.microsoft.com/hu-hu/azure/devops/repos/git/gitworkflow?view=azure-devops|
|Pipelines|Folyamatos integráció és terjesztés (CI/CD) kivitelezése bármilyen platformban és felhőben való folyamatos fejlesztéshez, teszteléshez és üzembe helyezéshez.|Jelenleg nem használjuk|https://learn.microsoft.com/hu-hu/azure/devops/pipelines/get-started/what-is-azure-pipelines?view=azure-devops|
|Test Plans|Böngészőalapú tesztkezelési megoldás a tervezett manuális teszteléshez, a felhasználói elfogadás teszteléséhez, a feltáró teszteléshez és az érdekelt felek visszajelzéseinek gyűjtéséhez szükséges összes képességet biztosítja.|Jelenleg nem használjuk|https://learn.microsoft.com/hu-hu/azure/devops/test/overview?view=azure-devops|
|Artifacts|A fejlesztés során használt függőségek (dependencies) egységes kezelésére szolgáló funkció|Jelenleg nem használjuk|https://learn.microsoft.com/hu-hu/azure/devops/artifacts/start-using-azure-artifacts?view=azure-devops&tabs=nuget%2Cnugetserver%2Cnugettfs|

## 1.3 Főbb fogalmak
|Fogalom|Magyarázat|
|-|-|
|CW|CargoWise|
|felhasználó|CW felhasználó|
|dev user|CW Key USer, a DevOps rendszer felhasználója|

# 2. Dashboard

## 2.1 Team-Dashboard
- Amennyiben az Azure DevOps szolgáltatás használata során bármelyik dev userben felmerül az igény egy-egy folyamat, állapot, stb. a csapat dashboardján történő elhelyezésére, azt a kivitelezés után itt fogjuk rögzíteni.

## 2.2 Egyéni Dashboard
- Bármely dev user tud készíteni, [itt](https://learn.microsoft.com/hu-hu/azure/devops/report/dashboards/quick-ref?view=azure-devops) találtok bővebb információt.

# 3. Boards
- A megoldandó feladatok, problémák, új szolgáltatások, funkciók kezelésére az Azure DevOps ún. *Work-Item*-eket használ.

- Mindig egy *Development*-el, *Issue*-val, vagy *Role Request*-el kezdődik, melyhez a dev user elvégezendő *Task*-okat kapcsol.

## 3.1 Work-Itemek

|Work-Item|Use-Case|
|-|-|
|Bug|Szigorúan csak a kódbázisban található *Bug*ok jelölése|
|Issue|Már használatban lévő CW szolgáltatással, jobbal felmerülő probléma|
|Role Request|Jogosultság kérés adott CW funkcióhoz, vagy modulhoz|
|Training|CW funkciók, modulok, (a funkció, modul, vagy folyamat hiányosságából adódó) nem megfelelő kezelése és *Issue*-t eredményez |
|Task|Dev user feladat|
|Development Story|Bármely felhasználótól érkezett, fejlesztést igénylendő, komplex feladat|

### 3.1.1 Development
- A felhasználó jelzi az igényét egy adott funkció létrehozásával, vagy módosításával kapcsolatban.

|Mezőnév|Magyarázat|Kötelező|
|-|-|-|
|Description|Felhasználó kérésének rövid leírása|Igen|
|Acceptance Criteria|Specifikus követelmények a megoldásra vonatkozóan|Nem|
|Requested On|Felhasználó kérésének időpontja|Igen|
|Requested CW User|Felhasználó neve|Igen|
|Due Date|Határidő|Nem|
|Priority|Prioritás 1-5-ig terjedő skálán|Igen|
|Users Priority|Prioritás a felhasználó szerint 1-5-ig terjedő skálán (1 a legmagasabb)|Igen|
|Risk|Rizikó, esetleges interferencia más CW szolgáltatással, funkcióval|Nem|
|Development|Amenniyben tartozik a *Development*-hez kód, hozzá lehet rendelni|Nem|
|Related Work|Kapcsolódó *Task* |Nem|
|Original Estimate|A *Development* elvégzéséhez szükséges idő (óra)|Nem|
|Completed|A *Development* tényleges időtartama (óra)|Nem|

### 3.1.2 Issue
- A felhasználó jelez egy, már létező CW funkcióval, job-al, szolgáltatással kapcsolatos problémát, hibát.

|Mezőnév|Magyarázat|Kötelező|
|-|-|-|
|Description|Felhasználó hibabejelentésének, észrevételének rövid leírása|Igen|
|Requested On|Felhasználó kérésének időpontja|Igen|
|Requested CW User|Felhasználó neve|Igen|
|Due Date|Határidő|Nem|
|Priority|Prioritás 1-5-ig terjedő skálán (1 a legmagasabb)|Igen|
|Users Priority|Prioritás a felhasználó szerint 1-5-ig terjedő skálán (1 a legmagasabb)|Igen|
|Development|Amenniyben tartozik az *Issue*-hoz kód, hozzá lehet rendelni|Nem|
|Related Work|Kapcsolódó *Task* |Nem|
|Original Estimate|Az *Issue* elvégzéséhez szükséges idő (óra)|Nem|
|Completed|Az *Issue* tényleges időtartama (óra)|Nem|

### 3.1.3 Role Request

- A felhasználó jelzi az igényét egy CW jogosultságra.

|Mezőnév|Magyarázat|Kötelező|
|-|-|-|
|Description|Role request ismertetése, indoklása|Igen|
|Requested On|Felhasználó kérésének időpontja|Igen|
|Requested CW User|Felhasználó neve|Igen|
|System|CW rendszer (PROD vagy TEST)|Igen|
|Original Estimate|A *Role Request* elvégzéséhez szükséges idő (óra)|Nem|
|Completed|A *Role Request* tényleges időtartama (óra)|Nem|

### 3.1.4 Task

- Bármiylen olyan dev user feladat, *Development*-hez tartozik, illetve egyéb, olyan feladatok amelyek nem érik el egy *Development* work-item komplexitását.

|Mezőnév|Magyarázat|Kötelező|
|-|-|-|
|Description|Feladat tetszőleges terjedelmű (akár specifikus, részletes) ismertetése|Igen|
|Priority|A *Task* prioritása 1-5-ig terjedő skálán (1 a legmagasabb) ahhoz képest, hogy a felette álló *User Story*, *Issue* vagy *Development* elvégzéséhez miylen sorrendben helyezkedik el.|Igen|
|Original Estimate|A *Task* elvégzéséhez szükséges idő (óra)|Nem|
|Completed|A *Task* tényleges időtartama (óra)|Nem|
|Due Date|Határidő|Nem|
|Requested On|Felhasználó kérésének időpontja|Igen|
|Requested CW User|Felhasználó neve|Igen

### 3.1.5 Training

- Amennyiben a dev user úgy ítéli meg, hogy a felhasználó által jelzett *Issue* létrejöttének oka a felhasználó a CW nem megfelelő használatának eredménye, úgy az *Issue* megoldásával párhuzamosan a felhasználó *Issue*-ját *Training*-gé minősítheti.

- Adott esetben a flhasználótól is érkezhet ilyen kérés.

### 3.1.6 Bug

## 3.2 Work-Item's Állapotok

- A *Work Item*-ek állapotát a work-item *Sate*-je jelzi. Attól függően változik, hogy az adott boardon a *Work-Item* hol helyezkedik el.

### 3.2.1 Work-Item állapottípusok

Állapot|Magyarázat|
|-|-|
New| Új *Work-Item*, az rendszerbe bekerülő work itemeket tartalmazza.
Active| A *Work-Item*-en már aktívan dolgoznak, felelőse van.
Closed| A *Work-Item*-et lezárták.
Removed| A *Work-Item*-et valamiylen ok miatt, (indokolni lehet) eltávolították.

## 3.5 Boardok

- A *Work Item*-eket megadott Boardokon használjuk, melyek a *Work-Item* típusától függően egy megadott folyamaton mennek végig.


## 3.4 Nem kódfájlok hozzáadása work-itemhez, ezek kezelése a MS SharePoint felületén
- nem kódfájlokat a dev user csoportnak létrehozott `Airmax Key Users DevOps` [SharePoint felületen](https://airmaxcargo.sharepoint.com/sites/AirmaxKeyUsersDevOps) kezelünk.

- a dokumentumok verziózását a SharePoint automatikusan végzi

- a szerkesztéshez a dokumentumot muszáj "kivenni" a dokumentumtárból, majd a szerkesztés befejezését követően be kell adni. Ezáltal elkerülhető, hogy több, egy adott dokumentumon dolgozó devuser munkája konfliktust okozzon.
 
# 4. Repos
- Ahhoz, hogy a CW-hez kapcsolódó (pl. automatiázciós) mikroszolgáltatásokat folyamatosan fejleszteni, implementálni és karbantartani tudjuk, elengedhetetlen egy olyan verziókövetett (git - oktatóanyag [itt](https://learn.microsoft.com/hu-hu/azure/devops/repos/git/?view=azure-devops), YT videó [itt](https://www.youtube.com/watch?v=PWqS4NBhEY8)) rendszer, mellyel a szolgáltatás zavartalan működése mellett, a kódbázison egyszerre többen, hatékonyan tudnak dolgozni.

- A kódbázis rendszerezéséhez és átláthatóságához a könyvtárstruktúrát, az adott programnyelvre vonatkozó stílust, kódolási gyakorlatokat elengedhetetlen meghatározni.

## 4.1 Könyvtárstruktúra a repositoryban
- A könyvtárstruktúrát a dev user a **saját neve alatt létrehozott repositoryban** teljesen szabadon határozhatja meg, illetve menedzselheti.

- Az automatizált működéshez készített `CargoWise` repository könyvtárstruktúrája a jövőben lesz definiálva.

## 4.1.1 Adatfájlok kezelése
- Adatfájlokat git-el kezelni tilos. Amennyiben több felhasználó dolgozik egy kódon az adatfájlok elérési útvonalát és egyéb beállításokat a felhasználónak a saját repojában létrehozandó konfigurációs fájlban (.json, .yml) kell rögzíteni.

- Ha felhasználó szeretné az adatok a saját munkaeszközén, a repository könyvtárában tárolni, ezt természetesen megteheti, de a fájlt, magát a köynvtárat, vagy a kiterjesztést a `.gitignore` fájlban rögzíteni kell, ezáltal a git figyelmen kívül hagyja szinkronizálás esetén.

- Sample és template fájlok tárolhatóak, ezt vagy egy megfelelő köynvtárba (pl.: `data/sample`, illetve `data/template`) kell rakni, vagy `sample`, illetve `template` prefixxel ellátni.

### 4.1.2 Speciális fájlok és mappák a repo-ban

#### 4.1.2.1 `.gitignore` fájl
- A `.gitignore` fájl funkciója, hogy a felhasználó beállításai szerint definiált mappákat, fájlokat, vagy bizonyos fájlkiterjesztéseket szinkronizáláskor figyelmen kívül

- Példa:

```
# USER FOLDERS
salacz.attila/data
salacz.attila/config
salacz.attila/playground
salacz.attila/test

# EXTENSIONS
*.so

# OTHER FOLDERS
.vscode
```
#### 4.1.2.2 Konfigurációs fájlok
- A konfigurációs fájlban adatok elérési útvonalát, a kód esetleges beállításait kell rögzíteni, így amennyiben több felhasználó dolgozik egy kódon, azonos beállítások mellett tudják azt fejleszteni, vagy futtatni.

- Példa `config.json` - syntax guide [itt](https://www.w3schools.com/whatis/whatis_json.asp).

```
{
    "version": 1.02,
    "countryList": ["HU", "DE", "GB"],
    "setup": {
        "map": true,
        "label": false
    }
}
```

- Példa `config.yml` - syntax guide [itt](https://www.tutorialspoint.com/yaml/yaml_basics.htm)

```
version: 1.02
countryList:
 - HU
 - DE
 - GB
setup:
 - map: true
 - label: false
```

#### 4.1.2.3 Átmenetileg szükséges fájlok tárolása, kezelése
- Minden oylan fájlt (köztük adatot is) amelyet csak átmenetileg szükséges tárolni a `tmp` mappába kell irányítani, majd a kód futásának befejezésével ennek a mappának a tartalmát törölni kell.

## 4.2 A kódbázis verziókövetett munkafolyamatának rövid leírása

### 4.2.1 Új branch létrehozása
- Új *Development Story* esetén a dev usernek a *Development Story* ID-val, illetve rövid elnevezésével egy új branchet kell létrehoznia. A branchet hozzá kell linkelni az adott *Development Story*-hoz.

### 4.2.2 Commit
- Amikor a *Development*-hez kapcoslódó *Task* kódját a dev user befejezte, a változást commitolni kell a bracnhben, a kapcsolódó *Task*-ot megjelölve, kommentelve.

### 4.2.3 Pull request
- Amennyiben a dev user elvégezettnek tekinti a *Development Story*-hez kapcsolódó *Task*-ok kódját, pull requestet (továbbiakban PR) kér.

- A PR során az esetleges conflictokat felül kell vizsgálni, a PR-t csak ezután lehet jóváhagyni. Minden felhasználó a saját repojának PR-eit bírálja el.

### 4.2.4 Delete branch
- Amennyiben a PR-t jóváhagyták, a kódbázist mergelték, a branch törölhető.

## 4.3 Alapvető kódolási elvek
- Do Not Repeat Yourself (DRY) - bővebb információ [itt](https://www.youtube.com/watch?v=rWpJt5CRDek)

### 4.3.1 Python

- [PEP-8 Style Guide](https://peps.python.org/pep-0008/) használata kötelező. Bármely EDI-ban elérhető automatikus formázás, ez nagyban tudja segíteni az összes felhasználó munkáját.

### 4.3.2 SQL

### 4.3.3 JSON

### 4.3.4 YAML

# 5. Ticket rendszer