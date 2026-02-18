# lib_ui — Accessibility Tracker

This repository is a fork of [desktop-app/lib_ui](https://github.com/desktop-app/lib_ui) that tracks **accessibility improvements** to Telegram Desktop's UI framework. All changes listed here are merged into the official upstream repository.

> This is part of the broader [Telegram Desktop Accessibility](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible) effort.

## Merged Pull Requests

| PR | Title | Author | First Telegram Desktop Release |
|---|---|---|---|
| [#265](https://github.com/desktop-app/lib_ui/pull/265) | Add accessibility roles, names, and keyboard activation for core widgets | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.2.5](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.2.5) |
| [#268](https://github.com/desktop-app/lib_ui/pull/268) | Add keyboard navigation and accessibility state handling for Checkbox and Radiobutton | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.2.6](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.2.6) |
| [#270](https://github.com/desktop-app/lib_ui/pull/270) | Add pressed state reporting for AbstractButton and fix Checkbox state notification | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.3.0](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.3.0) |
| [#271](https://github.com/desktop-app/lib_ui/pull/271) | Revert pressed state reporting from AbstractButton | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.3.0](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.3.0) |
| [#272](https://github.com/desktop-app/lib_ui/pull/272) | Add accessibility name for SideBarButton with badge support | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.3.2](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.3.2) |
| [#275](https://github.com/desktop-app/lib_ui/pull/275) | Add UIAutomation Invoke support for buttons and checkboxes | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.3.6](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.3.6) |
| [#277](https://github.com/desktop-app/lib_ui/pull/277) | Report checked state for SettingsButton toggles | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.4.0](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.4.0) |

## What Was Added

- **Core widget accessibility** — Roles, names, and keyboard activation for FlatLabel, FlatInput, InputField, MaskedInputField, CrossButton, IconButton, AbstractButton, SettingsButton, RoundButton, FlatButton
- **Checkbox & Radiobutton** — Keyboard navigation (Space to toggle), checked/checkable states, state change notifications
- **SideBarButton** — Accessibility name includes unread badge count (e.g., "Chats, 5 unread")
- **UIAutomation Invoke** — `IInvokeProvider` support so screen readers can programmatically click buttons and toggle checkboxes
- **SettingsButton toggles** — Checked/unchecked state reporting for screen readers

## Key Files

- `ui/accessible/ui_accessible_widget.h/cpp` — Widget wraps RpWidget for QAccessibleWidget
- `ui/accessible/ui_accessible_item.h/cpp` — Item for virtual/painted list items
- `ui/rp_widget.h` — Base virtual methods for accessibility

## Related Repositories

- [tdesktop-accessible](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible) — Main tracker with releases
- [lib_base](https://github.com/rezabakhshilaktasaraei/lib_base) — Screen reader detection

## License

GNU General Public License v3.0 with OpenSSL exception, same as the official [lib_ui](https://github.com/desktop-app/lib_ui).
