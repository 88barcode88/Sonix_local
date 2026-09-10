# Local Sonix - download

[Čeština](#čeština) | [English](#english)

---

## Čeština

Local Sonix je lokální desktopová aplikace pro diktování a realtime přepis řeči. Běží u tebe v počítači, používá tvoje vlastní API klíče a neukládá historii diktování.

## Stáhnout aplikaci

Aktuální verze **[0.2.2](https://github.com/88barcode88/Sonix_local/releases/tag/v0.2.2)**: [Windows Portable](https://github.com/88barcode88/Sonix_local/releases/download/v0.2.2/Local_Sonix-Portable-0.2.2-x64.exe) · [Mac DMG](https://github.com/88barcode88/Sonix_local/releases/download/v0.2.2/Local_Sonix-0.2.2-arm64.dmg). Všechny soubory najdeš v **[Releases](../../releases)**. **Nestahuj** zelené tlačítko `Code -> Download ZIP` - to je jen pro vývojáře.

### Windows

| Soubor | Pro koho |
|--------|----------|
| `Local_Sonix-Portable-0.2.2-x64.exe` | **Doporučeno** - stáhnout a rovnou spustit, nic se neinstaluje |
| `Local_Sonix-Setup-0.2.2-x64.exe` | Klasický instalátor se zástupcem v nabídce Start |
| `Local_Sonix-0.2.2-win.zip` | Rozbalit a spustit `Local Sonix.exe` |

Build je nepodepsaný, takže Windows SmartScreen může při prvním spuštění zobrazit varování o neznámém vydavateli. Po ověření zdroje a SHA256 můžeš pokračovat přes `Více informací -> Přesto spustit`, pokud tuto možnost systém nabízí. Samotné chybějící podepsání není důkazem bezpečnosti souboru.

### macOS

Pro Macy s čipem **Apple Silicon (řada M)**. Tento balíček nepodporuje Macy s procesorem Intel.

| Soubor | Pro koho |
|--------|----------|
| `Local_Sonix-0.2.2-arm64.dmg` | **Doporučeno** - otevři a přetáhni aplikaci do Aplikací |
| `Local_Sonix-0.2.2-arm64-mac.zip` | Doplňková varianta |

Je to **unsigned beta**, takže macOS Gatekeeper aplikaci napoprvé zablokuje. Spusť ji takto: v `Aplikace` na ikonu **pravý klik -> Otevřít -> Otevřít**. Stačí jednou, pak už půjde spouštět normálně.

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

---

## English

Local Sonix is a local desktop app for dictation and real-time speech transcription. It runs on your computer, uses your own API keys, and does not store dictation history.

## Download The App

Current version **[0.2.2](https://github.com/88barcode88/Sonix_local/releases/tag/v0.2.2)**: [Windows Portable](https://github.com/88barcode88/Sonix_local/releases/download/v0.2.2/Local_Sonix-Portable-0.2.2-x64.exe) · [Mac DMG](https://github.com/88barcode88/Sonix_local/releases/download/v0.2.2/Local_Sonix-0.2.2-arm64.dmg). All files are available in **[Releases](../../releases)**. Do **not** use the green `Code -> Download ZIP` button - that is only for developers.

### Windows

| File | Use case |
|------|----------|
| `Local_Sonix-Portable-0.2.2-x64.exe` | **Recommended** - download and run, no installation needed |
| `Local_Sonix-Setup-0.2.2-x64.exe` | Standard installer with Start menu shortcut |
| `Local_Sonix-0.2.2-win.zip` | Unzip and run `Local Sonix.exe` |

The build is unsigned, so Windows SmartScreen may show an unknown publisher warning on first launch. After verifying the source and SHA256, you can use `More info -> Run anyway` if the system offers it. A missing signature alone does not establish that a file is safe.

### macOS

For Macs with **Apple Silicon (M series)**. This package does not support Intel Macs.

| File | Use case |
|------|----------|
| `Local_Sonix-0.2.2-arm64.dmg` | **Recommended** - open it and drag the app to Applications |
| `Local_Sonix-0.2.2-arm64-mac.zip` | Alternative download |

This is an **unsigned beta**, so macOS Gatekeeper may block the app the first time. Open it like this: in `Applications`, **right-click the app -> Open -> Open**. You only need to do this once.

## First Launch

1. Open **Settings**.
2. Add your **Soniox** API key for real-time transcription.
3. Optionally add an **OpenAI** or **Mistral** key for AI text cleanup after recording stops.
4. Set your hotkey, language, and region.

## API Keys: What You Need

| Feature | Required key |
|---------|--------------|
| Live cloud transcription | Soniox |
| AI cleanup of finished text | OpenAI **or** Mistral, matching your selected provider |
| Local Whisper transcription on Windows | None; download the runtime and model in the app first |

Create keys in your own provider accounts. Available credit, plans and API limits determine usage; any API charges are paid directly to the provider. Enter each key under **Settings → API Keys** and use its **Save** button. Do not share keys in emails or screenshots. Normal setup does not require editing files or environment variables.

### Get a Soniox Key

1. Sign up or sign in at [Soniox Console](https://console.soniox.com).
2. If you need EU processing, complete the next section first.
3. Create a project and its API key. Check available credit and billing in your account.
4. Paste the key into **Soniox API key** in Local Sonix and click **Save Soniox key**.
5. Set **Soniox region** to match the project that owns the key. Select **EU** for an EU project.
6. Try a short realtime transcription.

### Enable Soniox EU Processing

**Selecting EU in the app or sending an email alone is not enough.** Soniox must enable regional projects on your account first. You then need an EU project, its API key and the EU region selected in the app.

1. Email **[support@soniox.com](mailto:support@soniox.com)**. Replace the account email below; do not include your API key:

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

2. Wait for support to confirm activation.
3. Create a **new project in the EU region** in Soniox Console, then create its API key.
4. Save that key in Local Sonix and select **Soniox region → EU**. Do not reuse a key from another region.
5. Test a short transcription to check the key/region combination. Verify the project region in the console; successful transcription alone does not prove EU configuration.

The standard global Soniox endpoint processes data in the **United States**. The app selects EU endpoints when you choose EU. Soniox states that a regional project's audio and transcripts remain in that region; account information, usage statistics and billing data may be processed elsewhere. See [Soniox data residency](https://soniox.com/docs/data-residency).

**Soniox's EU setting does not apply to OpenAI or Mistral.** AI transcription sends finished text to the selected AI provider when its key is saved, including text produced by local Whisper. Use realtime mode for Soniox transcription without an additional AI service.

### Get an OpenAI Key

1. Sign in at [OpenAI Platform – API keys](https://platform.openai.com/api-keys).
2. Select your project and create a new secret API key. Copy it when created and store it securely.
3. Check API billing, available credit and account limits.
4. Paste it into **OpenAI API key** in Local Sonix and click **Save OpenAI key**.
5. Choose **OpenAI**, an available model and **AI transcription** mode for AI cleanup.

See the [official OpenAI API quickstart](https://developers.openai.com/api/docs/quickstart).

### Get a Mistral Key

1. Sign in at [Mistral Studio](https://console.mistral.ai).
2. Open **API Keys → Create new key**, name the key and set its expiration.
3. Copy it immediately; the full key is only shown once. Check your account plan and limits.
4. Paste it into **Mistral API key** in Local Sonix and click **Save Mistral key**.
5. Choose **Mistral**, an available model and **AI transcription** mode for AI cleanup.

See the [official Mistral guide](https://docs.mistral.ai/getting-started/quickstarts/studio/activate-and-generate-api-key).

## Using The App

1. Allow microphone access and choose a mode: **realtime** displays text as you speak; **AI transcription** cleans up text after recording stops.
2. Start recording with the button or configured hotkey, dictate a short message, then press the hotkey again to stop.
3. Wait for processing to finish. With copying enabled, the result is placed on the clipboard.
4. Paste into your target app using **Ctrl+V** on Windows or **Cmd+V** on Mac. Automatic paste can be enabled in Settings.

To dictate into another program, place the cursor in its text field before using the global hotkey. Review the result before sending or saving it, especially names, numbers and AI edits.

## Settings Guide

Settings has **Basics**, **Transcription** and **Output** tabs. Use the corresponding save button for keys, the hotkey, dictionary and custom instruction.

| Setting | Purpose |
|---------|---------|
| App language | Choose Czech, English or German for the interface. |
| Hotkey | Start/stop recording outside the app window. Choose a combination not used by another program. |
| Transcription source | Soniox cloud or local Whisper. Whisper shows text only after recording stops. |
| Transcription language | Select the spoken language or automatic detection, independently of the interface language. |
| Soniox region and model | Match the region to the project/key. Choose a listed model; keep the default for initial setup. |
| Wait after a speech pause | Longer waits may reduce premature sentence boundaries but increase delay. |
| Filler words | Optionally filter filler words from the transcript. |
| AI provider and model | Choose OpenAI or Mistral for finished-text cleanup. Requires that provider's key; without it only local repetition cleanup is used. |
| AI output style | Simple keeps flowing text; structured organizes topics, paragraphs or lists. |
| Custom instruction | Edit the structured-style prompt and click **Save instruction**. **Restore default** brings back the original instruction. |
| Copying and trailing space | Control clipboard copying and whether a space is appended. |
| Automatic paste after stopping | Attempts to paste the finished result into the active text field. Paste manually if it fails. |
| Type realtime directly under cursor | Types into the active field during realtime recording. Keep the target window unchanged. AI mode waits for the finished result. |
| Dictionary | Save custom names and specialist terms. Soniox receives them as context for subsequent recordings. |
| Statistics | Show usage totals and estimated time savings/cost. Check the provider for actual billing. |

### Local Whisper On Windows

Select local Whisper in Settings, manually download the **runtime** and **model**, and wait until both are ready. Downloads require internet; local transcription itself needs no API key. Models include `medium-q5_0` (about 539 MB), `large-v3-q5_0` (about 1.08 GB) and `large-v3` (about 3.1 GB). Larger models need more memory and may be slower.

The idle shutdown setting controls how long Whisper stays in memory between recordings. Shorter periods free memory sooner; longer periods can make subsequent transcription faster. You can delete the model in Settings.

**The current Mac beta has no configured local Whisper runtime.** Use Soniox on Mac. Local Whisper followed by AI cleanup with a saved OpenAI/Mistral key is not fully offline: the finished text is sent to that provider.

## Troubleshooting

- **Transcription will not start:** check microphone access, internet for cloud processing, the saved key, its validity and credit. Soniox project, key and app region must match.
- **EU key fails:** confirm support enabled regional access and that the key belongs to an EU project. If EU processing is required, do not switch to the global region as a workaround.
- **AI cleanup fails:** check the selected provider's key, model availability and API limits. A Soniox key does not replace an OpenAI/Mistral key.
- **Hotkey does nothing:** choose another combination not reserved by the system or another app.
- **Mac cannot paste:** allow Local Sonix in system **Privacy & Security → Accessibility**. Also check **Microphone** permission for recording. Manual clipboard paste remains available.
- **Whisper is not ready:** on Windows, check both runtime and selected-model downloads. Loading a large model for the first time can take longer; see diagnostics in Settings.

## Security And Privacy

- API keys are stored encrypted in your user profile (Windows DPAPI / macOS Keychain).
- Recording needs microphone access; automatic typing and pasting on Mac also require Accessibility permission. The app does not need camera, location, or screen capture access.
- Dictation history is not stored. Only summary statistics and your dictionary are saved locally.

## Verify The Download (SHA256)

Each release includes a `SHA256SUMS-win.txt` (Windows) / `SHA256SUMS-mac.txt` (macOS) file.

```powershell
# Windows (PowerShell)
Get-FileHash ".\Local_Sonix-Portable-0.2.2-x64.exe" -Algorithm SHA256
```

```bash
# macOS / Linux
shasum -a 256 "Local_Sonix-0.2.2-arm64.dmg"
```

The result must match the corresponding line in `SHA256SUMS-win.txt` (Windows) / `SHA256SUMS-mac.txt` (macOS).
