# Testing markdown anchors

It looks like markdown anchor links aren't working well, I see
the following issues when viewing a markdown file in the zed
preview mode (zed v1.10.0; the same links work on GitHub and in
VS Code preview).

What works:

- A same-file fragment link: [Target section](#target-section)
  scrolls this preview down to the heading near the bottom. But
  then clicking the back arrow (left of the window tabs)
  activates the raw README.md, scrolled to its cursor position,
  instead of returning to the previous preview position.

What fails:

- A link with just a file, [test 1](test1.md), opens the raw
  file, not the preview.
- A link with a file and fragment,
  [test 1 line 50](test1.md#test-1-line-50), opens the raw file
  at whatever the current cursor location is; it does not move
  to the "test 1 line 50" heading.
- Reference links with fragments behave the same way:
  [this link][1] opens the raw test2.md and does not scroll to
  the "test 2 line 100" heading.

line 28 (filler so the Target section below needs scrolling)

line 30

line 32

line 34

line 36

line 38

line 40

line 42

line 44

line 46

line 48

line 50

## Target section

Clicking [Target section](#target-section) above lands here.

[1]: test2.md#test-2-line-100
