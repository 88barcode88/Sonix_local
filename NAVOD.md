# Local Sonix - návod k použití a nastavení

[Zpět ke stažení](README.md#čeština) | [English guide](GUIDE.md)

## První spuštění

1. Otevři **Nastavení**.
2. Vlož **Soniox** API klíč pro realtime přepis.
3. Volitelně vlož **OpenAI** nebo **Mistral** klíč pro AI úpravu textu po zastavení nahrávání.
4. Nastav klávesovou zkratku, jazyk a region.

## API klíče: co potřebuji

| Funkce | Potřebný klíč |
|--------|---------------|
| Průběžný cloudový přepis řeči | Soniox |
| AI úprava hotového textu | OpenAI **nebo** Mistral podle zvoleného poskytovatele |
| Lokální přepis přes Whisper na Windows | Žádný; nejprve stáhni runtime a model v aplikaci |

Klíče vytváříš ve vlastních účtech poskytovatelů. Jejich dostupný kredit, tarif a limity určují, kolik můžeš používat API. Případné poplatky za API platíš přímo poskytovateli. Klíče vkládej do **Nastavení → API klíče** a každý potvrď jeho tlačítkem **Uložit**. Nesdílej je v e-mailech ani screenshotech. Pro běžné používání není potřeba upravovat soubory ani proměnné prostředí.

### Soniox: získání klíče

1. Založ účet nebo se přihlas do [Soniox Console](https://console.soniox.com).
2. Pokud požaduješ EU, nejprve dokonči postup v následující sekci.
3. V konzoli vytvoř projekt a jeho API klíč. Zkontroluj také dostupný kredit a účtování ve svém účtu.
4. V aplikaci vlož klíč do pole **Soniox API klíč** a klikni na **Uložit Soniox klíč**.
5. Nastav **Soniox region** podle projektu, ze kterého klíč pochází. Pro EU projekt vyber **EU**.
6. Vyzkoušej krátký realtime přepis.

### Soniox: jak zajistit zpracování v EU

**Pouhé přepnutí aplikace na EU ani odeslání e-mailu nestačí.** Soniox musí nejprve povolit regionální projekty na tvém účtu. Potom potřebuješ projekt v EU, jeho API klíč a region EU v aplikaci.

1. Napiš na **[support@soniox.com](mailto:support@soniox.com)**. Můžeš použít tento text; doplň e-mail účtu, nikoli API klíč:

```text
Subject: Enable EU data residency for my account

Hello Soniox support,
I would like to enable EU data residency for my account: [account email].
I use Local Sonix for real-time speech transcription and need audio and
transcripts to be processed and stored in the EU.
Please enable access to EU projects and let me know when I can create
an EU project and its API key.
Thank you.
```

2. Počkej na potvrzení aktivace od podpory.
3. V Soniox Console vytvoř **nový projekt s regionem EU** a vytvoř jeho API klíč.
4. Ulož tento klíč v Local Sonix a nastav **Soniox region → EU**. Původní klíč z jiného regionu nepoužívej.
5. Ověř krátkým přepisem, že kombinace klíče a regionu funguje. Region projektu ověř v konzoli; samotný úspěšný přepis není důkazem EU nastavení.

Standardní globální Soniox endpoint zpracovává data v **USA**. EU projekt používá EU endpointy, které aplikace vybere nastavením regionu. Soniox uvádí, že audio a přepisy z regionálního projektu zůstávají v daném regionu; údaje účtu, statistiky používání a fakturace mohou být zpracovány mimo něj. [Oficiální pravidla a postup Soniox data residency](https://soniox.com/docs/data-residency).

**EU nastavení Sonioxu se nevztahuje na OpenAI ani Mistral.** V režimu AI přepisu se hotový text odešle vybranému AI poskytovateli, pokud máš uložený jeho klíč. To platí i pro text z lokálního Whisperu. Pro přepis pouze přes Soniox bez další AI služby použij realtime režim.

### OpenAI: získání klíče

1. Přihlas se do [OpenAI Platform – API keys](https://platform.openai.com/api-keys).
2. Vyber svůj projekt a vytvoř nový tajný API klíč. Zkopíruj ho při vytvoření a ulož bezpečně.
3. V nastavení účtu zkontroluj účtování, dostupný kredit a limity API.
4. V Local Sonix vlož klíč do **OpenAI API klíč** a klikni na **Uložit OpenAI klíč**.
5. Pro AI úpravu zvol poskytovatele **OpenAI**, dostupný model a režim **AI přepis**.

[Oficiální úvod k OpenAI API](https://developers.openai.com/api/docs/quickstart).

### Mistral: získání klíče

1. Přihlas se do [Mistral Studio](https://console.mistral.ai).
2. Otevři **API Keys → Create new key**, pojmenuj klíč a nastav jeho platnost.
3. Vytvořený klíč hned zkopíruj; celý se po zavření dialogu znovu nezobrazí. Zkontroluj tarif a limity účtu.
4. V Local Sonix vlož klíč do **Mistral API klíč** a klikni na **Uložit Mistral klíč**.
5. Pro AI úpravu zvol poskytovatele **Mistral**, dostupný model a režim **AI přepis**.

[Oficiální návod Mistral](https://docs.mistral.ai/getting-started/quickstarts/studio/activate-and-generate-api-key).

## Jak aplikaci používat

1. Povol aplikaci přístup k mikrofonu a zvol režim: **realtime** ukazuje text průběžně; **AI přepis** upraví výsledek až po zastavení.
2. Spusť nahrávání tlačítkem nebo nastavenou klávesovou zkratkou, nadiktuj krátký text a stejnou zkratkou nahrávání zastav.
3. Počkej na dokončení zpracování. Pokud je zapnuté kopírování, výsledek bude ve schránce.
4. Vlož text do cílové aplikace pomocí **Ctrl+V** na Windows nebo **Cmd+V** na Macu. Automatické vložení lze zapnout v Nastavení.

Pro práci v jiném programu nejprve umísti kurzor do jeho textového pole a pak použij globální zkratku. Před odesláním nebo uložením text vždy zkontroluj, zejména jména, čísla a AI úpravy.

## Přehled nastavení

Nastavení mají záložky **Základ**, **Přepis** a **Výstup**. U klíčů, zkratky, slovníku a vlastní instrukce použij příslušné tlačítko pro uložení.

| Nastavení | Co dělá |
|-----------|---------|
| Jazyk aplikace | Přepíná rozhraní mezi češtinou, angličtinou a němčinou. |
| Klávesová zkratka | Spouští a zastavuje nahrávání i mimo okno aplikace. Zvol kombinaci, kterou nepoužívá jiný program. |
| Zdroj přepisu | Soniox cloud nebo lokální Whisper. Whisper zobrazuje výsledek až po zastavení. |
| Jazyk přepisu | Zvol jazyk řeči, případně automatické rozpoznání. Je nezávislý na jazyku rozhraní. |
| Soniox region a model | Region musí odpovídat projektu a klíči. Model vybírej z nabídky; při prvním nastavení ponech výchozí. |
| Čekání po pauze v řeči | Delší čekání může omezit předčasné ukončování vět, ale zpomalí reakci. |
| Výplňová slova | Volitelně filtruje výplňová slova z přepisu. |
| AI poskytovatel a model | Vybere OpenAI nebo Mistral pro úpravu hotového textu. Potřebuje klíč vybraného poskytovatele; bez něj se použije jen místní odstranění opakování. |
| Styl AI přepisu | Jednoduchý přepis zachovává plynulý text; strukturovaný styl uspořádá témata, odstavce či seznamy. |
| Vlastní instrukce | Pro strukturovaný styl můžeš upravit prompt a kliknout na **Uložit instrukci**. **Obnovit výchozí** vrátí původní instrukci. |
| Kopírování a koncová mezera | Určuje kopírování výsledku do schránky a přidání mezery na konec. |
| Automaticky vložit po zastavení | Pokusí se vložit hotový výsledek do aktivního textového pole. Při neúspěchu použij ruční vložení. |
| Realtime psát přímo pod kurzor | V realtime režimu průběžně píše do aktivního pole. Při diktování neměň cílové okno. AI režim čeká na hotový výsledek. |
| Slovník | Přidej vlastní jména, názvy a odborné výrazy a ulož je. Soniox je dostane jako kontext pro další nahrávání. |
| Statistiky | Ukazují souhrny používání a odhady úspory času a ceny. Skutečné vyúčtování kontroluj u poskytovatele. |

### Lokální Whisper na Windows

V Nastavení vyber lokální Whisper, ručně stáhni **runtime** a **model** a počkej na stav připraveno. Stažení vyžaduje internet; samotný lokální přepis pak API klíč nepotřebuje. K dispozici jsou modely `medium-q5_0` (asi 539 MB), `large-v3-q5_0` (asi 1,08 GB) a `large-v3` (asi 3,1 GB). Větší modely potřebují více paměti a mohou být pomalejší.

Volba **Vypnout Whisper po nečinnosti** určuje, jak dlouho model zůstane v paměti mezi nahrávkami. Kratší doba uvolní paměť dříve; delší může urychlit další přepis. Model lze smazat v Nastavení.

**Současná Mac beta nemá připravený lokální Whisper runtime.** Na Macu používej Soniox. Lokální Whisper s následnou AI úpravou přes uložený OpenAI/Mistral klíč není plně offline: hotový text se odesílá tomuto poskytovateli.

## Když něco nefunguje

- **Přepis se nespustí:** zkontroluj mikrofon, internet při cloudovém přepisu, uložení klíče, jeho platnost a kredit. U Sonioxu musí souhlasit region projektu, klíče i aplikace.
- **EU klíč nefunguje:** ověř potvrzenou aktivaci od podpory a klíč z EU projektu. Pokud požaduješ EU, nepřepínej kvůli chybě na globální region.
- **AI úprava nefunguje:** zkontroluj klíč právě vybraného poskytovatele, dostupnost modelu a limity jeho API. Soniox klíč nenahrazuje OpenAI/Mistral klíč.
- **Zkratka nereaguje:** nastav jinou kombinaci, kterou nepoužívá systém nebo jiná aplikace.
- **Mac nevkládá text:** povol Local Sonix v systémovém nastavení **Soukromí a zabezpečení → Zpřístupnění**. Pro nahrávání zkontroluj také **Mikrofon**. Text můžeš vložit ručně ze schránky.
- **Whisper není připraven:** na Windows zkontroluj stažení runtime i vybraného modelu; první načtení většího modelu může trvat déle. Podrobnosti jsou v diagnostice v Nastavení.

## Bezpečnost a soukromí

- API klíče se ukládají šifrovaně v profilu tvého uživatele (Windows DPAPI / macOS Keychain).
- Pro nahrávání aplikace potřebuje mikrofon; na Macu potřebuje pro automatické psaní a vkládání také oprávnění Zpřístupnění. Nepotřebuje kameru, polohu ani snímání obrazovky.
- Historie diktování se neukládá, ukládají se jen souhrnné statistiky a tvůj slovník.

## Ověření staženého souboru (SHA256)

Ke každému vydání je v Releases přiložený `SHA256SUMS-win.txt` (Windows) / `SHA256SUMS-mac.txt` (macOS).

```powershell
# Windows (PowerShell)
Get-FileHash ".\Local_Sonix-Portable-0.2.2-x64.exe" -Algorithm SHA256
```

```bash
# macOS / Linux
shasum -a 256 "Local_Sonix-0.2.2-arm64.dmg"
```

Hodnota musí sedět s příslušným řádkem v `SHA256SUMS-win.txt` (Windows) / `SHA256SUMS-mac.txt` (macOS).
