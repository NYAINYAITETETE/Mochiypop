## Fontbakery report

Fontbakery version: 0.7.31

<details>
<summary><b>[1] Family checks</b></summary>
<details>
<summary>⚠ <b>WARN:</b> Is the command `ftxvalidator` (Apple Font Tool Suite) available?</summary>

* [com.google.fonts/check/ftxvalidator_is_available](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/ftxvalidator_is_available)
<pre>--- Rationale ---

There&#x27;s no reasonable (and legal) way to run the command `ftxvalidator` of the
Apple Font Tool Suite on a non-macOS machine. I.e. on GNU+Linux or Windows etc.

If Font Bakery is not running on an OSX machine, the machine running Font
Bakery could access `ftxvalidator` on OSX, e.g. via ssh or a remote procedure
call (rpc).

There&#x27;s an ssh example implementation at:
https://github.com/googlefonts/fontbakery/blob/master/prebuilt/workarounds
/ftxvalidator/ssh-implementation/ftxvalidator


</pre>

* ⚠ **WARN** Could not find ftxvalidator.

</details>
<br>
</details>
<details>
<summary><b>[6] MochiyPopOne-Regular.ttf</b></summary>
<details>
<summary>🔥 <b>FAIL:</b> Checking OS/2 Metrics match hhea Metrics.</summary>

* [com.google.fonts/check/os2_metrics_match_hhea](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/os2_metrics_match_hhea)
<pre>--- Rationale ---

When OS/2 and hhea vertical metrics match, the same linespacing results on
macOS, GNU+Linux and Windows. Unfortunately as of 2018, Google Fonts has
released many fonts with vertical metrics that don&#x27;t match in this way. When we
fix this issue in these existing families, we will create a visible change in
line/paragraph layout for either Windows or macOS users, which will upset some
of them.

But we have a duty to fix broken stuff, and inconsistent paragraph layout is
unacceptably broken when it is possible to avoid it.

If users complain and prefer the old broken version, they have the freedom to
take care of their own situation.


</pre>

* 🔥 **FAIL** OS/2 sTypoAscender (880) and hhea ascent (1160) must be equal. [code: ascender]

</details>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---

Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is
stored in the achVendID field of the OS/2 table.

Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:

https://docs.microsoft.com/en-us/typography/vendors/

This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.

Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.


</pre>

* ⚠ **WARN** OS/2 VendorID value 'FTDS' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---

Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will
only differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.

However, a quotedbl should have 2 contours, unless the font belongs to a
display family.

This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.


</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: numbersign	Contours detected: 4	Expected: 2
Glyph name: dollar	Contours detected: 2	Expected: 1 or 3
Glyph name: asterisk	Contours detected: 3	Expected: 1 or 4
Glyph name: plus	Contours detected: 2	Expected: 1
Glyph name: zero	Contours detected: 1	Expected: 2 or 3
Glyph name: two	Contours detected: 2	Expected: 1
Glyph name: three	Contours detected: 2	Expected: 1
Glyph name: five	Contours detected: 3	Expected: 1
Glyph name: seven	Contours detected: 2	Expected: 1
Glyph name: eight	Contours detected: 1	Expected: 3
Glyph name: E	Contours detected: 3	Expected: 1
Glyph name: F	Contours detected: 3	Expected: 1
Glyph name: G	Contours detected: 3	Expected: 1
Glyph name: H	Contours detected: 3	Expected: 1
Glyph name: N	Contours detected: 2	Expected: 1
Glyph name: Q	Contours detected: 3	Expected: 2
Glyph name: R	Contours detected: 3	Expected: 1 or 2
Glyph name: T	Contours detected: 2	Expected: 1
Glyph name: X	Contours detected: 2	Expected: 1
Glyph name: Y	Contours detected: 2	Expected: 1
Glyph name: Z	Contours detected: 2	Expected: 1
Glyph name: e	Contours detected: 1	Expected: 2
Glyph name: f	Contours detected: 2	Expected: 1
Glyph name: h	Contours detected: 2	Expected: 1
Glyph name: m	Contours detected: 3	Expected: 1
Glyph name: n	Contours detected: 2	Expected: 1
Glyph name: r	Contours detected: 2	Expected: 1
Glyph name: t	Contours detected: 2	Expected: 1
Glyph name: u	Contours detected: 2	Expected: 1
Glyph name: w	Contours detected: 2	Expected: 1
Glyph name: x	Contours detected: 2	Expected: 1
Glyph name: y	Contours detected: 2	Expected: 1
Glyph name: z	Contours detected: 2	Expected: 1
Glyph name: currency	Contours detected: 6	Expected: 2
Glyph name: yen	Contours detected: 5	Expected: 1 or 2
Glyph name: section	Contours detected: 1	Expected: 2
Glyph name: registered	Contours detected: 5	Expected: 3 or 4
Glyph name: plusminus	Contours detected: 3	Expected: 1 or 2
Glyph name: uni00B3	Contours detected: 2	Expected: 1
Glyph name: threequarters	Contours detected: 5	Expected: 3 or 4
Glyph name: AE	Contours detected: 5	Expected: 2
Glyph name: Egrave	Contours detected: 4	Expected: 2
Glyph name: Eacute	Contours detected: 4	Expected: 2
Glyph name: Ecircumflex	Contours detected: 4	Expected: 2
Glyph name: Edieresis	Contours detected: 5	Expected: 3
Glyph name: Eth	Contours detected: 3	Expected: 2
Glyph name: Ntilde	Contours detected: 3	Expected: 2
Glyph name: multiply	Contours detected: 2	Expected: 1
Glyph name: Yacute	Contours detected: 3	Expected: 2
Glyph name: ae	Contours detected: 2	Expected: 3
Glyph name: egrave	Contours detected: 2	Expected: 3
Glyph name: eacute	Contours detected: 2	Expected: 3
Glyph name: ecircumflex	Contours detected: 2	Expected: 3
Glyph name: edieresis	Contours detected: 3	Expected: 4
Glyph name: ntilde	Contours detected: 3	Expected: 2
Glyph name: ugrave	Contours detected: 3	Expected: 2
Glyph name: uacute	Contours detected: 3	Expected: 2
Glyph name: ucircumflex	Contours detected: 3	Expected: 2
Glyph name: udieresis	Contours detected: 4	Expected: 3
Glyph name: yacute	Contours detected: 3	Expected: 2
Glyph name: ydieresis	Contours detected: 4	Expected: 3
Glyph name: OE	Contours detected: 5	Expected: 2
Glyph name: Euro	Contours detected: 3	Expected: 1 or 2
Glyph name: trademark	Contours detected: 3	Expected: 2
Glyph name: arrowleft	Contours detected: 2	Expected: 1
Glyph name: arrowup	Contours detected: 2	Expected: 1
Glyph name: arrowright	Contours detected: 2	Expected: 1
Glyph name: arrowdown	Contours detected: 2	Expected: 1
Glyph name: musicalnote	Contours detected: 3	Expected: 1
Glyph name: AE	Contours detected: 5	Expected: 2
Glyph name: E	Contours detected: 3	Expected: 1
Glyph name: Eacute	Contours detected: 4	Expected: 2
Glyph name: Ecircumflex	Contours detected: 4	Expected: 2
Glyph name: Edieresis	Contours detected: 5	Expected: 3
Glyph name: Egrave	Contours detected: 4	Expected: 2
Glyph name: Eth	Contours detected: 3	Expected: 2
Glyph name: Euro	Contours detected: 3	Expected: 1 or 2
Glyph name: F	Contours detected: 3	Expected: 1
Glyph name: G	Contours detected: 3	Expected: 1
Glyph name: H	Contours detected: 3	Expected: 1
Glyph name: N	Contours detected: 2	Expected: 1
Glyph name: Ntilde	Contours detected: 3	Expected: 2
Glyph name: OE	Contours detected: 5	Expected: 2
Glyph name: Q	Contours detected: 3	Expected: 2
Glyph name: R	Contours detected: 3	Expected: 1 or 2
Glyph name: T	Contours detected: 2	Expected: 1
Glyph name: X	Contours detected: 2	Expected: 1
Glyph name: Y	Contours detected: 2	Expected: 1
Glyph name: Yacute	Contours detected: 3	Expected: 2
Glyph name: Z	Contours detected: 2	Expected: 1
Glyph name: ae	Contours detected: 2	Expected: 3
Glyph name: arrowdown	Contours detected: 2	Expected: 1
Glyph name: arrowup	Contours detected: 2	Expected: 1
Glyph name: asterisk	Contours detected: 3	Expected: 1 or 4
Glyph name: currency	Contours detected: 6	Expected: 2
Glyph name: dollar	Contours detected: 2	Expected: 1 or 3
Glyph name: e	Contours detected: 1	Expected: 2
Glyph name: eacute	Contours detected: 2	Expected: 3
Glyph name: ecircumflex	Contours detected: 2	Expected: 3
Glyph name: edieresis	Contours detected: 3	Expected: 4
Glyph name: egrave	Contours detected: 2	Expected: 3
Glyph name: eight	Contours detected: 1	Expected: 3
Glyph name: f	Contours detected: 2	Expected: 1
Glyph name: five	Contours detected: 3	Expected: 1
Glyph name: h	Contours detected: 2	Expected: 1
Glyph name: m	Contours detected: 3	Expected: 1
Glyph name: multiply	Contours detected: 2	Expected: 1
Glyph name: musicalnote	Contours detected: 3	Expected: 1
Glyph name: n	Contours detected: 2	Expected: 1
Glyph name: ntilde	Contours detected: 3	Expected: 2
Glyph name: numbersign	Contours detected: 4	Expected: 2
Glyph name: plus	Contours detected: 2	Expected: 1
Glyph name: plusminus	Contours detected: 3	Expected: 1 or 2
Glyph name: r	Contours detected: 2	Expected: 1
Glyph name: registered	Contours detected: 5	Expected: 3 or 4
Glyph name: section	Contours detected: 1	Expected: 2
Glyph name: seven	Contours detected: 2	Expected: 1
Glyph name: t	Contours detected: 2	Expected: 1
Glyph name: three	Contours detected: 2	Expected: 1
Glyph name: threequarters	Contours detected: 5	Expected: 3 or 4
Glyph name: trademark	Contours detected: 3	Expected: 2
Glyph name: two	Contours detected: 2	Expected: 1
Glyph name: u	Contours detected: 2	Expected: 1
Glyph name: uacute	Contours detected: 3	Expected: 2
Glyph name: ucircumflex	Contours detected: 3	Expected: 2
Glyph name: udieresis	Contours detected: 4	Expected: 3
Glyph name: ugrave	Contours detected: 3	Expected: 2
Glyph name: w	Contours detected: 2	Expected: 1
Glyph name: x	Contours detected: 2	Expected: 1
Glyph name: y	Contours detected: 2	Expected: 1
Glyph name: yacute	Contours detected: 3	Expected: 2
Glyph name: ydieresis	Contours detected: 4	Expected: 3
Glyph name: yen	Contours detected: 5	Expected: 1 or 2
Glyph name: z	Contours detected: 2	Expected: 1
Glyph name: zero	Contours detected: 1	Expected: 2 or 3 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---

All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.

If using GlyphsApp, ligature carets can be set directly on canvas by accessing
the `Glyph -&gt; Set Anchors` menu option or by pressing the `Cmd+U` keyboard
shortcut.


</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check mark characters are in GDEF mark glyph class</summary>

* [com.google.fonts/check/gdef_mark_chars](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gdef.html#com.google.fonts/check/gdef_mark_chars)
<pre>--- Rationale ---

Mark characters should be in the GDEF mark glyph class.


</pre>

* ⚠ **WARN** The following mark characters could be in the GDEF mark glyph class:
	 U+3099 and U+309A [code: mark-chars]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does GPOS table have kerning information?</summary>

* [com.google.fonts/check/gpos_kerning_info](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gpos.html#com.google.fonts/check/gpos_kerning_info)

* ⚠ **WARN** GPOS table lacks kerning information. [code: lacks-kern-info]

</details>
<br>
</details>
<details>
<summary><b>[6] MochiyPopPOne-Regular.ttf</b></summary>
<details>
<summary>🔥 <b>FAIL:</b> Checking OS/2 Metrics match hhea Metrics.</summary>

* [com.google.fonts/check/os2_metrics_match_hhea](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/universal.html#com.google.fonts/check/os2_metrics_match_hhea)
<pre>--- Rationale ---

When OS/2 and hhea vertical metrics match, the same linespacing results on
macOS, GNU+Linux and Windows. Unfortunately as of 2018, Google Fonts has
released many fonts with vertical metrics that don&#x27;t match in this way. When we
fix this issue in these existing families, we will create a visible change in
line/paragraph layout for either Windows or macOS users, which will upset some
of them.

But we have a duty to fix broken stuff, and inconsistent paragraph layout is
unacceptably broken when it is possible to avoid it.

If users complain and prefer the old broken version, they have the freedom to
take care of their own situation.


</pre>

* 🔥 **FAIL** OS/2 sTypoAscender (880) and hhea ascent (1160) must be equal. [code: ascender]

</details>
<details>
<summary>⚠ <b>WARN:</b> Checking OS/2 achVendID.</summary>

* [com.google.fonts/check/vendor_id](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/vendor_id)
<pre>--- Rationale ---

Microsoft keeps a list of font vendors and their respective contact info. This
list is updated regularly and is indexed by a 4-char &quot;Vendor ID&quot; which is
stored in the achVendID field of the OS/2 table.

Registering your ID is not mandatory, but it is a good practice since some
applications may display the type designer / type foundry contact info on some
dialog and also because that info will be visible on Microsoft&#x27;s website:

https://docs.microsoft.com/en-us/typography/vendors/

This check verifies whether or not a given font&#x27;s vendor ID is registered in
that list or if it has some of the default values used by the most common font
editors.

Each new FontBakery release includes a cached copy of that list of vendor IDs.
If you registered recently, you&#x27;re safe to ignore warnings emitted by this
check, since your ID will soon be included in one of our upcoming releases.


</pre>

* ⚠ **WARN** OS/2 VendorID value 'FTDS' is not yet recognized. If you registered it recently, then it's safe to ignore this warning message. Otherwise, you should set it to your own unique 4 character code, and register it with Microsoft at https://www.microsoft.com/typography/links/vendorlist.aspx
 [code: unknown]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check if each glyph has the recommended amount of contours.</summary>

* [com.google.fonts/check/contour_count](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/contour_count)
<pre>--- Rationale ---

Visually QAing thousands of glyphs by hand is tiring. Most glyphs can only be
constructured in a handful of ways. This means a glyph&#x27;s contour count will
only differ slightly amongst different fonts, e.g a &#x27;g&#x27; could either be 2 or 3
contours, depending on whether its double story or single story.

However, a quotedbl should have 2 contours, unless the font belongs to a
display family.

This check currently does not cover variable fonts because there&#x27;s plenty of
alternative ways of constructing glyphs with multiple outlines for each feature
in a VarFont. The expected contour count data for this check is currently
optimized for the typical construction of glyphs in static fonts.


</pre>

* ⚠ **WARN** This check inspects the glyph outlines and detects the total number of contours in each of them. The expected values are infered from the typical ammounts of contours observed in a large collection of reference font families. The divergences listed below may simply indicate a significantly different design on some of your glyphs. On the other hand, some of these may flag actual bugs in the font such as glyphs mapped to an incorrect codepoint. Please consider reviewing the design and codepoint assignment of these to make sure they are correct.

The following glyphs do not have the recommended number of contours:

Glyph name: numbersign	Contours detected: 4	Expected: 2
Glyph name: dollar	Contours detected: 2	Expected: 1 or 3
Glyph name: asterisk	Contours detected: 3	Expected: 1 or 4
Glyph name: plus	Contours detected: 2	Expected: 1
Glyph name: zero	Contours detected: 1	Expected: 2 or 3
Glyph name: two	Contours detected: 2	Expected: 1
Glyph name: three	Contours detected: 2	Expected: 1
Glyph name: five	Contours detected: 3	Expected: 1
Glyph name: seven	Contours detected: 2	Expected: 1
Glyph name: eight	Contours detected: 1	Expected: 3
Glyph name: E	Contours detected: 3	Expected: 1
Glyph name: F	Contours detected: 3	Expected: 1
Glyph name: G	Contours detected: 3	Expected: 1
Glyph name: H	Contours detected: 3	Expected: 1
Glyph name: N	Contours detected: 2	Expected: 1
Glyph name: Q	Contours detected: 3	Expected: 2
Glyph name: R	Contours detected: 3	Expected: 1 or 2
Glyph name: T	Contours detected: 2	Expected: 1
Glyph name: X	Contours detected: 2	Expected: 1
Glyph name: Y	Contours detected: 2	Expected: 1
Glyph name: Z	Contours detected: 2	Expected: 1
Glyph name: e	Contours detected: 1	Expected: 2
Glyph name: f	Contours detected: 2	Expected: 1
Glyph name: h	Contours detected: 2	Expected: 1
Glyph name: m	Contours detected: 3	Expected: 1
Glyph name: n	Contours detected: 2	Expected: 1
Glyph name: r	Contours detected: 2	Expected: 1
Glyph name: t	Contours detected: 2	Expected: 1
Glyph name: u	Contours detected: 2	Expected: 1
Glyph name: w	Contours detected: 2	Expected: 1
Glyph name: x	Contours detected: 2	Expected: 1
Glyph name: y	Contours detected: 2	Expected: 1
Glyph name: z	Contours detected: 2	Expected: 1
Glyph name: currency	Contours detected: 6	Expected: 2
Glyph name: yen	Contours detected: 5	Expected: 1 or 2
Glyph name: section	Contours detected: 1	Expected: 2
Glyph name: registered	Contours detected: 5	Expected: 3 or 4
Glyph name: plusminus	Contours detected: 3	Expected: 1 or 2
Glyph name: uni00B3	Contours detected: 2	Expected: 1
Glyph name: threequarters	Contours detected: 5	Expected: 3 or 4
Glyph name: AE	Contours detected: 5	Expected: 2
Glyph name: Egrave	Contours detected: 4	Expected: 2
Glyph name: Eacute	Contours detected: 4	Expected: 2
Glyph name: Ecircumflex	Contours detected: 4	Expected: 2
Glyph name: Edieresis	Contours detected: 5	Expected: 3
Glyph name: Eth	Contours detected: 3	Expected: 2
Glyph name: Ntilde	Contours detected: 3	Expected: 2
Glyph name: multiply	Contours detected: 2	Expected: 1
Glyph name: Yacute	Contours detected: 3	Expected: 2
Glyph name: ae	Contours detected: 2	Expected: 3
Glyph name: egrave	Contours detected: 2	Expected: 3
Glyph name: eacute	Contours detected: 2	Expected: 3
Glyph name: ecircumflex	Contours detected: 2	Expected: 3
Glyph name: edieresis	Contours detected: 3	Expected: 4
Glyph name: ntilde	Contours detected: 3	Expected: 2
Glyph name: ugrave	Contours detected: 3	Expected: 2
Glyph name: uacute	Contours detected: 3	Expected: 2
Glyph name: ucircumflex	Contours detected: 3	Expected: 2
Glyph name: udieresis	Contours detected: 4	Expected: 3
Glyph name: yacute	Contours detected: 3	Expected: 2
Glyph name: ydieresis	Contours detected: 4	Expected: 3
Glyph name: OE	Contours detected: 5	Expected: 2
Glyph name: Euro	Contours detected: 3	Expected: 1 or 2
Glyph name: trademark	Contours detected: 3	Expected: 2
Glyph name: arrowleft	Contours detected: 2	Expected: 1
Glyph name: arrowup	Contours detected: 2	Expected: 1
Glyph name: arrowright	Contours detected: 2	Expected: 1
Glyph name: arrowdown	Contours detected: 2	Expected: 1
Glyph name: musicalnote	Contours detected: 3	Expected: 1
Glyph name: AE	Contours detected: 5	Expected: 2
Glyph name: E	Contours detected: 3	Expected: 1
Glyph name: Eacute	Contours detected: 4	Expected: 2
Glyph name: Ecircumflex	Contours detected: 4	Expected: 2
Glyph name: Edieresis	Contours detected: 5	Expected: 3
Glyph name: Egrave	Contours detected: 4	Expected: 2
Glyph name: Eth	Contours detected: 3	Expected: 2
Glyph name: Euro	Contours detected: 3	Expected: 1 or 2
Glyph name: F	Contours detected: 3	Expected: 1
Glyph name: G	Contours detected: 3	Expected: 1
Glyph name: H	Contours detected: 3	Expected: 1
Glyph name: N	Contours detected: 2	Expected: 1
Glyph name: Ntilde	Contours detected: 3	Expected: 2
Glyph name: OE	Contours detected: 5	Expected: 2
Glyph name: Q	Contours detected: 3	Expected: 2
Glyph name: R	Contours detected: 3	Expected: 1 or 2
Glyph name: T	Contours detected: 2	Expected: 1
Glyph name: X	Contours detected: 2	Expected: 1
Glyph name: Y	Contours detected: 2	Expected: 1
Glyph name: Yacute	Contours detected: 3	Expected: 2
Glyph name: Z	Contours detected: 2	Expected: 1
Glyph name: ae	Contours detected: 2	Expected: 3
Glyph name: arrowdown	Contours detected: 2	Expected: 1
Glyph name: arrowup	Contours detected: 2	Expected: 1
Glyph name: asterisk	Contours detected: 3	Expected: 1 or 4
Glyph name: currency	Contours detected: 6	Expected: 2
Glyph name: dollar	Contours detected: 2	Expected: 1 or 3
Glyph name: e	Contours detected: 1	Expected: 2
Glyph name: eacute	Contours detected: 2	Expected: 3
Glyph name: ecircumflex	Contours detected: 2	Expected: 3
Glyph name: edieresis	Contours detected: 3	Expected: 4
Glyph name: egrave	Contours detected: 2	Expected: 3
Glyph name: eight	Contours detected: 1	Expected: 3
Glyph name: f	Contours detected: 2	Expected: 1
Glyph name: five	Contours detected: 3	Expected: 1
Glyph name: h	Contours detected: 2	Expected: 1
Glyph name: m	Contours detected: 3	Expected: 1
Glyph name: multiply	Contours detected: 2	Expected: 1
Glyph name: musicalnote	Contours detected: 3	Expected: 1
Glyph name: n	Contours detected: 2	Expected: 1
Glyph name: ntilde	Contours detected: 3	Expected: 2
Glyph name: numbersign	Contours detected: 4	Expected: 2
Glyph name: plus	Contours detected: 2	Expected: 1
Glyph name: plusminus	Contours detected: 3	Expected: 1 or 2
Glyph name: r	Contours detected: 2	Expected: 1
Glyph name: registered	Contours detected: 5	Expected: 3 or 4
Glyph name: section	Contours detected: 1	Expected: 2
Glyph name: seven	Contours detected: 2	Expected: 1
Glyph name: t	Contours detected: 2	Expected: 1
Glyph name: three	Contours detected: 2	Expected: 1
Glyph name: threequarters	Contours detected: 5	Expected: 3 or 4
Glyph name: trademark	Contours detected: 3	Expected: 2
Glyph name: two	Contours detected: 2	Expected: 1
Glyph name: u	Contours detected: 2	Expected: 1
Glyph name: uacute	Contours detected: 3	Expected: 2
Glyph name: ucircumflex	Contours detected: 3	Expected: 2
Glyph name: udieresis	Contours detected: 4	Expected: 3
Glyph name: ugrave	Contours detected: 3	Expected: 2
Glyph name: w	Contours detected: 2	Expected: 1
Glyph name: x	Contours detected: 2	Expected: 1
Glyph name: y	Contours detected: 2	Expected: 1
Glyph name: yacute	Contours detected: 3	Expected: 2
Glyph name: ydieresis	Contours detected: 4	Expected: 3
Glyph name: yen	Contours detected: 5	Expected: 1 or 2
Glyph name: z	Contours detected: 2	Expected: 1
Glyph name: zero	Contours detected: 1	Expected: 2 or 3 [code: contour-count]

</details>
<details>
<summary>⚠ <b>WARN:</b> Are there caret positions declared for every ligature?</summary>

* [com.google.fonts/check/ligature_carets](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/googlefonts.html#com.google.fonts/check/ligature_carets)
<pre>--- Rationale ---

All ligatures in a font must have corresponding caret (text cursor) positions
defined in the GDEF table, otherwhise, users may experience issues with caret
rendering.

If using GlyphsApp, ligature carets can be set directly on canvas by accessing
the `Glyph -&gt; Set Anchors` menu option or by pressing the `Cmd+U` keyboard
shortcut.


</pre>

* ⚠ **WARN** This font lacks caret position values for ligature glyphs on its GDEF table. [code: lacks-caret-pos]

</details>
<details>
<summary>⚠ <b>WARN:</b> Check mark characters are in GDEF mark glyph class</summary>

* [com.google.fonts/check/gdef_mark_chars](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gdef.html#com.google.fonts/check/gdef_mark_chars)
<pre>--- Rationale ---

Mark characters should be in the GDEF mark glyph class.


</pre>

* ⚠ **WARN** The following mark characters could be in the GDEF mark glyph class:
	 U+3099 and U+309A [code: mark-chars]

</details>
<details>
<summary>⚠ <b>WARN:</b> Does GPOS table have kerning information?</summary>

* [com.google.fonts/check/gpos_kerning_info](https://font-bakery.readthedocs.io/en/latest/fontbakery/profiles/gpos.html#com.google.fonts/check/gpos_kerning_info)

* ⚠ **WARN** GPOS table lacks kerning information. [code: lacks-kern-info]

</details>
<br>
</details>

### Summary

| 💔 ERROR | 🔥 FAIL | ⚠ WARN | 💤 SKIP | ℹ INFO | 🍞 PASS | 🔎 DEBUG |
|:-----:|:----:|:----:|:----:|:----:|:----:|:----:|
| 0 | 2 | 11 | 167 | 12 | 156 | 0 |
| 0% | 1% | 3% | 48% | 3% | 45% | 0% |

**Note:** The following loglevels were omitted in this report:
* **SKIP**
* **INFO**
* **PASS**
* **DEBUG**
