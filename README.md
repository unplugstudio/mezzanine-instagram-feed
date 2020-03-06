
# Mezzanine Instagram Feed

Connect Mezzanine sites to Instagram feeds

## Installation

1. Install via pip: `pip install mezzanine-instagram-feed`.
2. Add `instagramfeed` to your `INSTALLED_APPS`.

## Usage

Load the templatetag library and pass the username you want to query to the `instagramfeed_photos` template tag.

```django
{% load instagramfeed_tags %}
{% instagramfeed_photos "username" as photos %}
{% for photo in photos %}
  <a href="{{ photo.link }}">
    <img src="{{ photo.images.0.source }}" alt="{{ photo.alt_text }}">
  </a>
{% endfor %}
```

## Contributing

Review contribution guidelines at [CONTRIBUTING.md].

[CONTRIBUTING.md]: CONTRIBUTING.md
