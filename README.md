# Chrome Ectension

## File Structure

![Chrome Extension File Structure](./README%20Data/filestructure.png)

## Different sizes of icons

| Icon Size | Icon Use                                              |
| --------- | ----------------------------------------------------- |
| 16x16     | Favicon on the extension's pages and context menu.    |
| 32x32     | Windows computers often require this size.            |
| 48x48     | Displays on the Extensions page.                      |
| 128x128   | Displays on installation and in the Chrome Web Store. |

## Manifest File

```json
{
  "manifest_version": 2,
  "name": "My Extension",
  "version": "versionString",
  "description": "A plain text description",
  "icons": {...},
  "browser_action": {...},
  "page_action": {...},
  "background": {
    "scripts": [...],
    "persistent": false
  },
  "content_scripts": [
    {
      "matches": ["http://*/*", "https://*/*"],
      "js": ["contentScript.js"]
    }
  ],
  "permissions": ["tabs", "activeTab"],
  "web_accessible_resources": [...]
}
```

## Content Scripts

Content scripts are files that run in the context of web pages. By using the standard Document Object Model (DOM), they can read details of the web pages the browser visits, or make changes to them.

## Background Scripts

Background scripts are the place to put code that needs to do work without any specific trigger from the user interface. An example of a background script is code that needs to check for new mail in Gmail, or listen for the browser's `onInstalled` event.

## Popup

A popup is a small div that appears on top of the current page. It can be used to display a small amount of information or a form without leaving the current page.

## Options Page

An options page is an HTML page that lets users set preferences such as what pages to show the browser action on, what data to display in the popup, or whether to enable advanced features of the extension.

## DevTools Page

A DevTools page is an HTML page that runs in the context of the Chrome Developer Tools. It can interact with the currently inspected page, and get access to data about the page and the browser.

## Sidebars

A sidebar is an HTML page that runs in the context of a tab, but only shows in the sidebar. It can interact with the currently inspected page, and get access to data about the page and the browser.

## Context Menus

Context menus are menus that appear when you right-click on a page. They can be used to add custom actions to web pages.
