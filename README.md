<div align="center">

**[فارسی](README.fa.md)** | **English**

</div>

# lib_ui — Accessibility

Screen reader accessibility for Telegram Desktop's UI framework

> Fork of [desktop-app/lib_ui](https://github.com/desktop-app/lib_ui)

## About

This fork contains the accessibility changes for lib_ui, Telegram Desktop's UI framework. These changes provide the foundation that makes Telegram Desktop's widgets accessible to screen readers.

The work includes proper accessibility roles and names for all base widgets, keyboard navigation for interactive controls, state reporting for checkboxes and toggles, UIAutomation Invoke support, and the Accessible::Item infrastructure for exposing custom-painted elements.

## Contributions Merged Upstream — 7 PRs

| PR | Description | Date |
|----|-------------|------|
| [#265](https://github.com/desktop-app/lib_ui/pull/265) | **Core widget accessibility** — Roles and names for FlatLabel, all button types, inputs, menus, tooltips; keyboard activation for AbstractButton; accessibility factory | Oct 2025 |
| [#268](https://github.com/desktop-app/lib_ui/pull/268) | **Checkbox and Radiobutton** — Keyboard navigation (Space/Enter to toggle, arrow keys for radio groups), accessibility state/value API on RpWidget, checked/checkable state reporting | Nov 2025 |
| [#270](https://github.com/desktop-app/lib_ui/pull/270) | **Button pressed state** — Pressed state reporting for AbstractButton, Checkbox state change notification fix | Nov 2025 |
| [#271](https://github.com/desktop-app/lib_ui/pull/271) | **Revert pressed state** — Qt does not reliably propagate the pressed state; reverted AbstractButton change while keeping the Checkbox fix | Nov 2025 |
| [#272](https://github.com/desktop-app/lib_ui/pull/272) | **SideBarButton name** — Accessibility name with badge count (e.g. "Chats (3)"), live update on badge change | Nov 2025 |
| [#275](https://github.com/desktop-app/lib_ui/pull/275) | **UIAutomation Invoke** — Screen readers can activate buttons and checkboxes via the Invoke pattern (NVDA: Insert+Enter, JAWS: default action) | Dec 2025 |
| [#277](https://github.com/desktop-app/lib_ui/pull/277) | **SettingsButton toggles** — Checked/unchecked state reporting for toggle switches with live change notifications | Dec 2025 |

## Key Files

| File | Purpose |
|------|---------|
| `ui/accessibility.h/cpp` | Accessibility factory, `InstallAccessibleFactory()` |
| `ui/accessible/ui_accessible_widget.h/cpp` | `Accessible::Widget` — QAccessibleWidget for RpWidget |
| `ui/accessible/ui_accessible_item.h/cpp` | `Accessible::Item` and `SubItem` — virtual children for painted elements |
| `ui/rp_widget.h` | Base accessibility virtual methods on RpWidget |
| `ui/widgets/buttons.h/cpp` | Keyboard activation, pressed state, action API |
| `ui/widgets/checkbox.h/cpp` | Keyboard toggle, checked state reporting |
| `ui/widgets/continuous_sliders.h/cpp` | Keyboard navigation, value reporting |

## License

This project is licensed under the [GNU General Public License v3.0](LICENSE), with an OpenSSL exception.
