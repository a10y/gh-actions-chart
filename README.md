# GitHub Actions Run Frequency

A single-file static web app to visualize how often a GitHub Actions check runs over
time, and how long it takes. Each run is a stacked bar showing **queue time + run time**,
colored green/red for success/failure. Click a bar to jump to the exact Actions run.

## Use it

Open the [hosted page](https://a10y.github.io/gh-actions-chart/), then:

1. Enter a repo as `owner/repo` and click **Load checks**.
2. Pick a workflow/check to chart and **Fetch runs**.
3. Filter by branch, trigger (PR/push), or conclusion.

The current view is encoded in the URL, so you can copy the link to share the exact view.

## GitHub PAT (optional)

For private repos — or to raise the anonymous rate limit — paste a token in the **PAT**
field. A fine-grained token with **Actions: Read-only** + **Metadata: Read-only** on the
target repos is enough. The token is stored only in your browser's `localStorage` and is
**never** placed in the URL; calls go directly to `api.github.com`.

## Run locally

It's a single `index.html` with no build step — open the file directly, or serve it:

```sh
python3 -m http.server
```
