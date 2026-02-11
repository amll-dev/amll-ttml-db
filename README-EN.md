<div align=center>

[简体中文版本](https://github.com/amll-dev/amll-ttml-db/blob/main/README.md)
/
[English Version](https://github.com/amll-dev/amll-ttml-db/blob/main/README-EN.md)

# **AMLL TTML DataBase**

This is the TTML word-level lyric database for **Apple Music-like Lyrics (AMLL)**, designed to support high-performance lyric display.

**—— AMLL Ecosystem ——**

[Apple Music-like Lyrics](https://github.com/amll-dev/applemusic-like-lyrics)
/
[AMLL TTML Tool (Editor)](https://github.com/amll-dev/amll-ttml-tool)
/
[AMLL Editor (Next-Gen Editor)](https://github.com/amll-dev/amll-editor) (WIP)
/
[AMLL Page (Web Player)](https://github.com/apoint123/amll-page)

**—— Key Documentation ——**

[Review Guidelines](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/instruction.md)
/
[TTML Specification](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification.md)

</div>

---

> [!TIP]
> ## 📣 Announcement
> 
> We are recruiting content reviewers and long-term maintainers!
> For more details, please visit the [Discussion Thread](https://github.com/amll-dev/amll-ttml-db/discussions/8127).
> Thank you for supporting this project!

---

> [!Warning]
> **Notice to Developers:**
> This repository has been migrated to the [amll-dev](https://github.com/amll-dev) organization. The new URL is [https://github.com/amll-dev/amll-ttml-db](https://github.com/amll-dev/amll-ttml-db). Please update your downstream repositories accordingly.

---

> [!Important]
> 
> **A note for non-Chinese contributors:**
> This database is primarily for Chinese speakers. However, if you are translating lyrics into other languages, please specify the language using the "xml:lang" attribute. If a Chinese (or other language) version already exists, please preserve existing content.
> Since the AMLL software suite currently does not support multilingual translations natively, users should obtain single-language translated lyrics via third-party tools (e.g., [ranhengzhang/ttml-trans-filter](https://github.com/ranhengzhang/ttml-trans-filter)) before use.
> For more details: 👉 [TTML Specification (Section 5.3)](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification-en.md#53-multi-language-and-background-support).
> ---
> 
> 
> *Refer to the original README or the formatting examples below for code snippets regarding `xml:lang` usage.*

---

# Lyric Submission Workflow

## 1. Check for Duplicates

**Policy:** We primarily accept lyrics sourced from [Netease Cloud Music (NCM)](https://music.163.com). We also accept IDs from [Apple Music](https://music.apple.com), [QQ Music](https://y.qq.com), and [Spotify](https://open.spotify.com). Your submission must include an ID from at least one of these platforms.

> [!Tip]
> During review, we assume audio files across different platform IDs are identical or have an offset of less than 1ms. We strictly quality-check lyrics against the **NCM ID**. If you are submitting a special version for another platform, please specify this.

> [!WARNING]
> Submissions prior to 2024 may not fully comply with current standards. If you wish to correct legacy content, your contribution will be prioritized.

### Option A: Search via AMLL TTML Lyric Site (Recommended)

Visit the [Search Page](https://amlldb.bikonoo.com/search.html), enter the song title, and click <kbd>Search</kbd>. If no results are found, the song is open for submission.

### Option B: Search within this Repository

Obtain the Song ID (refer to [Metadata Guide](https://github.com/amll-dev/amll-ttml-tool/wiki/%E6%AD%8C%E8%AF%8D%E5%85%83%E6%95%B0%E6%8D%AE)) and search for it in this repo.

### Option C: SearchInAMLLDB

Visit [SearchInAMLLDB](https://steamfinder.github.io/search-in-amlldb), click <kbd>Update Database</kbd>, then search by title.

### Check for "Placeholder" Issues

Before working on a song, check the [Issues](https://github.com/amll-dev/amll-ttml-db/issues) tab. If an Open Issue exists with the **"Lyric Creation Placeholder"** (歌词制作占位) label, someone is already working on it.

> [!WARNING]
> **Priority Rule:** Submissions made within 7 days of creating a Placeholder Issue are prioritized, regardless of other submissions. Beyond 7 days, submissions are reviewed in chronological order. We recommend referencing your Issue in your Pull Request (PR).

## 2. Create Lyrics

### Requirements

Refer to the [Review Guidelines](https://www.google.com/search?q=./instructions/instruction.md) for full details.

#### Critical Rules

* **No Metadata in Body:** Do not include credits (Composer, Lyricist, Editor) in the lyric text. Use AMLL TTML Tool metadata fields instead.
* **No Empty Lines:** Use **End Time** tags to allow the player to generate instrumental intervals automatically.
* **Chronological Order:** Start times must not be later than End times.
* **English Spacing:** Ensure standard spacing between English words.
* **Modifications:** When correcting existing lyrics, state the reason and the original PR in the description.
* **Restrictions:** Translations for politically sensitive or humanitarian-violating songs are prohibited.
* *NSFW Content:* Translations should be accurate but tactful. Explicit content may delay review.



#### General Standards

* **Word-Level Accuracy:** Timing deviation must be within ±100ms.
* **Rich Features:** Utilize background vocals and duet features where appropriate.
* **Translation/Romanization:** Use `<span ttm:role="x-translation">` or `<span ttm:role="x-roman">` tags.

> [!NOTE]
> Apple Music's native TTML files often have timing drift. Please do not submit them without manual correction/verification.

### Tools

We recommend the [AMLL TTML Tool](https://amll-ttml-tool.stevexmh.net) or the [AMLL Editor](https://editor.amll.dev).

**Quick Guide for AMLL TTML Tool:**

1. **Import:** <kbd>File</kbd> -> <kbd>Import Lyrics</kbd> (Supports TTML, LRC, YRC, QRC, etc.).
2. **Audio:** Load audio file in the bottom left.
3. **Metadata:** <kbd>Edit</kbd> -> <kbd>Edit Metadata</kbd>.
4. **Edit:** Adjust segmentation, attributes, translations.
5. **Timing (Shortcuts):**
* <kbd>F</kbd>: Set **Start Time**.
* <kbd>G</kbd>: Set **End Time**, move to next word, set next **Start Time**.
* <kbd>H</kbd>: Set **End Time**, move to next word (creates a gap/instrumental).


6. **Export:** <kbd>File</kbd> -> <kbd>Save TTML</kbd>.

## 3. Submit Lyrics

* **Via Issue (Recommended):** Use the [Submission Template](https://github.com/amll-dev/amll-ttml-db/issues/new?template=submit-lyric.yml).
* **Via Pull Request:** Ensure strictly correct formatting to avoid bot errors.
* **Via Website:** Submit through the [Creator Center](https://amlldb.bikonoo.com/manage.html).

> **Missing Audio?** If the song is unavailable on NCM, provide a download link in the Issue/PR comments or upload it via the Creator Center.

## 4. Review Process

Submissions are manually reviewed by the **AMLL TTML Lyric Review Team**.

**Common Rejection Reasons:**

* Timing errors or excessive offset.
* **Over-correction:** Forcing effects where they don't belong or intentionally using wrong timing for visual effects.
* **Role Errors:** Incorrect distinction between Main Vocals, Background Vocals, and Duets.

> [!TIP]
> **Bot Commands (in PR comments):**
> * `/update {Link}`: Update the lyric file (re-triggers review).
> * `/label {Label}`: Add a specific label.
> * `/close {Reason}`: Close the submission.
> 
> 

---

# Using the Database

## Clients

* **AMLL Player:** Native client with local playback and WebSocket support. [Download Here](https://github.com/amll-dev/applemusic-like-lyrics/actions/workflows/build-player.yaml).
* **AMLL Page:** Web-based player. [View Here](https://github.com/apoint123/amll-page).
* **UniLyric:** Universal lyric converter and SMTC broadcaster. Highly recommended for broad compatibility. [View Here](https://github.com/apoint123/Unilyric).

## Mirrors (for BetterNCM)

If the official source is unstable, add a mirror string in "Settings - Lyric Sources":

* **Steve-xmh Mirror:**
`61ba6770-f02f-11ef-a3ae-5396943709e6|AMLL%20TTML%20Database%20(Mirror)||ttml|https://amll-ttml-db.stevexmh.net/ncm/[NCM_ID]`

*(See original README for community mirrors by HelloZGY and Luorix)*

## Integration for Developers

We encourage developers to integrate this database. Attribution is appreciated.

**Directory Structure:**

* `ncm-lyrics/` (Netease Cloud Music)
* `qq-lyrics/` (QQ Music)
* `am-lyrics/` (Apple Music)
* `spotify-lyrics/` (Spotify)

**Available Formats:** `.ttml` (Original), `.lrc`, `.yrc`, `.qrc`, `.lys`, `.eslrc`.

**Raw Data:** Available in `raw-lyrics/` or via `metadata/raw-lyrics-index.jsonl`.

---

# License

External data follows the original provider's license. Contributor-created content is licensed under **CC0 1.0**.

---

# Credits

Join the discussion: QQ Group `719423243`.
Thanks to all contributors!

---
