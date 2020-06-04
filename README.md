
# Mezzanine Instagram Feed

Connect Mezzanine sites to Instagram feeds.

[![PyPI version](https://badge.fury.io/py/mezzanine-instagram-feed.svg)](https://badge.fury.io/py/mezzanine-instagram-feed)
![Workflow status](https://github.com/unplugstudio/mezzanine-instagram-feed/workflows/Test%20and%20release/badge.svg)

## Installation

1. Install via pip: `pip install mezzanine-instagram-feed`.
2. Add `instagramfeed` to your `INSTALLED_APPS`.

## Usage

Load the templatetag library and pass the username you want to query to the `instagram_posts` template tag.

```django
{% load instagramfeed_tags %}

{% instagram_posts "USERNAME HERE" as posts %}
{% for posts in post %}
  <a href="https://instagram.com/p/{{ post.shortcode }}">
    <img src="{{ post.thumbnail_src }}" alt="{{ post.edge_media_to_caption.edges.0.node.text }}">
  </a>
{% endfor %}
```

**Keep in mind requests to Instagram are cached for 8 hours so new page loads don't always trigger new requests.**

## Configuration

Configuration variables read from `settings.py`:

| Setting          | Default | Description                                                   |
| ---------------- | ------- | ------------------------------------------------------------- |
| `SCRAPERAPI_KEY` | `None`  | If set will use scraperapi.com to proxy requests to Instagram |

## Contributing

Review contribution guidelines at [CONTRIBUTING.md].

[CONTRIBUTING.md]: CONTRIBUTING.md
