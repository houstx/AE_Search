# Home Search — hosting notes

Live at: https://houstx.github.io/AE_Search/

Three files matter. Upload all of them to the repository root.

| File | What it is | How often it changes |
|---|---|---|
| `index.html` | The whole app — map, listings, full brief | Only when the app itself changes |
| `updates.json` | New listings | Whenever a new home is found |
| `robots.txt` | Keeps the page out of Google | Never |

## Adding new homes — the common case

Your agent sends a JSON block. In GitHub open `updates.json`, click the pencil
icon, paste it in replacing everything, commit.

The buyer's page picks it up on her next visit. No download, no button for her
to press. New homes get a green **New** badge and sort to the top, and her saved
homes, comments and hidden list are untouched.

`updates.json` when there is nothing new:

```json
{ "type": "listings-update", "generated": null, "listings": [] }
```

## Changing the app itself

Upload a new `index.html` with the same filename — GitHub replaces it and the
site rebuilds in about a minute. The buyer's saved data survives, because it is
tied to the site address rather than to the file.

## What the buyer's saved data is tied to

Favorites, comments and hidden homes live in her browser, tied to
`houstx.github.io`. They persist between visits on the same device and browser.

They do **not** follow her to a different device or a different browser.
**Save my list** exports them to a file; **Load file** brings them back.

Renaming the repository is safe — her data is keyed to the account address, not
the repository name. Deleting her browser data is what loses it, so it is worth
telling her to tap **Save my list** after a serious session.
