# Local Sonix - download

[Čeština](#čeština) | [English](#english)

---

## Čeština

Local Sonix je lokální desktopová aplikace pro diktování a realtime přepis řeči. Běží u tebe v počítači, používá tvoje vlastní API klíče a neukládá historii diktování.

## Stáhnout aplikaci

Hotové soubory najdeš v sekci **[Releases](../../releases)**. **Nestahuj** zelené tlačítko `Code -> Download ZIP` - to je jen pro vývojáře.

### Windows

| Soubor | Pro koho |
|--------|----------|
| `Local.Sonix-Portable-0.1.55-x64.exe` | **Doporučeno** - stáhnout a rovnou spustit, nic se neinstaluje |
| `Local.Sonix-Setup-0.1.55-x64.exe` | Klasický instalátor se zástupcem v nabídce Start |
| `Local.Sonix-0.1.55-win.zip` | Rozbalit a spustit `Local Sonix.exe` |

Build je nepodepsaný, takže Windows SmartScreen nebo antivirus může při prvním spuštění zobrazit varování o neznámém vydavateli. Není to virus - aplikace jen nemá placený podpisový certifikát. Klikni na `Více informací -> Přesto spustit`.

### macOS (Apple Silicon - M1/M2/M3/M4)

| Soubor | Pro koho |
|--------|----------|
| `Local.Sonix-0.1.55-arm64.dmg` | **Doporučeno** - otevři a přetáhni aplikaci do Aplikací |
| `Local.Sonix-0.1.55-arm64-mac.zip` | Doplňková varianta |

Je to **unsigned beta**, takže macOS Gatekeeper aplikaci napoprvé zablokuje. Spusť ji takto: v `Aplikace` na ikonu **pravý klik -> Otevřít -> Otevřít**. Stačí jednou, pak už půjde spouštět normálně.

## První spuštění

1. Otevři **Nastavení**.
2. Vlož **Soniox** API klíč pro realtime přepis.
3. Volitelně vlož **OpenAI** nebo **Mistral** klíč pro AI úpravu textu po zastavení nahrávání.
4. Nastav klávesovou zkratku, jazyk a region.

## Bezpečnost a soukromí

- API klíče se ukládají šifrovaně v profilu tvého uživatele (Windows DPAPI / macOS Keychain).
- Aplikace žádá jen mikrofon. Nepotřebuje kameru, polohu ani obrazovku.
- Historie diktování se neukládá, ukládají se jen souhrnné statistiky a tvůj slovník.

## Ověření staženého souboru (SHA256)

Ke každému vydání je v Releases přiložený `SHA256SUMS.txt`.

```powershell
# Windows (PowerShell)
Get-FileHash ".\Local.Sonix-Portable-0.1.55-x64.exe" -Algorithm SHA256
```

```bash
# macOS / Linux
shasum -a 256 "Local.Sonix-0.1.55-arm64.dmg"
```

Hodnota musí sedět s příslušným řádkem v `SHA256SUMS.txt`.

---

## English

Local Sonix is a local desktop app for dictation and real-time speech transcription. It runs on your computer, uses your own API keys, and does not store dictation history.

## Download The App

Ready-to-use files are available in **[Releases](../../releases)**. Do **not** use the green `Code -> Download ZIP` button - that is only for developers.

### Windows

| File | Use case |
|------|----------|
| `Local.Sonix-Portable-0.1.55-x64.exe` | **Recommended** - download and run, no installation needed |
| `Local.Sonix-Setup-0.1.55-x64.exe` | Standard installer with Start menu shortcut |
| `Local.Sonix-0.1.55-win.zip` | Unzip and run `Local Sonix.exe` |

The build is unsigned, so Windows SmartScreen or antivirus software may show an unknown publisher warning on first launch. It is not a virus - the app simply does not have a paid code-signing certificate. Click `More info -> Run anyway`.

### macOS (Apple Silicon - M1/M2/M3/M4)

| File | Use case |
|------|----------|
| `Local.Sonix-0.1.55-arm64.dmg` | **Recommended** - open it and drag the app to Applications |
| `Local.Sonix-0.1.55-arm64-mac.zip` | Alternative download |

This is an **unsigned beta**, so macOS Gatekeeper may block the app the first time. Open it like this: in `Applications`, **right-click the app -> Open -> Open**. You only need to do this once.

## First Launch

1. Open **Settings**.
2. Add your **Soniox** API key for real-time transcription.
3. Optionally add an **OpenAI** or **Mistral** key for AI text cleanup after recording stops.
4. Set your hotkey, language, and region.

## Security And Privacy

- API keys are stored encrypted in your user profile (Windows DPAPI / macOS Keychain).
- The app only asks for microphone access. It does not need camera, location, or screen access.
- Dictation history is not stored. Only summary statistics and your dictionary are saved locally.

## Verify The Download (SHA256)

Each release includes a `SHA256SUMS.txt` file.

```powershell
# Windows (PowerShell)
Get-FileHash ".\Local.Sonix-Portable-0.1.55-x64.exe" -Algorithm SHA256
```

```bash
# macOS / Linux
shasum -a 256 "Local.Sonix-0.1.55-arm64.dmg"
```

The result must match the corresponding line in `SHA256SUMS.txt`.
