# Živý Obraz pro iOS

Jednoduchá iOS aplikace pro rychlý přehled zařízení ze služby [**Živý Obraz**](https://zivyobraz.eu/?page=o-sluzbe). Na iPhonu nebo iPadu uvidíš stav svých e-paperů, naměřené hodnoty, baterii, historii i widgety přímo na ploše.

## Veřejné testování přes TestFlight

Aplikace je dostupná k veřejnému testování přes Apple TestFlight (před kliknutím na odkaz si z App Store doinstaluj aplikaci TestFligt od Apple. Odkaz poté otevří přímo z iOS zařízení pro automatické propojení s TestFlight)

## [Připojit se k testování](https://testflight.apple.com/join/D6CzKtCZ).

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
