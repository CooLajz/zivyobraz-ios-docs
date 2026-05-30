# Živý Obraz pro iOS

Jednoduchá iOS aplikace pro rychlý přehled zařízení ze služby [**Živý Obraz**](https://zivyobraz.eu/?page=o-sluzbe). Na iPhonu nebo iPadu uvidíš stav svých e-paperů, naměřené hodnoty, baterii, historii i widgety přímo na ploše.

## Veřejné testování přes TestFlight

Aplikace je dostupná k veřejnému testování přes Apple TestFlight: [připojit se k testování](https://testflight.apple.com/join/D6CzKtCZ).

TestFlight je oficiální aplikace od Applu pro instalaci testovacích verzí aplikací před vydáním v App Storu. Po otevření odkazu si nainstaluješ TestFlight, přijmeš pozvánku a potom můžeš nainstalovat testovací verzi Živého Obrazu.

Testovací verze může obsahovat nové funkce dřív než běžná verze, ale občas se v ní může objevit chyba nebo nedodělané chování. Když vyjde nová testovací verze, TestFlight tě na ni upozorní a nabídne aktualizaci.

## Hlavní funkce

- **Přehled všech zařízení** - teplota, vlhkost, baterie, online stav a rychlé filtrování problémů.
- **Widgety na plochu iPhonu i iPadu** - vyber konkrétní e-paper a sleduj jeho hodnoty bez otevírání aplikace.
- **Vlastní widgety pro libovolné hodnoty** - poskládej si vlastní kartu z jakékoli hodnoty dostupné v exportu služby Živý Obraz.
- **Automatická aktualizace dat** - aplikace ukládá data pro widgety a obnovuje je na pozadí podle možností iOS.
- **Detail zařízení** - informace o signálu, baterii, firmwaru, posledním kontaktu a historii měření.
- **Více účtů a skupin** - můžeš přidat více exportních klíčů a volitelně filtrovat zařízení podle Group ID.
- **Úprava dashboardu** - vlastní aliasy, řazení zařízení a skrytí nepoužívaných e-paperů.
- **Volitelné odesílání baterie zařízení** - baterii iOS zařízení lze posílat zpět do Živého Obrazu přes importní API.

## Ukázky aplikace

### Přehled zařízení

Dashboard ukazuje e-papery v přehledných kartách. Rychle vidíš, která zařízení jsou online, jakou mají baterii a jaké hodnoty právě měří.

<p>
  <img src="pics/hlavni_obrazovka_zarizeni.png" alt="Hlavní obrazovka se seznamem zařízení" width="280">
  <img src="pics/detail_zarizeni_1.png" alt="Detail zařízení s historií a diagnostikou" width="280">
  <img src="pics/detail_zarizeni_2.png" alt="Detail zařízení s dalšími informacemi" width="280">
</p>

### Widgety na ploše

Klasické widgety zobrazují konkrétní e-paper přímo na ploše iPhonu nebo iPadu. Po prvním načtení dat v aplikaci stačí widget přidat na plochu a vybrat zařízení.

<p>
  <img src="pics/widgety_na_plose.png" alt="Widgety Živý Obraz na ploše" width="560">
</p>

### Vlastní widgety

Vlastní widgety jsou určené pro hodnoty z exportu služby Živý Obraz. Můžeš si vytvořit kartu pro jednu dominantní hodnotu, dvě nebo tři hodnoty, případně seznam více hodnot.

<p>
  <img src="pics/hlavni_obrazovka_custom_widgety.png" alt="Přehled vlastních widgetů v aplikaci" width="280">
  <img src="pics/custom_widgety_nastaveni.png" alt="Nastavení vlastní karty" width="280">
</p>

<p>
  <img src="pics/custom_widgety_na_plose.png" alt="Vlastní widgety na ploše iPhonu nebo iPadu" width="560">
</p>

### Nastavení aplikace

V nastavení se přidávají účty, exportní klíče, volitelné Group ID a importní API pro odesílání baterie zařízení.

<p>
  <img src="pics/nastaveni_aplikace.png" alt="Nastavení účtů v aplikaci" width="280">
</p>

## Jak aplikaci nastavit

### 1. Připrav si exportní klíč

Ve službě Živý Obraz si připrav **exportní klíč**. Aplikace ho používá pro načítání zařízení a hodnot.

Pokud chceš zobrazovat jen vybranou skupinu zařízení, připrav si také **Group ID**. Tento krok je volitelný.

### 2. Přidej účet v aplikaci

1. Otevři aplikaci Živý Obraz.
2. Klepni na ikonu nastavení.
3. Vyplň název účtu.
4. Vlož exportní klíč.
5. Volitelně vyplň Group ID.
6. Ulož nastavení tlačítkem **Hotovo**.

Po uložení aplikace načte zařízení a uloží data pro widgety.

### 3. Přidej widget na plochu

1. Na ploše iPhonu nebo iPadu podrž prst na volném místě.
2. Klepni na **Upravit**, zvol přidat widget a vyhledej **Živý Obraz**.
3. Vyber velikost widgetu.
4. Po přidání na widgetu podrž prstem a zvol **Upravit widget**.
5. Vyber konkrétní zařízení nebo ponech automatický výběr.

Widget používá poslední načtená data a průběžně se aktualizuje podle možností iOS.

### 4. Vytvoř vlastní widget

1. V aplikaci přepni na část **Vlastní**.
2. Klepni na přidání vlastní karty.
3. Vyber hodnoty z exportu služby Živý Obraz.
4. Zvol rozložení karty a vzhled.
5. Přidej na plochu widget **Živý Obraz Custom** a vyber vytvořenou kartu stejným způsobem jako pro widget zařízení v bodě 3.

Vlastní widget je vhodný například pro venkovní teplotu, vlhkost, tlak, CO2, kvalitu vzduchu, stav baterie nebo jakoukoli další hodnotu, kterou máš v exportu.

## Automatická aktualizace

Aplikace používá background refresh a sdílenou cache pro widgety. iOS vždy rozhoduje, kdy přesně může aplikace nebo widget data obnovit, ale aplikace se snaží udržovat data čerstvá a zároveň zbytečně nevolat API.

Pro nejlepší fungování nech aplikaci občas otevřít, ponech povolené aktualizace na pozadí a po změně nastavení proveď ruční refresh.

## Požadavky

- iPhone nebo iPad s iOS/iPadOS 17 nebo novějším.
- Exportní klíč ze služby Živý Obraz.
- Pro odesílání baterie zařízení importní klíč ze služby Živý Obraz.

## Soukromí a klíče

Exportní a importní klíče se ukládají bezpečně do iOS Keychainu. Aplikace si lokálně ukládá jen potřebná nastavení, cache pro widgety, aliasy zařízení, pořadí zařízení a diagnostiku aktualizací.

## Zásady ochrany soukromí

Tyto zásady ochrany soukromí se vztahují na iOS aplikaci **Živý Obraz**.

### Jaká data aplikace zpracovává

Aplikace zpracovává pouze data potřebná pro zobrazení informací ze služby Živý Obraz:

- exportní klíče a volitelné Group ID pro načítání zařízení a hodnot,
- volitelný importní klíč pro odesílání baterie iOS zařízení do služby Živý Obraz,
- názvy účtů zadané uživatelem,
- seznam zařízení, naměřené hodnoty, stav baterie, online stav a další informace vrácené exportním API,
- uživatelská nastavení aplikace, aliasy zařízení, pořadí zařízení, skryté položky, vlastní widgety a lokální cache pro widgety,
- technické informace potřebné pro diagnostiku aktualizací v aplikaci.

### Ukládání dat

Exportní a importní klíče jsou uložené v iOS Keychainu. Ostatní nastavení a cache se ukládají lokálně v zařízení a ve sdíleném úložišti aplikace a widgetů. Aplikace tato data nepředává provozovateli aplikace, neodesílá je do vlastních serverů a nepoužívá je pro reklamu ani analytiku.

### Komunikace se službou Živý Obraz

Aplikace používá zadané klíče pro komunikaci s API služby Živý Obraz. Při načítání dat odesílá exportní klíč, případně Group ID, aby mohla získat zařízení a hodnoty dostupné pro daný účet. Pokud uživatel zapne volitelné odesílání baterie zařízení, aplikace může pomocí importního klíče odesílat aktuální stav baterie iOS zařízení do služby Živý Obraz.

Zpracování dat na straně služby Živý Obraz se řídí podmínkami a zásadami této služby.

### Sdílení dat

Aplikace neprodává, nepronajímá ani nesdílí osobní data s třetími stranami. Aplikace neobsahuje reklamní SDK, sledovací SDK ani analytické nástroje třetích stran.

### Práva uživatele

Uživatel může data uložená v aplikaci odstranit odebráním účtů, smazáním uložených nastavení nebo odinstalováním aplikace. Odebráním účtu se odstraní uložené klíče a lokální data související s tímto účtem v aplikaci.

### Změny zásad

Tyto zásady mohou být aktualizovány při změně funkcí aplikace nebo způsobu zpracování dat. Aktuální znění je dostupné na této stránce.

### Kontakt

V případě dotazů k ochraně soukromí použijte kontaktní údaje uvedené u aplikace v App Storu nebo v repozitáři projektu.

## Privacy Policy

This Privacy Policy applies to the **Živý Obraz** iOS app.

### Data Processed by the App

The app processes only the data required to display information from the Živý Obraz service:

- export keys and an optional Group ID used to load devices and values,
- an optional import key used to send the iOS device battery level to the Živý Obraz service,
- account names entered by the user,
- device lists, measured values, battery status, online status, and other information returned by the export API,
- app settings, device aliases, device order, hidden items, custom widgets, and local widget cache,
- technical information needed for update diagnostics inside the app.

### Data Storage

Export and import keys are stored in the iOS Keychain. Other settings and cache data are stored locally on the device and in the shared storage used by the app and its widgets. The app does not send this data to the app developer's own servers and does not use it for advertising or analytics.

### Communication with the Živý Obraz Service

The app uses the keys entered by the user to communicate with the Živý Obraz API. When loading data, the app sends the export key and, if configured, the Group ID so it can retrieve devices and values available for the account. If the user enables optional device battery reporting, the app may use the import key to send the current iOS device battery level to the Živý Obraz service.

Data processing performed by the Živý Obraz service is governed by the terms and privacy policy of that service.

### Data Sharing

The app does not sell, rent, or share personal data with third parties. The app does not include advertising SDKs, tracking SDKs, or third-party analytics tools.

### User Rights

The user can remove data stored by the app by deleting accounts, clearing saved settings, or uninstalling the app. Removing an account deletes the stored keys and local app data related to that account.

### Changes to This Policy

This policy may be updated when the app features or data processing practices change. The latest version is available on this page.

### Contact

For privacy-related questions, please use the contact information provided for the app in the App Store or in the project repository.
