# QR Scanner Galaxy remote config

Package-isolated remote controls for
`com.devapp.qrscanner.qr_scanner_app`.

The current configuration enables official Google demo ads only for the signed
QA build. It cannot activate commercial ads because that build maps every
non-off ad mode to Google's fixed test IDs.

## Safe editing

1. Edit `config.json`.
2. Increase `config_revision` for every change.
3. Keep `package_name` unchanged.
4. Set `kill_switches.ads_enabled` to `false` for the immediate global stop.
5. Use each format's `enabled` field for App Open, Interstitial, or Native.
6. Keep `production_approved` false until a separate production build, exact
   package-specific AdMob IDs, consent QA, and explicit production approval.

Frequency, cooldown, delay, session caps, daily caps, placement switches, and
native refresh are bounded again inside the app. Remote values cannot bypass
consent, Pro, billing/fullscreen gates, or compiled limits.

Raw endpoint:

`https://raw.githubusercontent.com/metosapps/qr-scanner-app-galaxy-config/main/config.json`
