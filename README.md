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
| [#278](https://github.com/desktop-app/lib_ui/pull/278) | Add Accessible::Item for exposing painted (non-QWidget) elements to screen readers | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | v6.6.0 |
| [#284](https://github.com/desktop-app/lib_ui/pull/284) | Accessibility: Add screen reader support for Menu items | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | v6.6.0 |
| [#286](https://github.com/desktop-app/lib_ui/pull/286) | Accessibility: Improve menu accessibility states and navigation | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | v6.6.0 |
| [#292](https://github.com/desktop-app/lib_ui/pull/292) | feat(accessibility): add ButtonMenu role to IconButton and SideBarButton | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | v6.6.4 |
| [#293](https://github.com/desktop-app/lib_ui/pull/293) | Restore menu item focus for accessibility, fix DropdownMenu | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | v6.6.4 |
| [#308](https://github.com/desktop-app/lib_ui/pull/308) | Let ElasticScroll pass unhandled keys to the parent | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | Unreleased |
| [#304](https://github.com/desktop-app/lib_ui/pull/304) | feat(accessibility): support PageTab role and selected state on buttons | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | Unreleased |
| [#311](https://github.com/desktop-app/lib_ui/pull/311) | Use List/ListItem accessibility role for ordered button strips | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | Unreleased |

## What Was Added

- **Core widget accessibility** — Roles, names, and keyboard activation for FlatLabel, FlatInput, InputField, MaskedInputField, CrossButton, IconButton, AbstractButton, SettingsButton, RoundButton, FlatButton
- **Checkbox & Radiobutton** — Keyboard navigation (Space to toggle), checked/checkable states, state change notifications
- **SideBarButton** — Accessibility name includes unread badge count (e.g., "Chats, 5 unread")
- **UIAutomation Invoke** — `IInvokeProvider` support so screen readers can programmatically click buttons and toggle checkboxes
- **SettingsButton toggles** — Checked/unchecked state reporting for screen readers
- **`Accessible::Item` infrastructure** — Exposes painted (non-QWidget) elements as virtual children so screen readers can reach custom-drawn list items
- **Menu accessibility** — Screen reader support for Menu items, improved menu states and navigation, and `ButtonMenu` role for IconButton and SideBarButton
- **DropdownMenu focus** — Restores focus to the correct menu item for accessibility
- **`ElasticScroll` key handling** — Passes unhandled keys (arrows, Home/End) to the parent so scrolled lists stay keyboard-navigable
- **Ordered strips as lists** — `List` / `ListItem` roles (and `PageTab` role with selected state) for ordered button strips such as the chat-folders bar

## Key Files

- `ui/accessible/ui_accessible_widget.h/cpp` — Widget wraps RpWidget for QAccessibleWidget
- `ui/accessible/ui_accessible_item.h/cpp` — Item for virtual/painted list items
- `ui/rp_widget.h` — Base virtual methods for accessibility

## Related Repositories

- [tdesktop-accessible](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible) — Main tracker with releases
- [lib_base](https://github.com/rezabakhshilaktasaraei/lib_base) — Screen reader detection

## License

GNU General Public License v3.0 with OpenSSL exception, same as the official [lib_ui](https://github.com/desktop-app/lib_ui).
