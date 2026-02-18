<div align="center">

# lib_ui — Accessibility

<p>Screen reader accessibility for Telegram Desktop's UI framework</p>

<p>
  <a href="#english"><strong>English</strong></a> |
  <a href="#فارسی"><strong>فارسی</strong></a>
</p>

<p>
  <em>Fork of <a href="https://github.com/desktop-app/lib_ui">desktop-app/lib_ui</a></em>
</p>

</div>

---

<details open>
<summary id="english"><h2>English</h2></summary>

### About

This fork contains accessibility changes for [lib_ui](https://github.com/desktop-app/lib_ui), the UI framework used by Telegram Desktop. These changes provide the foundation that makes Telegram Desktop's widgets accessible to screen readers.

The work includes proper accessibility roles and names for all core widgets, keyboard navigation for interactive controls, state reporting for checkboxes and toggles, UIAutomation Invoke support, and the `Accessible::Item` infrastructure for exposing custom-painted elements.

### Contributions Merged Upstream — 7 PRs

| PR | Description | Merged |
|----|-------------|--------|
| [#265](https://github.com/desktop-app/lib_ui/pull/265) | **Core widget accessibility** — Accessibility factory, roles and names for FlatLabel, FlatButton, RoundButton, IconButton, SettingsButton, LinkButton, InputField, Checkbox, Radiobutton, PopupMenu, MenuItem, Tooltip, BoxContent; keyboard activation (Space/Enter) for AbstractButton; `StrongFocus` policy management when screen reader is active | Oct 2025 |
| [#268](https://github.com/desktop-app/lib_ui/pull/268) | **Checkbox and Radiobutton keyboard navigation** — Space/Enter/Return to toggle Checkbox; arrow keys to navigate between Radiobuttons in same group (auto-detects vertical vs horizontal layout); `accessibilityState()` and `accessibilityValue()` virtual API on RpWidget; `accessibilityStateChanged` and `accessibilityValueChanged` notification helpers | Nov 2025 |
| [#270](https://github.com/desktop-app/lib_ui/pull/270) | **Button pressed state and Checkbox fix** — Pressed state reporting for AbstractButton; fixed `accessibilityStateChanged` in Checkbox to flag which field changed rather than sending the current value | Nov 2025 |
| [#271](https://github.com/desktop-app/lib_ui/pull/271) | **Revert pressed state** — Qt does not reliably propagate the pressed state via `QAbstractButton`, so AbstractButton changes were reverted; Checkbox fix from #270 was preserved | Nov 2025 |
| [#272](https://github.com/desktop-app/lib_ui/pull/272) | **SideBarButton accessibility name** — Returns button text with badge count (e.g. "Chats (3)"); fires `accessibilityNameChanged` when badge updates | Nov 2025 |
| [#275](https://github.com/desktop-app/lib_ui/pull/275) | **UIAutomation Invoke support** — `accessibilityActionNames()` and `accessibilityDoAction()` virtual API on RpWidget; AbstractButton and Checkbox expose "press" action; deferred activation via `QTimer::singleShot(0)` with safety guards; compatible with NVDA Insert+Enter and JAWS default action | Dec 2025 |
| [#277](https://github.com/desktop-app/lib_ui/pull/277) | **SettingsButton toggle state** — Reports `checkable` and `checked` state when a toggle is present; fires `accessibilityStateChanged` on toggle changes | Dec 2025 |

### Currently In Review — 1 PR

| PR | Description |
|----|-------------|
| [#278](https://github.com/desktop-app/lib_ui/pull/278) | **Accessible::Item for painted elements** — `Item` implements `QAccessibleInterface` for virtual children identified by parent widget + index; `SubItem` for multi-column rows; thread-local `cachedItem()` to avoid allocations; new virtual methods on `RpWidget`: `accessibilityChildCount/Name/Description/Value/State/Rect/Role`, column sub-item methods, change notification helpers; `Accessible::Widget` updated to route `childCount/child/indexOfChild/childAt/focusChild` through the virtual child API |

### Key Files

| File | Purpose |
|------|---------|
| `ui/accessibility.h/cpp` | Accessibility factory, `InstallAccessibleFactory()` |
| `ui/accessible/ui_accessible_widget.h/cpp` | `Accessible::Widget` — QAccessibleWidget for RpWidget |
| `ui/accessible/ui_accessible_item.h/cpp` | `Accessible::Item` and `SubItem` — virtual children for painted elements |
| `ui/rp_widget.h` | Base accessibility virtual methods on RpWidget |
| `ui/widgets/buttons.h/cpp` | Keyboard activation, pressed state, action API |
| `ui/widgets/checkbox.h/cpp` | Keyboard toggle, checked state reporting |
| `ui/widgets/continuous_sliders.h/cpp` | Keyboard navigation, value reporting |

</details>

---

<details>
<summary id="فارسی"><h2>فارسی</h2></summary>

<div dir="rtl" align="right">

### درباره پروژه

این فورک شامل تغییرات دسترس‌پذیری برای [lib_ui](https://github.com/desktop-app/lib_ui)، فریم‌ورک رابط کاربری تلگرام دسکتاپ، است. این تغییرات پایه‌ای را فراهم می‌کنند که ویجت‌های تلگرام دسکتاپ را برای صفحه‌خوان‌ها قابل دسترس می‌سازد.

کارهای انجام‌شده شامل نقش‌ها و نام‌های مناسب دسترس‌پذیری برای تمام ویجت‌های پایه، پیمایش کیبورد برای کنترل‌های تعاملی، گزارش وضعیت برای چک‌باکس‌ها و تاگل‌ها، پشتیبانی از UIAutomation Invoke، و زیرساخت `Accessible::Item` برای نمایش عناصر ترسیم‌شده سفارشی است.

### تغییرات ادغام‌شده در مخزن رسمی — ۷ PR

</div>

| PR | توضیحات | تاریخ |
|----|---------|-------|
| [#265](https://github.com/desktop-app/lib_ui/pull/265) | <div dir="rtl"><strong>دسترس‌پذیری ویجت‌های پایه</strong> — فکتوری دسترس‌پذیری، نقش‌ها و نام‌ها برای FlatLabel، انواع دکمه‌ها، ورودی‌ها، منوها، راهنماها؛ فعال‌سازی با کیبورد (Space/Enter)؛ مدیریت StrongFocus هنگام فعال بودن صفحه‌خوان</div> | اکتبر ۲۰۲۵ |
| [#268](https://github.com/desktop-app/lib_ui/pull/268) | <div dir="rtl"><strong>پیمایش کیبورد چک‌باکس و رادیوباتن</strong> — Space/Enter برای تغییر چک‌باکس؛ کلیدهای جهتی برای پیمایش رادیوباتن‌ها؛ API مجازی <code>accessibilityState()</code> و <code>accessibilityValue()</code> روی RpWidget</div> | نوامبر ۲۰۲۵ |
| [#270](https://github.com/desktop-app/lib_ui/pull/270) | <div dir="rtl"><strong>وضعیت فشرده دکمه و اصلاح چک‌باکس</strong> — گزارش وضعیت فشرده برای AbstractButton؛ اصلاح <code>accessibilityStateChanged</code> در چک‌باکس</div> | نوامبر ۲۰۲۵ |
| [#271](https://github.com/desktop-app/lib_ui/pull/271) | <div dir="rtl"><strong>بازگردانی وضعیت فشرده</strong> — Qt وضعیت فشرده را به درستی منتقل نمی‌کند، تغییر AbstractButton برگردانده شد؛ اصلاح چک‌باکس حفظ شد</div> | نوامبر ۲۰۲۵ |
| [#272](https://github.com/desktop-app/lib_ui/pull/272) | <div dir="rtl"><strong>نام دسترس‌پذیری SideBarButton</strong> — متن دکمه با تعداد نشان (مثلاً «Chats (3)»)؛ به‌روزرسانی زنده هنگام تغییر نشان</div> | نوامبر ۲۰۲۵ |
| [#275](https://github.com/desktop-app/lib_ui/pull/275) | <div dir="rtl"><strong>پشتیبانی UIAutomation Invoke</strong> — API مجازی <code>accessibilityActionNames()</code> و <code>accessibilityDoAction()</code>؛ AbstractButton و Checkbox اکشن "press" را ارائه می‌دهند؛ سازگار با NVDA و JAWS</div> | دسامبر ۲۰۲۵ |
| [#277](https://github.com/desktop-app/lib_ui/pull/277) | <div dir="rtl"><strong>وضعیت تاگل SettingsButton</strong> — گزارش وضعیت <code>checkable</code> و <code>checked</code> هنگام وجود تاگل؛ اطلاع‌رسانی زنده تغییرات</div> | دسامبر ۲۰۲۵ |

<div dir="rtl" align="right">

### در انتظار بررسی — ۱ PR

</div>

| PR | توضیحات |
|----|---------|
| [#278](https://github.com/desktop-app/lib_ui/pull/278) | <div dir="rtl"><strong>Accessible::Item برای عناصر ترسیم‌شده</strong> — <code>Item</code> رابط <code>QAccessibleInterface</code> را برای فرزندان مجازی پیاده‌سازی می‌کند؛ <code>SubItem</code> برای ردیف‌های چندستونی؛ <code>cachedItem()</code> برای جلوگیری از تخصیص حافظه؛ متدهای مجازی جدید روی RpWidget برای شمارش، نام، توضیح، مقدار، وضعیت، ابعاد و نقش فرزندان</div> |

<div dir="rtl" align="right">

### فایل‌های کلیدی

</div>

| فایل | کاربرد |
|------|--------|
| `ui/accessibility.h/cpp` | <div dir="rtl">فکتوری دسترس‌پذیری</div> |
| `ui/accessible/ui_accessible_widget.h/cpp` | <div dir="rtl"><code>Accessible::Widget</code> — رابط دسترس‌پذیری برای RpWidget</div> |
| `ui/accessible/ui_accessible_item.h/cpp` | <div dir="rtl"><code>Accessible::Item</code> و <code>SubItem</code> — فرزندان مجازی</div> |
| `ui/rp_widget.h` | <div dir="rtl">متدهای مجازی دسترس‌پذیری پایه</div> |
| `ui/widgets/buttons.h/cpp` | <div dir="rtl">فعال‌سازی کیبورد، وضعیت فشرده، API اکشن</div> |
| `ui/widgets/checkbox.h/cpp` | <div dir="rtl">تغییر با کیبورد، گزارش وضعیت</div> |

</details>
