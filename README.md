<p align="center">
<img src="https://github.com/andrewRowlinson/mplsoccer/blob/master/docs/source/logo.png?raw=true" width="235px" alt="mplsoccer logo"/>
</p>

**mplsoccer is a Python library for plotting soccer/football charts in Matplotlib 
and loading StatsBomb open-data.**

---

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install mplsoccer.

```bash
pip install mplsoccer
```

---

## Docs

Read more in the [docs](https://mplsoccer.readthedocs.io/) and see some 
examples in our [gallery](https://mplsoccer.readthedocs.io/en/latest/gallery/index.html).

---

## Quick start

Plot a StatsBomb pitch

```python
from mplsoccer import Pitch
import matplotlib.pyplot as plt
pitch = Pitch(pitch_color='grass', line_color='white', stripe=True)
fig, ax = pitch.draw()
plt.show()
```
![alt text](https://github.com/andrewRowlinson/mplsoccer/blob/master/docs/quick_start.png?raw=true 
"statsbomb quick start pitch example")

Plot a Radar
```python
from mplsoccer import Radar
import matplotlib.pyplot as plt
radar = Radar(params=['Agility', 'Speed', 'Strength'], min_range=[0, 0, 0], max_range=[10, 10, 10])
fig, ax = radar.setup_axis()
rings_inner = radar.draw_circles(ax=ax, facecolor='#ffb2b2', edgecolor='#fc5f5f')
values = [5, 3, 10]
radar_poly, rings, vertices = radar.draw_radar(values, ax=ax,
                                               kwargs_radar={'facecolor': '#00f2c1', 'alpha': 0.6}, 
                                               kwargs_rings={'facecolor': '#d80499', 'alpha': 0.6})
range_labels = radar.draw_range_labels(ax=ax)
param_labels = radar.draw_param_labels(ax=ax)
plt.show()
```
![alt text](https://github.com/andrewRowlinson/mplsoccer/blob/master/docs/quick_start_radar.png?raw=true 
"radar quick start example")

---

## What is mplsoccer?
In mplsoccer, you can:

- plot football/soccer pitches on nine different pitch types
- plot radar charts
- plot Nightingale/pizza charts
- plot bumpy charts for showing changes over time
- plot arrows, heatmaps, hexbins, scatter, and (comet) lines
- load StatsBomb data as a tidy dataframe
- standardize pitch coordinates into a single format

I hope mplsoccer helps you make insightful graphics faster,
so you don't have to build charts from scratch.

---

## Want to help?
I would love the community to get involved in mplsoccer.
Take a look at our [open-issues](https://github.com/andrewRowlinson/mplsoccer/issues) 
for inspiration.
Please get in touch at rowlinsonandy@gmail.com or 
[@numberstorm](https://twitter.com/numberstorm) on Twitter to find out more.

---

## Recent changes

View the [changelog](https://github.com/andrewRowlinson/mplsoccer/blob/master/CHANGELOG.md) 
for a full list of the recent changes to mplsoccer.

---

## Inspiration

mplsoccer was inspired by:
- [Peter McKeever](http://petermckeever.com/2020/10/how-to-draw-a-football-pitch/) heavily 
inspired the API design
- [ggsoccer](https://github.com/Torvaney/ggsoccer) influenced the design and Standardizer
- [lastrow's](https://twitter.com/lastrowview) legendary animations
- [fcrstats'](http://fcrstats.com/) tutorials for using football data
- [fcpython's](https://fcpython.com/) Python tutorials for using football data
- [Karun Singh's](https://twitter.com/karun1710) expected threat (xT) visualizations
- [StatsBomb's](https://statsbomb.com/) great visual design and free open-data
- John Burn-Murdoch's [tweet](https://twitter.com/jburnmurdoch/status/1057907312030085120) got me 
interested in football analytics

---

## License

[MIT](https://choosealicense.com/licenses/mit)
