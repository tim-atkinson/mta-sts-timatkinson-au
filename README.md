# mta-sts-timatkinson-au

The [MTA-STS](https://www.rfc-editor.org/rfc/rfc8461) policy for `timatkinson.au`, served by
GitHub Pages at <https://mta-sts.timatkinson.au/.well-known/mta-sts.txt>.

MTA-STS tells sending mail servers to deliver only over TLS, and only to a server holding a
valid certificate for one of the MX hosts the policy lists. Senders find the policy through
the `_mta-sts.timatkinson.au` TXT record and fetch it over HTTPS from `mta-sts.timatkinson.au`.

| File | Purpose |
|------|---------|
| `docs/.well-known/mta-sts.txt` | the policy (`mode: enforce`, one `mx:` line per MX host) |
| `docs/CNAME` | the Pages custom domain |
| `docs/.nojekyll` | lets Pages publish the `.well-known` directory |

Senders cache the policy for `max_age` seconds. Change the `id` in the
`_mta-sts.timatkinson.au` TXT record every time this file changes, or they will not fetch
the new version.

The same setup for another domain is described in
[rybbt/mta-sts-rybbt-com](https://github.com/rybbt/mta-sts-rybbt-com).
