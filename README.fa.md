<div align="center">

**[English](README.md)** | **فارسی**

</div>

<div dir="rtl" align="right">

# lib_ui — دسترس‌پذیری

دسترس‌پذیری صفحه‌خوان برای فریم‌ورک رابط کاربری تلگرام دسکتاپ

> فورک از [desktop-app/lib_ui](https://github.com/desktop-app/lib_ui)

## درباره پروژه

این فورک شامل تغییرات دسترس‌پذیری برای lib_ui، فریم‌ورک رابط کاربری تلگرام دسکتاپ، است. این تغییرات پایه‌ای را فراهم می‌کنند که ویجت‌های تلگرام دسکتاپ را برای صفحه‌خوان‌ها قابل دسترس می‌سازد.

کارهای انجام‌شده شامل نقش‌ها و نام‌های مناسب دسترس‌پذیری برای تمام ویجت‌های پایه، پیمایش کیبورد برای کنترل‌های تعاملی، گزارش وضعیت برای چک‌باکس‌ها و تاگل‌ها، پشتیبانی از UIAutomation Invoke، و زیرساخت Accessible::Item برای نمایش عناصر ترسیم‌شده سفارشی است.

## تغییرات ادغام‌شده در مخازن رسمی — ۷ پول‌ریکوئست

</div>

| PR | توضیحات | تاریخ |
|----|---------|-------|
| [#265](https://github.com/desktop-app/lib_ui/pull/265) | **دسترس‌پذیری ویجت‌های پایه** — نقش‌ها و نام‌ها برای برچسب‌ها، انواع دکمه‌ها، ورودی‌ها، منوها، راهنماها؛ فعال‌سازی با کیبورد؛ فکتوری دسترس‌پذیری | اکتبر ۲۰۲۵ |
| [#268](https://github.com/desktop-app/lib_ui/pull/268) | **چک‌باکس و رادیوباتن** — پیمایش با کیبورد (Space/Enter برای تغییر، کلیدهای جهتی برای گروه رادیو)، API وضعیت/مقدار دسترس‌پذیری، گزارش وضعیت checked/checkable | نوامبر ۲۰۲۵ |
| [#270](https://github.com/desktop-app/lib_ui/pull/270) | **وضعیت فشرده دکمه** — گزارش وضعیت فشرده‌شدن برای AbstractButton، رفع اشکال اطلاع‌رسانی تغییر وضعیت چک‌باکس | نوامبر ۲۰۲۵ |
| [#271](https://github.com/desktop-app/lib_ui/pull/271) | **بازگردانی وضعیت فشرده** — Qt وضعیت فشرده را به درستی منتقل نمی‌کند؛ تغییر AbstractButton برگردانده شد و اصلاح چک‌باکس باقی ماند | نوامبر ۲۰۲۵ |
| [#272](https://github.com/desktop-app/lib_ui/pull/272) | **نام SideBarButton** — نام دسترس‌پذیری با تعداد نشان (مثلاً «Chats (3)»)، به‌روزرسانی زنده هنگام تغییر نشان | نوامبر ۲۰۲۵ |
| [#275](https://github.com/desktop-app/lib_ui/pull/275) | **UIAutomation Invoke** — صفحه‌خوان‌ها می‌توانند دکمه‌ها و چک‌باکس‌ها را از طریق الگوی Invoke فعال کنند (NVDA: Insert+Enter) | دسامبر ۲۰۲۵ |
| [#277](https://github.com/desktop-app/lib_ui/pull/277) | **تاگل‌های SettingsButton** — گزارش وضعیت روشن/خاموش برای سوئیچ‌های تنظیمات با اطلاع‌رسانی زنده | دسامبر ۲۰۲۵ |

<div dir="rtl" align="right">

## فایل‌های کلیدی

</div>

| فایل | کاربرد |
|------|--------|
| `ui/accessibility.h/cpp` | فکتوری دسترس‌پذیری، `InstallAccessibleFactory()` |
| `ui/accessible/ui_accessible_widget.h/cpp` | `Accessible::Widget` — رابط QAccessibleWidget برای RpWidget |
| `ui/accessible/ui_accessible_item.h/cpp` | `Accessible::Item` و `SubItem` — فرزندان مجازی برای عناصر ترسیم‌شده |
| `ui/rp_widget.h` | متدهای مجازی پایه دسترس‌پذیری روی RpWidget |
| `ui/widgets/buttons.h/cpp` | فعال‌سازی با کیبورد، وضعیت فشرده، API عملیات |
| `ui/widgets/checkbox.h/cpp` | تغییر وضعیت با کیبورد، گزارش وضعیت checked |
| `ui/widgets/continuous_sliders.h/cpp` | پیمایش با کیبورد، گزارش مقدار |

<div dir="rtl" align="right">

## مجوز

این پروژه تحت مجوز [GNU General Public License v3.0](LICENSE) با استثنای OpenSSL منتشر شده است.

</div>
