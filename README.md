# Lattice — portfolio site with a Formgong contact form

**Live demo:** https://lattice.formgong.com · Download: the [latest release](https://github.com/formgong/lattice-template/releases/latest) zip.

Шаблон сайту-портфоліо з формою Formgong

A dark, motion-led one-page site for a creative developer or a small studio. One `index.html`: no build step, no dependencies besides Google Fonts. The contact form posts to Formgong and shows "received" only when the server answers `success: true`; any other answer shows the server's message.

## English

**Set up the form**

1. Create a form in the Formgong dashboard and copy its access key.
2. In `index.html`, replace `fk_your_access_key` with that key.
3. Optional: put your Turnstile site key in `data-sitekey` on `<form id="fg-form">`; the widget loads by itself.

**Rebrand**

- Colours and fonts are CSS variables at the top of the `<style>` block (`--bg`, `--line`, `--grid`, `--accent`, `--font`).
- Every border sits on a grid line. The script's `layout()` picks the cell (75px wide screens, 56px phones), the columns and rows for the window, and places each box by grid lines. Change the cell size there, not in CSS.
- Studio name, contacts, projects, services and quotes are placeholders. Projects and services live in the `PROJECTS` and `SERVICES` arrays in the script; quotes are in the HTML.
- The clock reads `data-tz` (an IANA time zone such as `Europe/Lisbon`).

**Motion**

- A light intro spells the studio name, then wipes away (once per tab session; click to skip).
- Boxes slide in from their side as they scroll into view (left half from the left, right half from the right), then their frames are drawn from the top-left corner: top and left lines first, then right and bottom. The hero corners open from their own corner points. Lines are painted by `.b::after` over a transparent border, so they land on the same pixels as the grid.
- One particle orb travels between sections. Any element with `data-orb="sphere|blob|dust"` and `data-orb-color="white|teal|amber"` becomes a stop.
- Scroll drives the hero split, the pinned project switcher (wide screens), the about text, and the bottom progress line. Headings reveal with clip-path; numbers count up; quotes move one card at a time and stop on grid lines, pausing on hover.
- With `prefers-reduced-motion: reduce` there is no intro, no marquee, no counting, and the orb stays still.

**Credit** — the footer links to Formgong. You may remove it.

## Українська

Темний односторінковий сайт з анімацією для розробника чи невеликої студії. Один файл `index.html`, без збірки й залежностей, окрім Google Fonts. Форма шле заявки у Formgong і пише «отримано» лише тоді, коли сервер відповів `success: true`. В інших випадках показує повідомлення сервера.

**Підключити форму:** створіть форму в кабінеті Formgong, скопіюйте ключ доступу й замініть ним `fk_your_access_key` в `index.html`. Якщо потрібна капча, вкажіть ключ Turnstile в атрибуті `data-sitekey` форми.

**Під себе:** кольори й шрифти задано змінними на початку `<style>`. Кожна рамка стоїть на лінії сітки: розмір клітинки, кількість колонок і рядів рахує функція `layout()` у скрипті. Назва студії, контакти, проєкти, послуги й відгуки тут лише приклади. Проєкти й послуги лежать у масивах `PROJECTS` і `SERVICES` у скрипті.

**Анімація:** блоки в'їжджають збоку, коли з'являються на екрані, а їхні рамки малюються з лівого верхнього кута; світла заставка з назвою, куля з частинок, що переходить між секціями, перемикання проєктів під час прокрутки, лічильники, стрічка відгуків. Якщо в системі ввімкнено зменшення руху, анімації вимикаються.
