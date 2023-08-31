# Cider app (Apple Music) widget for Qtile

- a Qtile widget for viewing and interacting your current Apple Music track


| :exclamation:  Disclaimer  |
|----------------------------|

This is a modified version of [BenGH28/qtile-spotify-widget](https://github.com/BenGH28/qtile-spotify-widget) that's been adapted to work with the Cider app (used to listen to Apple Music).

## Install

### Copy the file

- copy the `cider.py` to `~/.config/qtile/` directory. This is the easiest option

## In config.py

```python
from cider import Cider

#...rest of config

# add Cider to list of widgets
screens = [
    Screen(
            bottom=bar.Bar(
                widgets=[
                    Cider(), # add config options as you like them
                ],
                size=24,
                # border_width=[2, 0, 2, 0],  # Draw top and bottom borders
                # border_color=["ff00ff", "000000", "ff00ff", "000000"]  # Borders are magenta
            ),
        ),
    ]
]
```

## Customization

| key | default | description |
|-----|---------|-------------|
|play_icon| ''| "icon to display when playing music"|
|pause_icon| ''| "icon to display when music paused"|
|update_interval| 0.5| "polling rate in seconds"|
|format| "{icon} {artist}:{album} - {track}"| "Apple Music display format"|

- see also Qtile's built-in [`TextBox`](https://docs.qtile.org/en/stable/manual/ref/widgets.html#libqtile.widget.TextBox) for more keys to customize

## Alternatives

- [Mpris2](https://docs.qtile.org/en/stable/manual/ref/widgets.html#libqtile.widget.Mpris2) a more generic widget using `dbus-next`
that allows you to display music info from any player (audacious, vlc, etc.).

## Credits

- [BenGH28/qtile-spotify-widget](https://github.com/BenGH28/qtile-spotify-widget) for coding the widget for to work with Spotify.
