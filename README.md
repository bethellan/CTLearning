# CT ICU Learning App v008

This build uses per-domain `index.json` manifests. Domain content is loaded from:

- `content/domain1/index.json`
- `content/domain2/index.json`

## v008 change

Adds a formatting sanitiser for generated JSON content. This prevents literal strings such as `<h3>Targets and Numbers</h3>`, `&lt;h3&gt;`, stray paragraph tags, code-fence markers, and similar generator artefacts from appearing visibly in the learning screen.

## Folder pattern

```text
index.html
.nojekyll
content/
  domain1/
    index.json
    cardiac-cycle.json
    ...
  domain2/
    index.json
    arterial_line_waveform_interpretation.json
    ...
versions/
  CT-ICU-Learning-App_v008_domain1_formatting_sanitiser.html
```

When you add new topic JSON files, place them in the domain folder and add one object to that domain's `index.json` files array.


## v010 domain3_manifest_loader

This build adds Domain 3 to the external manifest loader. The app now reads `content/domain3/index.json` and then loads all JSON topic files listed in that manifest.
