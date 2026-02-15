非常抱歉，我仔细检查了文档，发现确实保留了一些括号内的中文说明（如“矫枉过正”、“歌词制作占位”等）以及部分链接和图片属性中的中文。

以下是**彻底去除了所有残留中文字符**的纯净英文版 README。

---

```markdown
<div align=center>

[Simplified Chinese](https://github.com/amll-dev/amll-ttml-db/blob/main/README.md)
/
[English](https://github.com/amll-dev/amll-ttml-db/blob/main/README-EN.md)

# **AMLL TTML DataBase**

This is the TTML word-level lyric database for **Apple Music-like Lyrics (AMLL)**, providing support for enhanced lyric performance and display.

**—— AMLL Ecosystem ——**

[Apple Music-like Lyrics](https://github.com/amll-dev/applemusic-like-lyrics)
/
[AMLL TTML Tool (Lyric Editor)](https://github.com/amll-dev/amll-ttml-tool)
/
[AMLL Editor (Next-Gen Editor)](https://github.com/amll-dev/amll-editor) (In Development)
/
[AMLL Page (Web Player)](https://github.com/apoint123/amll-page)

**—— Important Documentation ——**

[Review Guidelines](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/instruction.md)
/
[TTML Specification](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification.md)

</div>

***

> [!TIP]
>
> ## Announcement
> We are actively recruiting content reviewers and long-term maintainers!
> For more information, please visit the [Announcement Thread](https://github.com/amll-dev/amll-ttml-db/discussions/8127).
> Thank you to all contributors for your support!

***

> [!Warning]
> **Notice to Developers:**
> This repository has been migrated to the [amll-dev](https://github.com/amll-dev) organization. The repository URL has been updated to https://github.com/amll-dev/amll-ttml-db. Please update your downstream repositories accordingly.

***

> [!Important]
>
> **A note for non-Chinese contributors:**
>
> This database is primarily for Chinese speakers. However, if you are translating lyrics into other languages, please specify it using the "xml:lang" attribute. If a Chinese (or other language) version already exists, please preserve the existing content.
>
> Since AMLL series software currently does not support multilingual translations natively, users should obtain single-language-translated lyrics by using third-party tools (e.g., [ranhengzhang/ttml-trans-filter](https://github.com/ranhengzhang/ttml-trans-filter)) before use.
>
> Looking for more details? 👉 [TTML Specification (Section 5.3)](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification-en.md#53-multi-language-and-background-support).
>
> ---
>
> *For demonstration purposes, the examples provided below are formatted. Please note that in an actual TTML file, the content is minified according to HTML standards. Keep this in mind when reading the examples and submitting files.*
>
> ---
>
> ###### Format 1:
>
> > **Example Code:**
> >
> > ```xml
> > <p begin="00:21.400" end="00:23.870" ttm:agent="v1" itunes:key="L1">
> >   <span begin="00:21.400" end="00:22.010">Lower</span>
> >   <span begin="00:22.200" end="00:23.010">Beings</span>
> >   <span ttm:role="x-translation" xml:lang="en-US">Lower beings</span>
> >   <span ttm:role="x-translation" xml:lang="ja-JP">劣等な生物たちよ</span>
> > </p>
> > ```
> >
> > **Example File:**
> >
> > [HOYOMiX/YMIR - Flare](https://github.com/amll-dev/amll-ttml-db/blob/main/raw-lyrics/1752080938784-68000793-8355bb14.ttml)
>
> ---
>
> ###### Format 2:
>
> > **Example Code:**
> >
> > ```xml
> > <iTunesMetadata xmlns="[http://music.apple.com/lyric-ttml-internal](http://music.apple.com/lyric-ttml-internal)">
> >   <translations>
> >     <translation type="subtitle" xml:lang="zh-Hans">
> >       <text for="L1">Dawn has not arrived</text>
> >     </translation>
> >     <translation type="subtitle" xml:lang="el-GR">
> >       <text for="L1">Πριν απ' την αυγή</text>
> >     </translation>
> >   </translations>
> > </iTunesMetadata>
> > ```
> >
> > **Example File:**
> >
> > [Darren Korb - Time Belongs to Us](https://github.com/amll-dev/amll-ttml-db/blob/main/raw-lyrics/1762708573944-68000793-qnjnaX11.ttml)
> >
> > ---
> >
> > *Although this format complies with the new standards of Apple Music, we strongly discourage using it because most programs utilizing amll-ttml-db cannot parse it. Furthermore, if you submit lyrics in this format via an Issue, the bot will automatically convert them to the first format.*

***

# Lyric Submission Workflow

## 1. Check for Duplicates

In principle, AMLL TTML DataBase primarily accepts lyrics sourced from [Netease Cloud Music (NCM)](https://music.163.com) to facilitate usage by the general user base. We also accept lyrics with source IDs from [Apple Music](https://music.apple.com), [QQ Music](https://y.qq.com), and [Spotify](https://open.spotify.com). Therefore, submitted TTML files must contain a valid ID from at least one of these four platforms.

> [!Tip]
>
> During the review process, we assume that the audio corresponding to all platform IDs listed in your submission is identical, or that the offset between audio files is less than 1ms. For lyrics in this library, we strictly perform quality assurance based on the **valid NCM ID**. **Exception:** If you have created and submitted a specific version tailored for another platform (due to audio differences), please specify this explicitly.

> [!WARNING]
>
> Due to historical reasons, submissions made prior to 2024 may contain content that does not fully comply with current standards. We ask for your understanding. If you have concerns about such content and the capacity to improve it, we welcome submissions for corrections, which will be processed with priority.

### Option A: Search via AMLL TTML Lyric Site (Recommended)

Please visit the [Search Interface](https://amlldb.bikonoo.com/search.html) of the AMLL TTML Lyric Site. Enter the name of the song you wish to submit and click the <kbd>Search</kbd> button. If no results are returned, no TTML lyrics currently exist for that song, and we welcome your submission.

> Thanks to [@cybaka520](https://github.com/cybaka520) for building the lyric site!

### Option B: Search within this Repository

Please refer to the [Lyric Metadata Guide](https://github.com/amll-dev/amll-ttml-tool/wiki/%E6%AD%8C%E8%AF%8D%E5%85%83%E6%95%B0%E6%8D%AE) to obtain the ID of the song you wish to submit. Search for this ID within this repository. If no files are found, no TTML lyrics exist, and we welcome your submission.

### Option C: Search via SearchInAMLLDB (Alternative)

Visit [SearchInAMLLDB](https://steamfinder.github.io/search-in-amlldb), click the <kbd>Update Database</kbd> button at the top to pull the latest data, enter the song name, and click <kbd>Query</kbd>. If no results are found, the song is open for submission.

> Thanks to [@SteamFinder](https://github.com/SteamFinder) for building the search tool!

### Check for "Lyric Creation Placeholder" Issues

If you are preparing to submit lyrics for a specific song, creating a **"Lyric Creation Placeholder"** Issue indicates that you have claimed the task. This prevents conflicts caused by multiple users submitting the same song simultaneously.

> [!WARNING]
>
> Contributors who publish a Placeholder Issue will have their submissions **prioritized for review** if submitted within **7 days** of the issue creation, regardless of whether others submit the same song during this period.
>
> If the submission exceeds this timeframe, we will review submissions in chronological order of receipt.
>
> The timeframe is determined by the **system timestamp of the Placeholder Issue** and the **system timestamp of the automatically created PR**.
>
> If you have published a Placeholder Issue and subsequently submitted a contribution, we suggest referencing your Issue in the comments to minimize potential disputes.

Please visit the [Issues](https://github.com/amll-dev/amll-ttml-db/issues) section of this repository and search for the song name. If there is no **Open** Issue with the **"Lyric Creation Placeholder"** label, the task has not been claimed, and we welcome your submission.

You may also search via the [AMLL TTML Lyric Site](https://amlldb.bikonoo.com/).

## 2. Create Lyrics

### Lyric Requirements

For full review details, please refer to the [Instruction Document](./instructions/instruction.md). The following is a summary of the basic requirements.

#### Mandatory Requirements

- **No Metadata in Body:** Do not include non-lyric information (e.g., Lyricist, Composer, Creator credits) within the lyric body.
  > We recommend using the AMLL TTML Tool's metadata function to store this information.
- **No Empty Lines:** Do not leave empty lines. Use **End Time** tags to allow the lyric player to automatically generate instrumental/interlude sections.
- **Chronological Order:** Word timing must not be erroneous (e.g., Start Time being later than End Time).
- **English Spacing:** For English songs, the interval between words must not exceed one space.
- **Modifications:** When correcting existing lyrics, you must state the reason for the modification and the original PR number in the supplementary description.
- **Restricted Content:** Translations are prohibited for songs involving political sensitivity or violations of humanitarian principles (Romanization is generally unrestricted). Mandarin Chinese songs generally do not require translation submissions.
  > For translations of potential NSFW (Not Safe For Work) content, we do not object to expressing the original meaning, but please ensure the translation is **tactful and measured**. Failure to do so may result in delayed review or rejection.

#### General Review Standards

- **Word-Level Precision:** Ensure timing deviations are within **±100ms**.
  > In principle, we still accept line-level lyrics. However, unless there are special circumstances, we strongly prefer word-level lyrics to provide the best user experience.
- **Feature Usage:** Fully utilize TTML features, such as background vocal lyrics and duet lyrics.
- **Translation/Romanization:** Provide translations and Romanization (where applicable).
  > For creators not using the AMLL TTML Tool, you can add translations by inserting `<span ttm:role="x-translation" xml:lang="...">...</span>` or Romanization by inserting `<span ttm:role="x-roman">...</span>` inside the `p` element of the relevant line.

> [!NOTE]
> You may use TTML lyric files sourced from Apple Music. However, these files are rarely perfectly accurate. Please avoid submitting them directly without correction, as they may be rejected by reviewers due to **excessive word offset**.

### Using AMLL TTML Tool

We recommend using the [AMLL TTML Tool](https://amll-ttml-tool.stevexmh.net) to create word-level lyrics.
> You may also use [AMLL Editor](https://editor.amll.dev) developed by [@Linho1219](https://github.com/Linho1219), which introduces features like <kbd>Auto-scroll with Playback</kbd> and other utilities.

**Prerequisites:**

1. A song audio file readable by the AMLL TTML Tool.
   > Encrypted formats are not supported.
2. A lyric file or plain text recognized by the AMLL TTML Tool.
   > Supported formats: TTML / LRC / ESLyric / YRC / QRC / Lyricify Syllable

**Steps:**

1. Click <kbd>File</kbd> -> <kbd>Import Lyrics</kbd> in the top left, select your format, and follow the prompts.
2. Load your audio file in the bottom left; adjust playback speed and volume as needed.
3. Click <kbd>Edit</kbd> -> <kbd>Edit Metadata</kbd> in the top left. Refer to the [Metadata Guide](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/instruction.md#1-%E5%85%83%E6%95%B0%E6%8D%AE) to complete the fields.
4. In the **Edit** interface, refine the lyrics (segment lines, change line attributes, add translations/romanization).
5. In the **Timing** interface, play the audio and use the following keys to synchronize:
   | Key | Description |
   | :--- | :--- |
   | <kbd>F</kbd> | Record **Current Position** as the **Start Time** of the current word. |
   | <kbd>G</kbd> | Record **Current Position** as **End Time**, move to the next word, and record **Current Position** as its **Start Time**. |
   | <kbd>H</kbd> | Record **Current Position** as **End Time**, then move to the next word.<br/>*Used to end a sentence or word to create an instrumental gap or reflect a singer's pause.* |
6. Preview the result in the **Preview** interface.
7. Save via <kbd>File</kbd> -> <kbd>Save TTML File</kbd>.

## 3. Submit Lyrics

- **Via Issue (Recommended):** Create a [Submit/Correct Lyrics Issue](https://github.com/amll-dev/amll-ttml-db/issues/new?template=submit-lyric.yml). Detailed instructions are available on that page.

- **Via Pull Request:** You can manually submit a PR. You must ensure your TTML file is **correctly formatted** and mimics the style of PRs submitted by the Bot in this repository.
   > This method avoids the Bot's auto-formatting behaviors (like "Reordering Metadata" or "Reordering Lines by Timestamp"). However, strictly ensure your file and PR format are perfect.

- **Via Website:** Submit via the [Creator Center](https://amlldb.bikonoo.com/manage.html) on the AMLL TTML Lyric Site. Log in, click <kbd>Upload</kbd>, and upload your TTML file. The site typically auto-fills the title from metadata.
   > Note: The website currently has fewer reviewers. For faster review, prioritize GitHub submissions.

> **Handling Missing Audio:**
> If your song has no available version on Netease Cloud Music, you can upload the audio file yourself:
> - **In Issues:** Provide a download link in the "Remarks" section.
> - **In Pull Requests:** Provide a download link in the PR Body under `Remarks` or in a Comment.
> - **In Creator Center:** Click <kbd>Content Management</kbd>, find your lyric entry, and click <kbd>Upload Audio</kbd>.

## 4. Review Process

To improve consistency and quality, lyrics are manually reviewed by the **AMLL TTML Lyric Review Team** based on the [Review Guidelines](./instructions/instruction.md).

If your submission is rejected, please modify it according to the reviewer's comments and resubmit. **Common reasons for rejection include:**

- **Timing Errors:** Word offsets are too large or incorrect.
- **Over-Correction:**
  - Forcing effects into songs where they are inappropriate.
  - Intentionally using incorrect timing to trigger specific visual effects.
- **Role Attribute Errors:**
  - Incorrectly distinguishing whether the singer is in a "Backing Vocal" state or a "Solo Duet" state.
  - Unless the lyric structure explicitly demands it, do not create two different states for the same singer's same performance style without a clear motive. (Performance styles include Lead, Rap, Harmony, etc.)

If you believe your lyrics do not contain the issues cited, please resubmit with an explanation to help the reviewer understand your intent, or request a different reviewer.

> [!TIP]
> **Bot Commands (in PR Comments):**
>
> * `/update {Direct Link to TTML File}`: Update the lyric file. This is considered a re-submission for review.
> * `/label {Label}`: Add [Appropriate Labels](https://github.com/amll-dev/amll-ttml-db/labels).
> * `/close {Reason}`: Self-close the submission (reason optional).
>
> *Note: The bot may have a 1-2 minute delay. It will react with a thumbs-up when processing.*

***

# Using the Database

## AMLL Player [Recommended]

AMLL Player is the native local client for Apple Music-like Lyrics. It supports local music playback and WebSocket server connection. [Download Here](https://github.com/amll-dev/applemusic-like-lyrics/actions/workflows/build-player.yaml)

It has built-in database search functionality. Import local songs, edit lyric override info, and search/import directly from AMLL TTML DB.

## AMLL Page

The online web version of AMLL Player. Aside from plugin capabilities, it is consistent with the Player. [Learn More](https://github.com/apoint123/amll-page)

> Thanks to [@apoint123](https://github.com/apoint123) for developing the web version!

## Apple Music-like Lyrics for BetterNCM [Stopped Maintenance]

This plugin has built-in support for this repository. Simply pin the **AMLL TTML Word-Level Lyric Database (Multi-Source Aggregation)** source to the top.

> If you wish to continue using the Netease Cloud Music client while using lyrics from this repository, please combine [amll-bncm-ws-connector](https://github.com/Steve-xmh/amll-bncm-ws-connector) with AMLL Player.

### Mirror Sources

If the official source is unstable (search failures, exceptions), you can add a mirror source in Plugin Settings -> `Lyric Sources` -> `Add from Lyric Source String`:

**Steve-xmh Mirror:** [@Steve-xmh](https://github.com/Steve-xmh)

```text
61ba6770-f02f-11ef-a3ae-5396943709e6|AMLL%20TTML%20Database%20(Steve-xmh%20Mirror)||ttml|[https://amll-ttml-db.stevexmh.net/ncm/](https://amll-ttml-db.stevexmh.net/ncm/)[NCM_ID]

```

### Community Mirrors

You may also try community-provided mirrors (refer to internal docs for usage). Thanks to [@HelloZGY](https://github.com/cybaka520) and [@Luorix](https://github.com/LuorixDev)!

**AMLL TTML DB Mirror Site** by [@HelloZGY](https://github.com/cybaka520)

```text
19cf30a0-6206-11f0-b2b3-0d580aff0f69|Mirror%20Site||ttml|[https://amlldb.bikonoo.com/ncm-lyrics/](https://amlldb.bikonoo.com/ncm-lyrics/)[NCM_ID].ttml

```

**AMLL-TTML-DB Auto-Mirror** by [@Luorix](https://github.com/LuorixDev)

```text
06e48500-d086-11f0-bb6e-451fd0fc9216|Dimeta%20Mirror%20v1||ttml|[https://amll.mirror.dimeta.top/api/db/ncm-lyrics/](https://amll.mirror.dimeta.top/api/db/ncm-lyrics/)[NCM_ID].ttml

```

## UniLyric [Broadest Compatibility]

UniLyric is a versatile lyric converter and a lyric sender for AMLL Player. It works by listening to [SMTC](https://learn.microsoft.com/en-us/windows/uwp/audio-video-camera/integrate-with-systemmediatransportcontrols) (System Media Transport Controls) to retrieve song info and progress. Therefore, it works with any player that supports SMTC. It integrates AMLL TTML DB search and is currently the most effective tool for searching lyrics and sending them to AMLL Player. [Learn More](https://github.com/apoint123/Unilyric)

## Integration for Developers

> [!TIP]
> While not mandatory, we hope that when using this database, you include a link or description pointing to this repository (or derivative projects) in your project, or display the lyric author information found in the metadata. This helps more people discover and contribute to the database.

To integrate this database, use the corresponding platform folder and the music ID to retrieve files.

**Supported Platforms:**

* [Netease Cloud Music](https://www.google.com/search?q=./ncm-lyrics) - [`ncm-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/ncm-lyrics)
* [QQ Music](https://www.google.com/search?q=./qq-lyrics) - [`qq-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/qq-lyrics)
* [Apple Music](https://www.google.com/search?q=./am-lyrics) - [`am-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/am-lyrics)
* [Spotify](https://www.google.com/search?q=./spotify-lyrics) - [`spotify-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/spotify-lyrics)

**File Formats (distinguished by extension):**

* `.ttml` - Original TTML format
* `.lrc` - Standard LRC format
* `.yrc` - NCM Word-level format
* `.qrc` - QQ Music Word-level format
* `.lys` - Lyricify Syllable format
* `.eslrc` - ESLrc Word-level format

**Direct Link Pattern:**

> `https://raw.githubusercontent.com/amll-dev/amll-ttml-db/refs/heads/main/[Platform_Folder]/[Music_ID].[Extension]`

**Raw Data:**
For all historical files, visit the [raw-lyrics/](https://www.google.com/search?q=./raw-lyrics/) folder. Files are named: `[Unix_Timestamp]-[Submitter_GitHub_ID]-[8_Char_Random_ID].ttml`.
Alternatively, check [metadata/raw-lyrics-index.jsonl](https://github.com/amll-dev/amll-ttml-db/raw/refs/heads/main/metadata/raw-lyrics-index.jsonl) for a complete chronological index.

---

# License

External data follows the original provider's license. Portions created by contributors are licensed under **[CC0 1.0 Universal](https://github.com/amll-dev/amll-ttml-db?tab=CC0-1.0-1-ov-file)**.

---

# Acknowledgments

We welcome you to join the AMLL Family QQ Group: `719423243`.

Thanks to all contributors who have helped build this repository!

```

```
