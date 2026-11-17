# The KERI Timeline

A sourced timeline of how Key Event Receipt Infrastructure got from an unsolved key-management problem in 2013 to open standards, state law and open infrastructure in 2026.

**Live site:** [kordwarshuis.github.io/KERI-timeline](https://kordwarshuis.github.io/KERI-timeline/)

The page is a static site: `index.html` loads `timeline.json` in the browser. There is no build step.

## View locally

```bash
python3 -m http.server 8080
```

Then open [http://127.0.0.1:8080/](http://127.0.0.1:8080/).

## Layout

```
index.html       Timeline UI (CSS + JS inline)
timeline.json    All eras, categories, sources and events
assets/img/      Brand marks and wave graphic
```

## Contribute

Entries live in `timeline.json`. Prefer a pull request that adds or corrects an event and cites a source.

Fastest path: [edit `timeline.json` on GitHub](https://github.com/kordwarshuis/KERI-timeline/edit/main/timeline.json). GitHub will fork the repo if needed and open a PR.

Locally:

1. Edit `timeline.json`.
2. Check the page in a local server.
3. Open a pull request.

Every entry should say where it comes from. Talk references use an `at` timestamp (`HH:MM:SS`) so the site can deep-link into the recording. Where sources disagree or a date is inferred, add a `note` on the event.

### Event fields

| Field | Meaning |
| --- | --- |
| `id` | Stable kebab-case id |
| `date` | Sortable ISO start date; pad unknown month/day with `-01` |
| `display` | Human-readable date shown on the page |
| `precision` | `day`, `month`, `year`, `range`, or `approx` |
| `era` | Id from `eras` |
| `category` | Id from `categories` |
| `importance` | `3` milestone, `2` notable, `1` detail |
| `status` | `done`, `expected`, or `forecast` |
| `title` | Short headline |
| `summary` | One or two sentences |
| `quote` | Optional; taken from the first listed source |
| `note` | Optional dating or conflict note |
| `sources` | Array of `{ "source": "<id>", "at": "HH:MM:SS" }` and/or `{ "source": "<id>", "note": "…" }` |

`meta` in `timeline.json` documents the same conventions. Add new talk or corpus items under `sources` before citing them from an event.

## Branding

Colours and the KERI Foundation marks follow [keri.foundation](https://keri.foundation/).
