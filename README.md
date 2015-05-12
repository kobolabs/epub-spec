# Kobo ePub Guidelines
What’s in this Document:
 
* Elements of the ePub spec that Kobo does and does not support.
* Features of the five Kobo reading platforms.
* Recommendations on file production and testing for content creators. 
 

### Table of Contents

1. [ePub Versions Kobo Supports](#epub-versions-kobo-supports)
2. [Kobo Reading Platforms](#kobo-serves-content-to-users-on-these-5-reading-platforms)
3. [Kobo Devices](#current-kobo-devices)
5. [Kobo Recommends Initial ePub Check](#kobo-recommends-initial-epub-check)
6. [Sideloading for Testing Purposes](#sideloading-for-testing-purposes)
7. [Digital Rights Management (DRM)](#digital-rights-management-drm)
8. [Placing Images Properly](#placing-images-properly)
9. [Cover Images](#cover-images)
10. [Scalable Vector Graphics (SVG)](#scalable-vector-graphics-svg)
11. [Table of Contents (ToC)](#table-of-contents-toc)
12. [OPF](#opf)
13. [CSS](#css)
14. [Supported Fonts](#supported-fonts)
15. [Obfuscated Fonts](#obfuscated-fonts-are-not-currently-supported-by-the-kobo-cms)
16. [Embedded Fonts](#embedded-fonts-can-be-selected-by-users)
17. [Languages](#languages-other-than-english)
18. [Footnotes/Endnotes](#footnotesendnotes-are-fully-supported-across-kobo-platforms)
19. [Fixed Layout](#fixed-layout-fxl-support)
20. [SMIL](#kobo-supports-smil)
21. [Image-Based FXL Reader](#image-based-fxl-reader)
22. [Multimedia Support / Media Overlays](#multimedia-support--media-overlays)
23. [JavaScript Support](#javascript-support)
24. [MathML](#mathml-is-supported-on-ios-elnk-and-desktop-platforms)
25. [Fallback Statements/Switches](#fallback-statementsswitches)
26. [ePub Previews](#epub-previews)
27. [Tables](#tables)
28. [Limitations and Maximums](#limitations-and-maximums)
29. [Support Grid] (#support-grid)
30. [Questions?](#still-have-questions)

### ePub Versions Kobo Supports
 
Kobo supports ePub, the universal open standard eBook format maintained by the Independent Digital Publishing Forum [(IDPF)](http://idpf.org/epub). The current version is ePub 3 but Kobo still supports its predecessor, ePub 2.0.1.

Any ePub file sent to Kobo will be made available on all of Kobo's reading platforms with the exception of ePub2 Fixed Layout content which is not available on Desktop or eInk:

| Platform  | ePub2 Reflowable | ePub2 FXL | ePub3 Reflowable | ePub3 FXL |
|-----------|------------------|-----------|------------------|-----------|
| Android   | Y                | Y         | Y                | Y         |
| Desktop   | Y                | N         | Y                | Y         |
| eInk      | Y                | N         | Y                | Y         |
| iOS       | Y                | Y         | Y                | Y         |
| Windows 8 | Y                | Y         | Y                | Y         |
 
The ePub 3.0 spec is based on HTML5 and CSS3, adhering to the most recent versions. Content creators are advised to review the [HTML5 and CSS3 reference profiles](http://www.idpf.org/epub/30/spec/epub30-contentdocs.html#references) because changes to them could impact file production. 
 
Kobo supports a subset of elements from the ePub 3.0 spec. The following covers which elements are supported across Kobo’s reading platforms.

### Kobo Serves Content to Users On These 5 Reading Platforms 
 
1. eInk/EPD — Kobo eInk devices (Aura, Glo, Touch) 
2. Desktop — the Kobo desktop app for PC and Apple Computers
3. Android — all Android devices running the Kobo app including all Kobo Arc versions
4. iOS — iPad, iPhone and iPod Touch
5. Windows 8 — all tablets, smartphones and computers running Windows 8.

### Current Kobo Devices
 
Android: 
* Arc 7 SD
* Arc 7 HD
* Arc 10 HD

eInk:
* Glo HD
* Aura H2O
* Aura
* Aura HD


### Earlier Kobo Devices
 
Android:
* Arc (original)
* Vox

eInk:
* Glo
* Kobo Mini
* Touch
* Kobo WiFi
* Kobo1
 
### Kobo Recommends Initial ePub Check 
 
The Kobo CMS does not use a built in ePubCheck. To detect errors in ePubs, the IDPF provides both a [web validation tool](http://validator.idpf.org/) and a [desktop application](https://github.com/IDPF/epubcheck). Kobo cannot guarantee that files that fail ePubCheck will render correctly across its reading platforms. So ePubs should be validated using the most recent version of ePubCheck prior to distribution. 
 
The Kobo Content Management System will neither reject those files that fail ePubCheck nor send reports to their publishers. However, if any rendering or performance issues harm the user experience, the files may be flagged for, and then failed in, the Kobo content QA process. 

Kobo recommends content creators remove any files not listed in the OPF document, as suggested by the validator. Leaving these files in the ePub can cause unexpected behaviour that may result in failing QA test results.

### Sideloading for Testing Purposes
 
Kobo encourages the testing of content on all its reading platforms by sideloading. Content should display identically whether sideloaded or downloaded to a device from the Kobo store. Instances where this is not the case can be reported to renderingissues@kobo.com and the epub in question will be logged for investigation. The only present exception applies to ePubs containing obfuscated fonts which will display correctly when sideloaded but will not pass content QA once processed - see [Font Obfuscation] (https://github.com/kobolabs/epub-spec/blob/master/README.md#obfuscated-fonts-are-not-currently-supported-by-the-kobo-cms).

Here’s how to sideload content on Kobo's reading platforms:
 
**eInk**

1. Connect the device to your computer via USB.
2. Find the drive on your computer in Finder or Windows Explorer.
3. Drag your ePub onto the device. To trigger the Kobo WebKit, change the file extension to “.kepub.epub”. To trigger the Kobo Webkit for a Fixed Layout title, change the extension to “.fxl.kepub.epub”. (If the extension is left unchanged it will render using the Adobe Digital Editions Webkit.)
4. Disconnect your device. The file will automatically appear in your library.
 
**Desktop**

1. Open the Kobo Desktop app.
2. Make sure you have [Adobe Digital Editions](http://www.adobe.com/ca/products/digital-editions/download.html) installed. 
3. Select the Library tab in Kobo Desktop and press CTRL+Shift+S on Windows or ⌘+SHIFT+S on a Mac. This will display any files in the “My Digital Editions” folder on your computer with the extension .kepub.epub or .fxl.kepub.epub
 
**Android**

1. Connect the device to your computer via USB.
2. Find the drive on your computer in Windows Explorer. If you use a Mac, install and connect to the device using [Android File Transfer](http://www.android.com/filetransfer/).
3. Drag your ePub onto the device.
4. On the device, navigate to the Kobo App or, if you use a Kobo Arc, the Books Collection. Select options (the three dots on the top right) then “Import”.
5. Once the files appear, confirm that you want to import them. They will display in your library.
 
**iOS**

1. Connect the device to your computer with the iOS cable.
2. Open iTunes and navigate to iPad -> Apps.
3. Select the Kobo app from the box on the left.
4. Drag the ePub to the box in the bottom right of your iTunes window. The file will then automatically import and display in your library.

(The Kobo iOS app is registered among apps that open ePub and pdf files. Users can use the standard “open in…” menu from Safari, Dropbox, or any other app that supports it to view their files.)
 
**Windows 8**

1. Open the Kobo app, navigate to the Library and swipe up from the bottom of the screen.
2. Select “import”.
3. Select the files on the device that you want to import. (The Kobo app will scan all the files on your device that it can import. You may not be able to transfer files via USB depending on the specific Windows 8 device and may need to transfer them by OneDrive, Dropbox, email or some other method instead.)
4. Select “Open” and wait for the files to load into your library.

(Sideloading is not yet supported on the Kobo app for Windows 8 phones.)

### Digital Rights Management (DRM)
 
ePubs loaded to the Kobo store are protected by Kobo DRM. Kobo can turn the DRM off at the publisher-level, when publishers make a request to the Publisher Operations team.
 
Kobo’s DRM system hosts content on its reading platforms using advanced security methods, including the use of encryption and hash algorithms. Various keys are used to encrypt content before it is sent to the reading platform. There are unique keys for each eBook, user and device. 
 
At a minimum, Kobo employs encryption standards in the 128-bit version of the Advanced Encryption Standard (AES) of the US Government.
 
### Placing Images Properly
 
Kobo reading platforms support the core image types outlined in the [IDPF spec](http://www.idpf.org/epub/30/spec/epub30-publications.html#cmt-grp-image). This includes JPG, PNG and GIF but not Scalable Vector Graphics (SVG), which are not supported on all reading platforms. (See the Support Grid.) PNG files are preferred over JPG.
 
All images should use the RGB color model, and not CMYK. Encapsulated PostScript (EPS) images are not supported on Kobo.
 
**The advised maximum size for all image types is 3 MB.** ePubs with larger images are still accepted and those images will not cause Kobo apps and devices to crash. However, ePubs with images all under this limit perform optimally across platforms.

**Image dimensions should be set in percentages instead of pixels in the CSS for reflowable content.** Images with dimensions set by pixels may stretch depending on the orientation, device and user settings. Kobo reading platforms insert max-width and max-height CSS for images and videos to ensures that they are not split over multiple screens.
 
**For a full screen image view** on the Android and iOS platforms, users can long press images in reflowable ePubs. Once in full-screen view, users will be able to pinch and zoom. This can also be acheived on eInk devices (running version 3.14 or later) by double tapping images.

### Cover Images
 
If an external cover image is uploaded to both the Kobo system and the ePub, that external image displays as the thumbnail image in the store and in user’s libraries. The internal ePub cover still displays when the user opens the file on their device.
 
GIF files are not supported for covers.
 
The suggested optimal ratio for covers on Kobo is 3:4 width:height. (The average size and dimensions for ebook covers in the Kobo store are 800:1224px width:height.) However covers in all dimensions will be rendered consistently across platforms. Content creators are advised to keep their cover images under 3MB. Larger covers will still render but will not improve the display of their content.
 
### Scalable Vector Graphics (SVG)
 
SVG is partially supported across Kobo platforms. Thorough testing is advised for ePubs with SVG, particularly for text rendering. Content creators are advised to use the [ePub switch element](http://www.idpf.org/epub/30/spec/epub30-contentdocs.html#elemdef-switch) to provide fallback content. Refer to the support grid in this document or the test results for Kobo's reading platforms at [ePubtest.org] (http://www.epubtest.org).
 
### Table of Contents (ToC)
 
**For ePub 2.0.1**, Kobo reading platforms populate the ToC menu in the book with the ToC from the file toc.ncx (which is in navMap). However, if the toc.ncx is not present, the TOC menu is populated by the Spine listing in the OPF.
 
When an OPF-spine item is not listed in the TOC.ncx, the Kobo CMS will create a listing for it using the filename or the opening words from the section. This listing will be displayed to the user in the TOC Menu across all reading platforms. This process may be removed in a future release. ePubs that use a nav.html TOC will not be impacted. 
 
**For ePub 3.0**, Kobo platforms will read the ToC from the ToC table in the nav.html file. When a ToC table is not present, the next available table will be used. If the nav.html is not present, it will populate the ToC with the toc.ncx. If the toc.ncx is not present, it will populate the ToC with the spine listing in the OPF.
 
The hidden attribute can be used to prevent the ToC listing from appearing in the ePub body while still displaying in the ToC menu. ToC menus on Kobo platforms support nesting up to three elements deep.

Kobo does not require a specific naming convention for the .ncx or .html/.xhtml file, the content creator can name the file as they choose ([filename].ncx, [filename].html). Please note the file naming suggestions provided in the [OPF] (#OPF) section. 

### OPF
 
The Kobo CMS reads the external metadata provided by the publisher. So most fields in the metadata section of the OPF file are not read. The one exception is the <dc:identifier>. It should contain the eBook ISBN, also supplied in the external metadata. However, if this field does not contain the eBook ISBN, it must be in the ePub file name. Content creators are also advised that the <dc:identifier> in the OPF should be identical to the identifier in the .ncx file.
 
Kobo uses external metadata files to populate the various metadata fields on the Kobo website. The ISBN in the <dc: identifier> field in the OPF file matches the ePub to the external metadata entry. If there is no ISBN in the <dc: identifier> tab, Kobo looks for the ISBN in the ePub filename. The ISBN from the external metadata must match either the <dc: identifier> field or the ePub file name.
 
The OPF file can be named however the content creator chooses ([filename].opf), but please note the file naming conventions suggested below. 
 
**Content creators are advised to use [tags for manifest items](http://www.idpf.org/epub/30/spec/epub30-publications.html#sec-item-property-values)**, specifically the cover tag. Some of these are read across Kobo’s reading platforms and future developments will be able to take advantage of properly tagged items.
 
**Special characters and spaces should not be used** for file names within an ePub. This can result in naming inconsistencies with the items listed in the OPF manifest. File names containing non-alphanumeric characters are not fully supported, and their use may lead to undefined behaviour, which may be inconsistent across clients.

### CSS

**Background Colors**

Kobo recommends that publishers avoid specifying white as a background colour in the CSS for their ePubs. This can cause text to become unreadable in Night Mode on the Kobo Android app as the text and the background will both display as white. This recommendation only applies to reflowable content as Night Mode cannot be turned on while reading Fixed Layout content.

`.c5 {
  background: #fff
  }`

**Small Caps**

In order to structure Small Caps that will display correctly on Kobo's reading platforms content creators must use the CSS property "font-variant".

Ex.
`p.sc {
   font-variant: small-caps;
}`

The property "font-size" is often used incorrectly to format Small Caps and can result in disproportionate text sizing depending on the app/device being used and the font settings chosen by the user. The impact is particularly noticeable when the value used for this property is set to "x-small" or "small". Content creators are also advised to use a font that contains Small Caps glyphs for optimal rendering.

**Inline Styling**

Kobo strongly advises against the use of inline styling for all content types (reflowable and Fixed Layout). Inline style elements may not be rendered as intended across Kobo's reading platforms. Styling elements should be contained within CSS.

For example, text should be formatted as follows: 

HTML:<br>
`<p class="text">Sample text.</p>`<br>
`<p class="text">Sample text, part two.</p>`<br>
CSS:<br>
`p.text {
    margin: 0;
    text-size: 10px;
}`

Not like this:

HTML:<br>
`<p style="margin: 0;text-size: 10px;">Sample text.</p>`<br>
`<p style="margin: 0;text-size: 10px;">Sample text, part two.</p>`<br>

### Supported Fonts
 
TTF, OTF, and WOFF fonts are supported by all of our platforms with the exception of Windows 8. For a detailed breakdown of our font support by platform, check [EPUBTEST.org](http://epubtest.org/results). 

**Font customization options available to Kobo users** on each reading platform:
 
**Android:** Droid Sans Serif, Droid Serif.
 
**Desktop:** A-OTF Gothic MB101 Pr6N R, A-OTF Ryumin PR6N R-KL, Arial, Ariel Narrow, Arial Unicode MS, Calibri, Calibri Light, Cambria, Cambria Math, Constantia, DFKai-SB, Georgia, KaiTi, Lucida Sans, Palatino Linotype, Meiryo, Meiryo UI, MS Gothic, MS Mincho, MS PGothic, MS PMincho, SimHei, Times New Roman, Tahoma, Trebuchet MS.
 
**eInk:** Amasis, Avenir Next, Caecilia, Georgia, Gill Sans, Kobo Nickel, Malabar, Gothic, Ryumin, [Dyslexie](http://www.dyslexiefont.com), [OpenDyslexic](http://opendyslexic.org/) (the last two are optimized for readers with dyslexia).
 
**iOS:** Avenir, Baskerville, Cochin, Georgia, Helvetica, Optima, Palatino, Trebuchet, Verdana.
 
**Windows 8:** Cambria, Calibri, Georgia, SegoeUI, Times New Roman, Trebuchet MS, Verdana.

### Obfuscated Fonts Are Not Currently Supported by the Kobo CMS
Non-sideloaded titles with obfuscated fonts will display the reading platform’s default font instead of the intended font. As a result all Fixed Layout titles with obfuscated fonts are likely to fail QA. However, work is underway at Kobo to support obfuscated fonts and render these titles correctly.
DRM is applied to all ePubs sold through Kobo unless the account/publisher sending the content elects to have Kobo distribute their ePubs without DRM. As a result Kobo users will not be able to extract fonts from ePubs with DRM even when the embedded fonts are not obfuscated.

### Embedded Fonts Can Be Selected By Users 
When opening a new book, the font that displays is the one chosen by the user for their previous open book. For an embedded font, users can select “Document Default” or “Publisher Default” from the font options. The exception is FXL content for which users cannot choose their font. Fonts in FXL content are determined by the CSS in the ePub.

If the reading experience of a book requires that the embedded font be used, consider adding a note to the front matter. Instruct the user to select the “Document Default” font option. 

**To avoid text-positioning errors**, seriously consider embedding and specifying fonts in the CSS for all Fixed Layout ePubs. If fonts are not embedded and specified, the reading platform defaults to Times. Fixed Layout files that use the default font should be tested extensively on Kobo’s reading platforms.

**Content creators are advised against referencing fonts in the CSS that are not embedded in the ePub.** Kobo devices and devices that Kobo apps can be installed on will have specific fonts included. However the available fonts vary across these devices and there is no way to ensure that any one font will be available on the device chosen by the user. As a result the font styling in the CSS will not display as intended across multiple devices and platforms.

### Languages Other Than English
 
When a user selects an available default font, Kobo reading platforms may not correctly render all glyphs within the script. So Content containing glyphs not present in Kobo’s default apps should be tested across platforms. Creators may want to embed a font that contains the glyphs used in their content to ensure it renders correctly.
 
Some glyphs do not render on most fonts. In cases where creators are unable to supply embedded fonts they can insert a note into the front matter of their content instructing users to select the font Georgia. It correctly renders the greatest set of scripts.
 
Kobo is currently working to add built-in fonts to the eInk and Android-reading platforms and render glyphs from all scripts correctly. The Desktop, iOS and Windows 8 platforms already contain built-in fonts that will render glyphs from all scripts.

Kobo has support for right-to-left language formatting in the following areas:
* Kobo supports the OPF spine-level [page-progression-direction](http://www.idpf.org/epub/30/spec/epub30-publications.html#attrdef-spine-page-progression-direction) attribute for right-to-left page flow
* Kobo supports the writing-mode CSS3 property and associated elements for vertical text layouts (LTR or RTL)
* Kobo supports the HTML5 dir attribute
* Kobo supports ruby text*

*_This support excludes the Windows 8 platform._

### Footnotes/Endnotes Are Fully Supported Across Kobo Platforms
 
Footnotes and endnotes on the eInk (with the exception of the original Kobo reader and the Kobo Wi-Fi) and iOS platforms will will display as a pop-up box containing the content being linked to. The pop-up boxes also contain links to the HTML sections containing the reference material. On iOS the footnote pop-up will render more than just plain text, including images, links and other content in the footnote or endnote. On the Desktop, Android and Windows 8 platforms users will not see a pop-up but can simply follow the link to HTML section with the reference text.
 
It is strongly recommended that reference notes use the appropriate [ePub:type identifying attribute](http://www.idpf.org/epub/30/spec/epub30-contentdocs.html#sec-xhtml-content-type-attribute) for footnotes and endnotes. This attribute is currently supported on Kobo's iOS platform and its use is the best way to ensure that footnotes and endnotes will display as intended on iOS as well as future releases on other platforms. Both the iOS and eInk platforms have additional means of detecting content that is linked as a footnote or endnote for the purpose of creating pop-ups but the best way of ensuring that those pop-ups display as intended is to use the "noteref" attribute.

### Fixed Layout (FXL) Support
 
Kobo supports the [official ePub3 FXL spec](http://www.idpf.org/epub/fxl/). This includes such features as [Right-to-Left Reading](http://www.idpf.org/epub/30/spec/epub30-publications.html#attrdef-spine-page-progression-direction), SMIL/Read Along, and various rendition-spread options. The [rendition:layout property](http://www.idpf.org/epub/fxl/#property-layout) in the OPF determines the layout of the content and is read by all of Kobo’s platforms.
 
Kobo platforms also read the field <option name=”fixed-layout”>true/false</option> to identify whether ePubs should be rendered as FXL. The file containing this field is usually titled com.kobobooks.display-options.xml and can be found in the META-INF directory of the ePub. This file is not required for ePub3 FXL content. 

All five values in the [rendition:spread property](http://www.idpf.org/epub/fxl/#property-spread) are on the Android, Desktop and eInk reading platforms. The iOS platform supports the properties "Both", "None" and "Auto" but not "Portrait" or "Landscape". The Windows 8 platform supports the properties "None" and "Auto" but not "Both", "Portrait" or "Landscape". Rendition-spread properties are only read at the book level for all reading platforms. Future versions of Kobo’s reading platforms may read the rendition:spread and rendition:layout properties at the spine level.
 
**Pinch and zoom gestures** are present on the Android, iOS, and Windows 8 reading platforms. Zooming is possible on eInk devices by accessing the reading menu and zooming. Zooming is not supported on the Kobo Desktop app.
 
FXL content on Android always displays one page in portrait view.

**Kobo strongly advises against the use of inline styling for FXL content**. Text boxes with inline styling may render inconsistently across platforms, resulting in text overlapping or incorrect positioning.
 
**Kobo also advises against using images where the width or height (in pixels) exceed the dimensions of the viewport**. ePubs containing images that exceed the viewport dimensions may not render correctly on the eInk platform.

**Kobo Advises Against Overuse of Fixed Layout**

Content creators are advised against producing Fixed Layout ePubs solely for the purpose of reproducing a print layout. Text cannot be resized by users while reading Fixed Layout content and as a result small text can only be read by zooming in. This can greatly diminish the reading experience particularly on eInk devices, smartphones and Desktop applications. Fixed Layout serves comics, children's books and other categories well but is not an ideal format for text heavy content that could be displayed as reflowable content. Furthermore Fixed Layout ePubs require more in depth testing prior to distribution to ensure that they display correctly across multiple reading platforms.

### Kobo Supports SMIL
 
[SMIL (Synchronized Multimedia Integration Language)](http://www.idpf.org/epub/30/spec/epub30-mediaoverlays.html#sec-smil-smil-elem) is supported for FXL titles on Android and iOS. Audio files must be encoded using Apple iTunes AAC-LC mp4-v2 codec, 256 kbps.
 
Note: the Kobo Android platform **does not currently support**:

* Non-Linear playback
* Text highlighting for SVG text
 
When the rendition:spread property is set to “none” or “auto”, Android displays a full spread in FXL Read Along content in landscape.
 
Custom text colors for highlighting are not currently supported on Android. However, custom text colors for highlighting is possible on iOS. The iOS app uses the CSS class ‘kobo-smil-highlight’ to color highlighted text. So, by adding that class to the CSS plus a color declaration, the color of the highlighted text on the app can be customized.

### Image-Based FXL Reader
 
The Kobo Android and iOS platforms will render FXL ePubs that meet certain criteria with an image-based Fixed Layout reader. This reader features significantly faster panning, zooming, and page-turns than the standard one. Designed to enhance the reading experience of comics, it works for any FXL ePubs composed entirely of images.
 
**ePubs that meet the following criteria will be displayed with the image-based reader on Kobo’s iOS and Android platforms**:

1. The content is Fixed Layout.
2. The ePub does not contain SMIL content.
3. An image must be available for each spine item. Spine items are inspected for images using these rules — and each spine item must contain one of the following formats:
<ul>
<li>a. either a non-SVG image (e.g. PNG)</li>
<li>b. or an SVG image with a non-SVG image fallback provided in the manifest. In this case, the fallback image is used in the comics renderer</li>
<li>c. or an HTML file which falls under one of the following categories:
<ul>
<li>i. either it contains a single ‘img’ tag which references an image. In this case, this image will be used</li>
<li>ii. or it contains a svg definition with an ‘image’ child tag referencing an image. In this case, the referenced image will be used. NB: embedded object tags (‘object’), which may include an SVG image in the ‘data’ attribute, do not fall into this category</li>
<li>iii. or an HTML page which contains no child elements under ‘body’. This item will be rendered as a blank white page.</li></ul></li></ul>
4. The same image cannot appear twice in a row. If two consecutive pages refer to the same image, the platform will assume that CSS styling is repositioning the image, which is not supported by the image-based FXL reader.
 
For example, a file that lists spine items, manifest items, and contains nothing but an image in the HTML body will trigger the image-based renderer.
 
First spine item:<br>
`<spine page-progression-direction="ltr" toc="ncx">`<br>
`<itemref idref="page0-xhtml" linear="yes"/>`

Matching item in manifest:<br>
`<item id="page0-xhtml" href="contents/Page00.xhtml" media-type="application/xhtml+xml"/>`
 
HTML body for item:<br>
`<body>`<br>
`<div id="layer0">`<br>
`<image width="1076" height="1394" xlink:href="../images/Image01-1-0.jpg"/>`<br>
`</div>`<br>
`</body>`
 
If images are set using the [background property](http://www.w3.org/TR/CSS21/colors.html#propdef-background) of elements the platform will fall back to using the default reader.
 
On Android, if the image is determined to be twice as large as the screen in any dimension, a low-res version of the image loads when the user turns a page. Within a second, the high-res version replaces the original image. This optimization prevents memory issues when users quickly flip through pages. The low-res image might appear slightly blurry or soft compared to the final hi-res image.

### Multimedia Support / Media Overlays 
 
Testing across platforms for ePubs with multimedia and other media overlays is recommended.
 
Embedded audio and video is currently supported on Kobo’s iOS and Android platforms for all content. 
 
Windows 8 does not currently support embedded audio and video. Kobo eInk devices and the desktop app do not support embedded audio and video either but will display any content included as a fallback using the [switch element](http://www.idpf.org/epub/30/spec/epub30-contentdocs.html#elemdef-switch) display instead.

**Autoplay Functionality is not currently supported**

Kobo's platforms do not currently support autoplay functionality for embedded media. Elements using this tag will display but will not begin playback without user interaction.

Ex. <br>
`<audio class="myaudio" src="sounds/audio.mp3" autoplay="autoplay">Sample text.</audio>`
 
### JavaScript Support
 
Kobo’s Android and iOS platforms support JavaScript for Fixed Layout and reflowable ePubs, but it is recommended not to use JavaScript in reflowable content in ways that may alter the layout of the book. Kobo’s eInk and Desktop platforms have limited support for JavaScript, and do not support interactive JavaScript elements. ePubs with JavaScript should contain fallback statements. This way, platforms that do not support JavaScript can still produce a coherent reading experience. Thorough testing on all platforms is strongly recommended to ensure that fallback as well as JavaScript content renders correctly.

**Disabling Menu Activation for Interactive Elements**

Taps in book content (on elements other than links) are passed up to the Kobo reading apps in order to trigger menus and other reading system interactions. To avoid having your interactive elements trigger unrelated reading system functionality JavaScript files must contain event listeners for both _click_ and _touchend_ (or _touchstart_) events, and both listener functions must call [preventDefault()](http://www.w3schools.com/jquery/event_preventdefault.asp) on both _click_ and _touchend_ (or _touchstart_, if you’d prefer) events. Any interactive logic will need to be implemented in the touch handler, rather than the click handler, as in the example below:
<pre><code>exampleElement.addEventListener('click', handleClick, false);
exampleElement.addEventListener('touchend', handleTouch, false);

function handleClick(event) {
	event.preventDefault();
}

function handleTouch(event) {
	exampleElement.style.background="red";
	event.preventDefault();
}
</code></pre>
 
### MathML is Supported on iOS, elnk, and Desktop platforms
 
Please note that [MathML](http://www.idpf.org/epub/30/spec/epub30-contentdocs.html#sec-xhtml-mathml) is not presently supported on the Kobo Android or Windows 8 platforms. At present content creators are encouraged to either include a note to indicate that the content is not optimized for Android and Windows 8 devices, or else use images (rather than MathML) for the mathematical content.

### Fallback Statements/Switches 
 
The Desktop, eInk and iOS platforms support ePub switch statements. In addition the Desktop and eInk platforms support fallback statements in the manifest. Further details on fallback content and statements can be found in the [IDPF spec](http://www.idpf.org/epub/30/spec/epub30-publications.html#sec-fallback-processing-flow). As some devices and apps do not yet or cannot support audio/video, JavaScript, MathML, or other “enhanced” elements it is recommended that ePubs with these elements use fallback statements to ensure that they are accessible to readers. ePubs that make proper use of switches and fallback statements will be able to take advantage of future development for fallback statements on the Android and Windows 8 platforms.
 
For example:
 
<pre><code>&lt;!--&lt;epub:switch id=&quot;c01-mdis-0001&quot;&gt;
 &lt;epub:case required-namespace=&quot;http://www.w3.org/1998/Math/MathML&quot;&gt;
   &lt;span class=&quot;equation&quot;&gt;
     &lt;span class=&quot;equation-line&quot;&gt;
       &lt;span class=&quot;equation-label&quot; style=&quot;margin-top:0.02384993em&quot;&gt;(1.1)&lt;/span&gt;
       &lt;span class=&quot;equation-content&quot;&gt;
         &lt;math display='block' xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;&gt;
&lt;mrow&gt;&lt;msub&gt;&lt;mi&gt;V&lt;/mi&gt;&lt;mn&gt;1&lt;/mn&gt;&lt;/msub&gt;&lt;mo&gt;+&lt;/mo&gt;&lt;msub&gt;&lt;mi&gt;Z&lt;/mi&gt;&lt;mi&gt;s&lt;/mi&gt;&lt;/msub&gt;&lt;msub&gt;&lt;mi&gt;I&lt;/mi&gt;&lt;mn&gt;1&lt;/mn&gt;&lt;/msub&gt;&lt;mo&gt;=&lt;/mo&gt;&lt;msub&gt;&lt;mi&gt;V&lt;/mi&gt;&lt;mi&gt;s&lt;/mi&gt;&lt;/msub&gt;&lt;/mrow&gt;&lt;/math&gt;&lt;/span&gt;&lt;/span&gt;&lt;/span&gt;
    &lt;/epub:case&gt;
     &lt;epub:default&gt;--&gt;
   &lt;p class=&quot;para_center&quot;&gt;
     &lt;img id=&quot;c01-mdis-0001&quot; src=&quot;images/m001.gif&quot; alt=&quot;&quot;/&gt;
   &lt;/p&gt;
   &lt;!--&lt;/epub:default&gt;
&lt;/epub:switch&gt;--&gt;
</code></pre>
 
In the above, the parts of the switch which legacy viewers would not be able to handle have been called out. So platforms that do not support MathML display the fallback content instead. 

### ePub Previews 
 
Publishers can set the amount of content they make available in previews. They use their metadata feed or work with Kobo’s Publisher Operations team to customize their account settings.
 
**On the account level**, previews are set to display 5% of the ePub’s content by default. Previews can be turned on or off. The maximum percentage that accounts can be set to is 25%.
 
**On the product level**, the default is 5%. Publishers can set preview percentages for individual titles. They can use the Kobo Excel metadata template or ONIX 3.0 with the tags EpubUsageType, EpubUsageStatus or EpubUsageLimit. Previews can be set between 0% and 25%.
 
Publishers can also upload custom previews by using the naming convention ISBN_preview.epub in the preview files they distribute.
 
### Tables 
 
Sometimes tables wider than four columns may not be readable in reflowable ePub files, particularly on eInk devices. Content producers adding tables with more than four columns are advised to test their content on all Kobo reading platforms. Likewise, when HTML tables do not render as intended, they can reformat or capture the tables as high-resolution images.
 
### Limitations and Maximums 
 
Kobo recommends the following limits for ePub file and component size. Files exceeding these sizes will not necessarily fail to load to the Kobo store. Moreover, large files that successfully load to the store will not degrade app performance. Larger files will simply take longer to download to users’ devices and use more memory.
 
* 3 MB/image in FXL and Reflowable ePubs
* 3 800 000 pixels/viewport or ~1950x1950 in FXL ePubs 
* 1 GB/ePub
 
### Support Grid

The following table lists features supported by at least one Kobo platform but not uniformly supported across all platforms. Features not listed here are either supported across all platforms or not supported on any platforms.

| Platform  | MathML | SMIL | JavaScript | CSS Animations | Audio/Video |
|-----------|--------|------|------------|----------------|-------------|
| Android   | N      | Y    | Y          | Y              | Y           |
| Desktop   | Y      | N    | N          | Y              | N           |
| eInk      | Y      | N    | N          | Y              | N           |
| iOS       | Y      | Y    | Y          | Y              | Y           |
| Windows 8 | N      | N    | N          | N              | N           |

### Still have questions? 
 
Learn more about Kobo’s ePub support at [epubtest.org](http://epubtest.org/). It’s categorized into required and optional features. 

If you encounter any rendering issues you can bring them to our attention at renderingissues@kobo.com. Please provide as much detail as possible, including app version, device, and screenshots if possible. Any comments or concerns about the documentation above can be submitted directly via Github comments. Immediate responses to all emails and comments cannot be guaranteed but all feedback related to documentation and content rendering is appreciated.

If you are already configured as a publisher or distributor with Kobo and have a questions concerning content management (metadata or ePub uploads, pricing, pre-orders, etc.) you can follow up with your contact on the Publisher Operations team.

If you are a small publisher or a self-published author and would like to sell your content through Kobo you can do so through [Kobo Writing Life](http://www.kobo.com/writinglife).



