# Miaowing Tab Announcements

Remote announcements for Miaowing Tab.

## How To Publish

1. Create a new sortable directory under `announcements/`.
2. Put the announcement Markdown at `readme.md`.
3. Update `announcements.json` so `latest` points to that Markdown file.
4. Add the same path to the start of `historylist`, with the title shown in the extension's history menu.

Example:

```json
{
  "latest": "announcements/002/readme.md",
  "historylist": [
    {
      "path": "announcements/002/readme.md",
      "title": "Miaowing Tab 1.1.0"
    },
    {
      "path": "announcements/001/readme.md",
      "title": "Miaowing Tab 1.0.0"
    }
  ]
}
```

If `latest` is empty, missing, or `null`, the extension will not show a new announcement.
Keep `historylist` ordered from newest to oldest and include `latest`. Older extension versions ignore
this field, while newer versions still support manifests that only contain `latest`.

## Directory Naming

Use simple numbers so history stays easy to sort:

```text
announcements/001/readme.md
announcements/002/readme.md
announcements/003/readme.md
```

Each `path` is also the announcement id. After a user marks
`announcements/002/readme.md` as read, that exact announcement will not show again.

## Markdown

The extension renders the Markdown file itself in the announcement dialog. Put the title, body, images, lists, and any announcement structure directly in `readme.md`.

Images can live beside the Markdown:

```text
announcements/002/readme.md
announcements/002/images/preview.png
```

Use relative paths for local announcement images:

```md
![Preview](./images/preview.png)
```

Absolute image URLs such as `https://example.com/image.png` are used as-is.
