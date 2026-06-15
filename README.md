# Local Sonix — stažení

Local Sonix je lokální desktopová aplikace pro diktování a realtime přepis řeči. Běží u tebe v počítači, používá tvoje vlastní API klíče a neukládá historii diktování.

## Stáhnout aplikaci

Hotové soubory ke stažení najdeš vždy v sekci **[Releases](../../releases)** (vpravý sloupec na hlavní stránce repozitáře, nebo záložka „Releases"). **Nestahuj** zelené tlačítko `Code → Download ZIP` — to je jen pro vývojáře.

### Windows

| Soubor | Pro koho |
|--------|----------|
| `Local Sonix-Portable-…-x64.exe` | **Doporučeno** — stáhnout a rovnou spustit, nic se neinstaluje |
| `Local Sonix-Setup-…-x64.exe` | Klasický instalátor (zástupce v nabídce Start, odinstalace) |
| `Local Sonix-…-win.zip` | Rozbalit a spustit `Local Sonix.exe` |

Build je nepodepsaný, takže Windows SmartScreen nebo antivirus může při prvním spuštění zobrazit varování („neznámý vydavatel"). Není to virus — jen nemá placený podpisový certifikát. Klikni na `Více informací → Přesto spustit`. Pro jistotu si ověř SHA256 (níže).

### macOS (Apple Silicon — M1/M2/M3/M4)

| Soubor | Pro koho |
|--------|----------|
| `Local Sonix-…-arm64.dmg` | **Doporučeno** — otevři, přetáhni do Aplikací |
| `Local Sonix-…-arm64-mac.zip` | Doplňková varianta |

Je to **unsigned beta**, takže macOS Gatekeeper aplikaci napoprvé zablokuje. Spusť ji takto: v `Aplikace` na ikonu **pravý klik → Otevřít → Otevřít**. Stačí jednou, pak už jde spouštět normálně.

## První spuštění

1. Otevři **Nastavení**.
2. Vlož **Soniox** API klíč (povinný pro realtime přepis).
3. Volitelně vlož **OpenAI** nebo **Mistral** klíč pro AI úpravu textu po zastavení nahrávání.
4. Nastav klávesovou zkratku a region.

## Bezpečnost a soukromí

- API klíče se ukládají **šifrovaně** v profilu tvého uživatele (Windows DPAPI / macOS Keychain). Aplikace je neposílá nikam jinam než vybranému providerovi.
- Aplikace žádá **jen mikrofon**. Žádná kamera, poloha ani obrazovka.
- **Neukládá se historie diktování** — jen souhrnné statistiky a tvůj slovník.

## Ověření staženého souboru (SHA256)

Ke každému vydání je v Releases přiložený `SHA256SUMS.txt`. Ověření:

```powershell
# Windows (PowerShell)
Get-FileHash ".\Local Sonix-Portable-0.1.53-x64.exe" -Algorithm SHA256
```

```bash
# macOS / Linux
shasum -a 256 "Local Sonix-0.1.53-arm64.dmg"
```

Hodnota musí sedět s tím, co je v `SHA256SUMS.txt` u daného vydání.
