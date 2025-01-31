# Hyprspace

A plugin for Hyprland that implements a workspace overview feature similar to that of KDE Plasma and macOS, aims to provide a mouse-friendly way of workspace and window management.

> Only works with the latest git version currently!



https://github.com/KZDKM/Hyprspace/assets/41317840/ed1a585a-30d5-4a79-a6da-8cc0713828f9


## Features
- [x] Overview interface
    - [x] Workspace minimap
    - [x] Workspace display
- [x] Mouse controls
    - [x] Moving window between workspaces
    - [x] Creating new workspaces
- [x] Configurability
- [x] Animation support
- [x] Multi-monitor support
- [ ] Monitor scaling support
- [ ] aarch64 support (CFunctionHook reimplementation)
- [ ] Touchpad & gesture support

## Installation

- Make sure to use `hyprland-git` (versions newer than this commit: https://github.com/hyprwm/Hyprland/commit/ef23ef60c5641c5903f9cf40571ead7ad6aba1b9)

### Manual

To build, have hyprland headers installed and under the repo directory do:
```
make all
```
Then use `hyprctl plugin load` followed by the absolute path to the `.so` file to load

### Hyprpm
```
hyprpm add https://github.com/KZDKM/Hyprspace
hyprpm enable Hyprspace

```
## Configuration
### Dispatchers
- Use `overview:toggle` dispatcher to toggle workspace overview on current monitor
- Use `overview:close` to close the overview on current monitor if opened
- Use `overview:open` to open the overview on current monitor if closed
- Adding the `all` argument to `overview:close` and `overview:open` would open / close overview on all monitors
### Styling
#### Colors
- `plugin:overview:panelColor`
- `plugin:overview:workspaceActiveBackground`
- `plugin:overview:workspaceInactiveBackground`
- `plugin:overview:workspaceActiveBorder`
- `plugin:overview:workspaceInactiveBorder`
- `plugin:overview:dragAlpha` overrides the alpha of window when dragged in overview (0 - 1, 0 = transparent, 1 = opaque)
#### Layout
- `plugin:overview:panelHeight`
- `plugin:overview:workspaceMargin` spacing of workspaces with eachother and the edge of the panel
- `plugin:overview:centerAligned` whether if workspaces should be aligned at the center (KDE / macOS style) or at the left (Windows style)
- `plugin:overview:overrideGaps` whether if the following tiling gap values should be applied when workspace is open
- `plugin:overview:gapsIn`
- `plugin:overview:gapsOut`
- `plugin:overview:hideBackgroundLayers` do not draw background layers in overview
- `plugin:overview:drawActiveWorkspace` draw the active workspace in overview as-is

### Animation
- The panel uses the `windows` curve for a slide-in animation

### Behaviors
- `plugin:overview:autoDrag` mouse click always drags window when overview is open
- `plugin:overview:autoScroll` mouse scroll on active workspace area always switch workspace
- `plugin:overview:exitOnClick` mouse click without dragging exits overview
- `plugin:overview:switchOnDrop` switch to the workspace when a window is droppped into it
- `plugin:overview:exitOnSwitch` overview exits when overview is switched by clicking on workspace view or by `switchOnDrop`
- `plugin:overview:showNewWorkspace` add a new empty workspace at the end of workspaces view
- `plugin:overview:showEmptyWorkspace` show empty workspaces that are inbetween non-empty workspaces


## Plugin Compatibility
- [x] [hyprsplit](https://github.com/shezdy/hyprsplit) (tested)
