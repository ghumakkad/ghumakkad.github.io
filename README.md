# अथातो घुमक्कड़ जिज्ञासा

Personal landing page at [pccofvns.live](https://pccofvns.live), built with Jekyll and hosted on GitHub Pages.

## Links

- [Live site](https://pccofvns.live)
- [My CV](https://pccofvns.github.io)

## Tech Stack

| Library | Version | Via |
|---------|---------|-----|
| Bootstrap | 5.3.3 | CDN (jsDelivr) |
| Font Awesome | 6.7.2 | CDN (cdnjs) |
| jQuery | 3.7.1 | CDN (jquery.com) |
| Google Fonts (Vollkorn) | — | CDN (fonts.googleapis.com) |
| Jekyll | GitHub Pages default | GitHub Pages |

## Development

```bash
jekyll serve   # http://localhost:4000
jekyll build   # output to _site/
```

No Gemfile — relies on GitHub Pages' default Jekyll environment. Theme skin is set via `theme_skin` in `_config.yml` (options: `turquoise`, `blue`, `green`, `berry`, `orange`, `ceramic`).
