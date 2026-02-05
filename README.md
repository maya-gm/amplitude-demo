# Amplitude Demo Page

A consent-gated demo that replicates [Amplitude.com](https://amplitude.com/) and demonstrates **Analytics**, **Session Replay**, **Guides and Surveys**, and **Experiment** with autocapture (including frustration interactions).

## What’s included

- **Analytics (Browser SDK 2)** – Autocapture: page views, sessions, form interactions, file downloads, attribution, page URL enrichment, **frustration interactions** (rage/dead clicks). No custom events for “Analytics initialized”, “consent given”, or “scroll depth”.
- **Session Replay** – Plugin with `sampleRate: 1` (100% for demo).
- **Guides and Surveys** – Engagement plugin; use the same project in Amplitude to create guides/surveys.
- **Experiment** – JS SDK; set your deployment key in `index.html` (see below).

## Consent

Amplitude is **only** loaded after the user clicks **Accept** in the consent banner. Until then, no scripts are loaded and no events are sent.

## Run the demo

1. Open `index.html` in a browser (file:// or a local server).
2. Click **Accept** in the consent banner.
3. Use the page (click, navigate, submit the form) to generate autocapture and replay data.

For Session Replay and some CDNs, a local server is more reliable:

```bash
npx serve .
# or: python3 -m http.server 8080
```

Then open `http://localhost:3000` (or 8080).

## Experiment deployment key

To enable **Experiment**, replace the placeholder in `index.html`:

```javascript
const EXPERIMENT_DEPLOYMENT_KEY = 'DEPLOYMENT_KEY';
```

Use your real deployment key from **Amplitude → Experiment → Deployment**. If you leave it as `'DEPLOYMENT_KEY'`, the Experiment SDK is not initialized.

## References

- [Browser SDK 2](https://amplitude.com/docs/sdks/analytics/browser/browser-sdk-2)
- [Session Replay Browser Plugin](https://amplitude.com/docs/session-replay/session-replay-plugin)
- [Guides and Surveys Web SDK](https://amplitude.com/docs/guides-and-surveys/sdk)
- [Experiment JavaScript SDK](https://amplitude.com/docs/sdks/experiment-sdks/experiment-javascript)
