# mail-redirect

Tiny static page that redirects `https://curlyfrighz.github.io/mail-redirect/?id=<message-id>`
to `message://<message-id>` so Apple Mail.app opens the message directly.

Built so Discord (and other tools that only auto-linkify `https://`) can
render clickable links into Mail.app, instead of bare `message://` URLs
that have to be copy-pasted.

## Usage

```
https://curlyfrighz.github.io/mail-redirect/?id=<rfc822-message-id>
```

The `<rfc822-message-id>` is the RFC 822 `Message-ID:` header value,
URL-encoded, without surrounding angle brackets. Example:

```
https://curlyfrighz.github.io/mail-redirect/?id=CA%2BMOe6S%40mail.gmail.com
```

The page strips any leading/trailing angle brackets you accidentally
include, then wraps with `%3C` / `%3E` for the `message://` scheme.

Requires Apple Mail.app on macOS / iOS. Other mail clients ignore the
`message://` scheme.
