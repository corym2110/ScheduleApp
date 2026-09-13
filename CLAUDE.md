# Project conventions

## App shell (all pages)
Every page in this product uses the same shell as `2110 Scheduling Dashboard.dc.html`:

- **Sidebar**: dark rail (`#12141f`), `position: fixed; top:0; left:0; bottom:0`, always fully visible while content scrolls. Collapsible between 232px expanded and 76px icon-only; the `2` logo mark stays visible in both states, only the "2110 Fitness" wordmark hides. Nav items center when collapsed. No internal scroll.
- **Content area**: `margin-left` equal to the sidebar width, animated with the collapse.
- **Header**: 64px, surface background, bottom divider. Left group is the sidebar collapse toggle (chevron flips direction) then the search field. Right group is the light/dark toggle, notifications, and the primary action pill — that group is `flex:none` and the search field absorbs shrink.
- **Layout**: fluid width, native text sizes (no scaled fixed canvas). Grids use `repeat(auto-fit, minmax(...))` so they wrap rather than squeeze. The document scrolls; nothing clips.
- **Theme**: light/dark via `data-theme` on `#app`, with CSS variables (`--bg --surface --text --divider --muted --ok --row --card --accent --accent-deep --on-accent --link --link-hover`). Light-mode accent is the deepened teal; dark mode uses the Nocturne blurple.

New pages should be built by copying this shell and replacing only the `<main>` content.
