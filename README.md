# CT ICU Learning App - v007 Manifest Loader

This build uses one manifest per domain so the app does not hard-code topic filenames in JavaScript.

## GitHub Pages structure

```text
index.html
.nojekyll
content/
  domain1/
    index.json
    cardiac-cycle.json
    afterload_svr_and_pvr.json
    ...
  domain2/
    index.json
    arterial_line_waveform_interpretation.json
    ...
versions/
  CT-ICU-Learning-App_v007_manifest_loader.html
```

## Adding a new topic

1. Drop the new JSON file into the relevant domain folder.
2. Open `content/domainX/index.json`.
3. Add one object to the `files` array:

```json
{ "file": "new_topic_file.json", "title": "New Topic Title" }
```

That is the only required app-side update.

## Important

Browsers cannot scan local folders directly. The manifest is the directory index. GitHub Pages will serve these files over HTTPS, so `fetch()` can load the manifest and topic files normally.
