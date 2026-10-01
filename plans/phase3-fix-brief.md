IMPLEMENT-ONLY. Work in /root/projects/redesign-uiux. Edit ONLY site/index.html. Keep every other file unchanged. Use your edit tool in place; do not regenerate the whole file.

The page is good. Apply these 8 precision fixes:

1. Line 656, the var STYLES data: two occurrences of #000 inside the Brutalism style entry. Replace both with #0A0A0A (off-black).

2. Delete the meta description line 7 entirely: <meta name="description" content="A merged design skill pack for AI agents: taste-skill judgment plus the ui-ux-pro-max catalog engine, bridged by three dials.">

3. Section "Catalog domains" (HTML around lines 597-613): after the <div class="section-head"> closing tag and before the <div class="chips"> opening tag, insert this one paragraph exactly:

<p class="chips-note">Ten of the catalog domains in the repo&#39;s data/ directory, searched with one command.</p>

4. In the <style> block, after the .chip rule (the one ending with transition: border-color 200ms ease, color 200ms ease; }), add this new rule:

.chips-note {
  margin: var(--space-sm) 0 var(--space-md);
  font-size: 14px;
  color: var(--color-muted-foreground);
}

5. Same .chip rule you just added the note below: append one more declaration inside it, after the transition line: text-transform: uppercase;

6. In the nav (HTML lines 500-509): find <a class="brand" href="#top">redesign<em>-</em>uiux</a> and replace it with exactly:

<a class="brand" href="#top" aria-label="redesign uiux home">redesign<span class="dash">-</span>uiux</a>

7. In the <style> block, the .brand em rule (font-style: normal; color: var(--color-accent); }): replace the selector .brand em with .brand .dash everywhere it appears (it appears exactly once).

8. Verify with node --check that the inline script still parses after your edits. Do not touch anything else.

Done means: node --check passes, zero occurrences of #000 (only #0A0A0A), meta description gone, chips-note paragraph present, .chip has text-transform: uppercase, .selector .dash exists. Print DONE-FIX-1