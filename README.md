# Testing markdown anchors

Markdown links aren't working well in Zed's Markdown Preview. Version:
- Zed 1.10.3 0c54c414d522234de7298039708ffe85a116892a  – /home/wink/.local/zed.app/libexec/zed-editor
- OS: Arch Linux, KDE Plasma (Wayland)

## Expected behavior using GitHub with a Browser

Here is a simple example of how Zed Markdown Preview should behave,
while viewing this page on GitHub click on "test 1 line 50" below:
  - GitHub will display test1.md with "test 1 line 50" at the top of the page
  - [test 1 line 50](test1.md#test-1-line-50)

## To test in Zed:

- Clone this repo: `git clone https://github.com/winksaville/zed-markdown-link-issue`
- cd into the repo: `cd zed-markdown-link-issue`
- Open README.md (the normal editor buffer)
- Open this file in preview mode:
  - Click on the eye icon upper right or
  - Right click on this file's tab and from the menu select "Open Markdown Preview"

## Tests when viewing in Markdown Preview

- T1: Fragment link (same file) [Target section](#target-section)
  - Works
- T2: A link with just a file, [test 1](test1.md)
  - Fails: opens the raw file, not the preview.
- T3: A link with a file and fragment [test 1 line 50](test1.md#test-1-line-50)
  - Fails: opens the raw file at whatever the current cursor location is;
    it does not move to the "test 1 line 50" heading.
- T4: Reference links, [this link][1]
  - Fails: same as T3.
- T5: After T1 navigates the preview to Target section, click the back arrow (left of the tab bar).
  - Fails: returns to raw file not the preview.

## Filler lines

line

line

line

line

line

line

line

line

line

line

line

## Target section

Clicking [Target section](#target-section) above should land here.

[1]: test2.md#test-2-line-100
