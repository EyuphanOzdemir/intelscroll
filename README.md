# IntelScroll

A download and introduction page for IntelScroll, with a generated browser app
in `app/` and Android APK downloads.

Website: https://eyuphanozdemir.github.io/intelscroll/

Download: https://github.com/EyuphanOzdemir/intelscroll/releases/download/v1.5.0/IntelScroll-1.5.0.apk

IntelScroll turns your topics into short facts, concepts, outlines, visual diagrams, Q&A, quizzes, quotations, comparisons, and true/false questions using your chosen AI provider. An invitation code unlocks Gemini 3.1 Flash-Lite during first-launch setup. Email ozdemireyuphan@gmail.com to request a code, or continue without one and add your own AI provider on Models. No API credential is bundled in the APK; provider keys are stored securely on the device. Availability depends on quotas and provider limits. Prompts are sent to your chosen provider, and usage charges may apply.

## Why IntelScroll?

IntelScroll gives the spare moments you might spend doomscrolling a useful direction: short learning cards about subjects you choose. Create broad or specific topics, add custom instructions, and generate new content on demand in nine learning modes. The app is free with no IntelScroll subscription; AI provider usage may incur charges.

Apps such as [Deepstash](https://deepstash.com/) help readers discover ideas from a published library and offer free and paid plans. IntelScroll focuses on generating cards for your own topics with your chosen AI model. Save entries locally, share them, or export a topic's saved entries as a text file. AI-generated content can contain mistakes.

## Current controls

- Swipe right across the content panel, or tap **New**, to generate a card.
- Swipe left, or tap **Save**, to save the current card.
- Tap **Share** to share a card, or **Expand** to add a thorough explanation once per card while preserving its format. Diagram mode keeps the original visual alongside the explanation.
- Scroll vertically to read. Hide or show the topic, model and mode controls as needed.

## Install on Android

1. Download the APK on a phone running Android 7.0 or later.
2. Open it and allow installation from your browser or file manager when Android prompts.
3. Install IntelScroll. On first launch, enter an invitation code to unlock the Gemini starter, or choose "I don't have one" and add your own AI provider on Models. Continuing without a code permanently dismisses invitation setup and hides the starter. Add a topic and start learning.

Existing users complete invitation setup once after updating; custom models and saved entries are retained.

## New in 1.5.0

- Nine learning modes, including Quotes, Comparison (Compare in the app), and True/False.
- Rendered Mermaid diagrams for relationship maps, mindmaps, timelines, process flows, and more. The renderer is bundled in the app.
- More detailed expansions that preserve the selected format and the original quiz or true/false answers.
- Clear messages when the model cannot provide suitable content, including reliable quotations.

Install the new APK over the existing app to retain saved entries and settings.

The APK contains the app's JavaScript and runs without Metro or a computer. Internet access is needed to reach hosted AI providers.

## Website hosting

The introduction page and generated `app/` directory are published with GitHub
Pages from the main branch. The APK is a GitHub release asset. Keep `.nojekyll`
at the site root. Generated JavaScript and assets are published; keys, app
settings, private signing files, and the native source tree are not included.

## Browser app

App URL: https://eyuphanozdemir.github.io/intelscroll/app/

Choose an AI model on Models, create a subject on Topics, and use New, Expand,
Save, and Share on Home. Saved cards can be shared or downloaded by topic as
UTF-8 text. Use a provider that permits browser requests; model discovery can
fail independently of generation. No live provider has yet been verified
by this implementation's automated smoke test.

On iPhone, open the app in Safari → Share → Add to Home Screen. Installation is
optional. After an online visit the app shell and locally saved content can be
opened offline; new generation needs internet access. Accept the Reload prompt
to apply an app update while retaining your saved content.

Topics, settings, invitation status, saved cards, and API keys live in this
browser's localStorage. Clearing site data removes them. Data is separate from
Android and other devices, with no cloud sync. Browser API keys are remembered
in the browser profile, rather than a native secure keychain.

Maintainers: from the private application checkout, run
`./scripts/stage-web.ps1`, inspect this checkout's diff and status, then publish
only when validation is complete. The script builds and copies assets without
committing or pushing. Verify the app URL, icon/manifest/worker URLs, and original
APK link after publication. Physical iPhone sharing and installation still need
verification.

Azure Functions CORS now permits the published website origin and local preview
origins on port 4173; preflight responses were verified on 15 October 2026.
Verify a valid and invalid invitation in the browser after deploying changes to
invitation support.
