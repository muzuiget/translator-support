# Quick Start

This extension uses Chrome's on-device model for translation. Model setup is required upon first use.

### About Models

Chrome 138 introduced built-in AI capabilities, including two types of models for translation:

* **Translation-Specific Models**: Small, single-language models, each responsible for translating one **Language Pair**, such as `English -> Chinese`.
* **Generative Models**: Large, multilingual models, namely Gemini Nano, which achieve translation via prompting.

This extension uses **Translation-Specific Models**, which have low hardware requirements and are extremely fast even when using CPU computation.

Furthermore, Chrome also provides a **Language Detection Model** used to determine the language of a given text.

Therefore, this extension is essentially a model scheduler:

1. Call the **Language Detection Model** to determine the **Source Language**.
2. Users select the **Target Language**.
3. If the **Language Pair** model exists, that model is used for translation.

### Model Setup

For a quick start, it's suggested that you download only one **Language Pair** model first, such as `English -> Chinese`.

1. Open the extension interface and go to the **Settings > Models** panel.
2. Select the **Source Language** as `English`.
3. Select the **Target Language** as `Chinese` (or your native language).
4. Click the **Save** button.

The log panel at the bottom will output model information; `Save success.` indicates successful saving.

### Start Translation

Open a YouTube page:

1. Open the extension interface and switch to the **Translation** panel.
2. Select the **Target Language**.
3. Select the **Page Elements** to translate.

### Frequently Asked Questions

**Question: The download progress seems to be stuck.**

This appears to be a [bug][] in Chrome where it fails to correctly report the download progress, but the model is actually still downloading in the background.

You can check the model download status by opening `chrome://on-device-translation-internals/` in a new tab.

You can also manually download the required models on this page.

Once the status of the required models has changed to `Installed`, please return to the extension interface to set up the models again.

[bug]: https://issues.chromium.org/issues/444560478
