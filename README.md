# Cider app (Apple Music) widget for Qtile

- a Qtile widget for viewing and interacting your current Apple Music track

![cider_widget](https://github.com/SergiMartinezR/qtile-cider-widget/assets/82753872/cff7f1d3-0184-4425-8e10-a4f2391fec4f)

| :exclamation:  Disclaimer  |
|----------------------------|

This is a modified version of [BenGH28/qtile-spotify-widget](https://github.com/BenGH28/qtile-spotify-widget) that's been adapted to work with the [Cider app](https://github.com/ciderapp/Cider) (used to listen to Apple Music).

**Btw I use the free version of Cider (the one in the Archlinux User Repository).

## Install

### Copy the file

- copy the `cider.py` to `~/.config/qtile/` directory. This is the easiest option

### Submodule for the dotfile addicts

- add it as a submodule if you save your dotfiles with git

```sh
# using yadm (a git wrapper)
yadm submodule add https://github.com/SergiMartinezR/qtile-cider-widget ~/.config/qtile/cider
```

Note: You only need to do one of these options to have it on your system

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

- The spotify version made by BenGH28 [BenGH28/qtile-spotify-widget](https://github.com/BenGH28/qtile-spotify-widget). 

## Credits

- [BenGH28/qtile-spotify-widget](https://github.com/BenGH28/qtile-spotify-widget) for coding the widget for to work with Spotify.
