# Local Sonix - user guide and settings

[Back to downloads](README.md#english) | [Český návod](NAVOD.md)

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
