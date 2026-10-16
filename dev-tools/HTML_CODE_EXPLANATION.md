# Lux Omni V3 — HTML Code Explanation

**Document:** `dev-tools/HTML_CODE_EXPLANATION.md`  
**Code covered:** `site/index.html`  
**Purpose:** Learning reference for the current topbar HTML  
**Status:** HTML structure only; CSS styling and JavaScript behaviour are not implemented here.

> **Maintenance rule:** Whenever `site/index.html` changes in a future push, update the complete HTML snapshot and the relevant explanations in this document. This guide is intended to match the current version of the page, not an older example.

## 1. What this HTML currently builds

The page contains:
- The Lux Omni topbar header.
- A clickable brand area with the application icon, product name, and slogan.
- A right-side controls container.
- A Connections button with an initial checking indicator.
- A dropdown menu with placeholder rows for Google Drive, Dropbox, and OneDrive.
- A feedback area for future connection-operation messages.

The HTML defines the structure and meaning of these elements. It does **not** make the dropdown open, rotate the service icon every 10 seconds, check real connection states, or connect/disconnect accounts. Those behaviours will be implemented later with JavaScript. The linked stylesheet will control the visual layout and appearance.

## 2. Full HTML currently in `site/index.html`

The code below is the complete page with a documentation pointer added at the top of the HTML file.

~~~html
<!DOCTYPE html>
<!-- HTML walkthrough: ../dev-tools/HTML_CODE_EXPLANATION.md. Keep it synchronized when this file changes. -->
<html lang="en">
<head>
    <!-- Document metadata -->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- Topbar stylesheet -->
    <link rel="stylesheet" href="./css/shell/topbar/topbar.css">

    <title>Lux Omni</title>
</head>

<body>
    <!-- Left: brand identity. Right: application controls. -->
    <header class="lux-topbar">

        <!-- Brand logo, name and slogan -->
        <a class="brand" href="./" aria-label="Lux Omni home">
            <span class="brand-mark" aria-hidden="true">
                <img
                    src="./icons/svg/lux-omni-app-icon.svg"
                    alt=""
                >
            </span>

            <span class="brand-copy">
                <span class="brand-name">Lux Omni</span>
                <span class="brand-slogan">
                    One Ecosystem. Endless Possibilities.
                </span>
            </span>
        </a>

        <!-- Right-side application controls -->
        <div class="topbar-actions">

            <!-- Connection status monitor and dropdown -->
            <div class="topbar-connection-control">

                <!-- Rotating service-status button -->
                <button
                    class="topbar-connection-button"
                    id="connection-toggle"
                    type="button"
                    aria-label="Checking service connections. Open connection menu."
                    aria-expanded="false"
                    aria-controls="connection-menu"
                    data-connection-state="checking"
                >
                    <!-- Generic indicator shown during initial checking -->
                    <img
                        class="topbar-active-service-icon"
                        id="active-service-icon"
                        src="./icons/svg/lux-omni-micro-spinner.svg"
                        alt=""
                    >

                    <!-- Status of the currently displayed service -->
                    <span
                        class="topbar-active-status-dot"
                        id="active-status-dot"
                        aria-hidden="true"
                    ></span>
                </button>

                <!-- Service menu, initially hidden -->
                <section
                    class="topbar-connection-menu"
                    id="connection-menu"
                    aria-labelledby="connection-heading"
                    aria-describedby="connection-description"
                    hidden
                >
                    <!-- Dropdown heading -->
                    <div class="topbar-connection-header">
                        <h2 id="connection-heading">
                            Service Connections
                        </h2>

                        <p id="connection-description">
                            View and manage each service independently.
                        </p>
                    </div>

                    <!-- Individual service entries -->
                    <ul class="topbar-service-list">

                        <!-- Google Drive -->
                        <li
                            class="topbar-service-entry"
                            data-provider="google-drive"
                            data-connection-state="checking"
                        >
                            <img
                                class="topbar-service-icon"
                                src="./icons/providers/google-drive.svg"
                                alt=""
                            >

                            <span
                                class="topbar-service-status-dot"
                                aria-hidden="true"
                            ></span>

                            <span class="topbar-service-name">
                                Google Drive
                            </span>

                            <span class="topbar-service-status">
                                Checking...
                            </span>

                            <button
                                class="topbar-service-action"
                                type="button"
                                data-provider="google-drive"
                                disabled
                                aria-label="Checking Google Drive connection"
                            >
                                Checking...
                            </button>
                        </li>

                        <!-- Dropbox -->
                        <li
                            class="topbar-service-entry"
                            data-provider="dropbox"
                            data-connection-state="checking"
                        >
                            <img
                                class="topbar-service-icon"
                                src="./icons/providers/dropbox.svg"
                                alt=""
                            >

                            <span
                                class="topbar-service-status-dot"
                                aria-hidden="true"
                            ></span>

                            <span class="topbar-service-name">
                                Dropbox
                            </span>

                            <span class="topbar-service-status">
                                Checking...
                            </span>

                            <button
                                class="topbar-service-action"
                                type="button"
                                data-provider="dropbox"
                                disabled
                                aria-label="Checking Dropbox connection"
                            >
                                Checking...
                            </button>
                        </li>

                        <!-- OneDrive -->
                        <li
                            class="topbar-service-entry"
                            data-provider="onedrive"
                            data-connection-state="checking"
                        >
                            <img
                                class="topbar-service-icon"
                                src="./icons/providers/onedrive.svg"
                                alt=""
                            >

                            <span
                                class="topbar-service-status-dot"
                                aria-hidden="true"
                            ></span>

                            <span class="topbar-service-name">
                                OneDrive
                            </span>

                            <span class="topbar-service-status">
                                Checking...
                            </span>

                            <button
                                class="topbar-service-action"
                                type="button"
                                data-provider="onedrive"
                                disabled
                                aria-label="Checking OneDrive connection"
                            >
                                Checking...
                            </button>
                        </li>

                    </ul>

                    <!-- Feedback for future connection operations -->
                    <p
                        class="topbar-connection-feedback"
                        id="connection-feedback"
                        role="status"
                        aria-live="polite"
                    ></p>

                </section>
            </div>

            <!-- Future controls: Focus Mode, Sync and Account -->

        </div>
    </header>
</body>
</html>
~~~

## 3. HTML elements: what they do and when to use them

| Element | What it does | Why it is used here |
|---|---|---|
| `<!DOCTYPE html>` | Tells the browser to use modern HTML rendering rules. | It is placed at the start of an HTML document. |
| `<html>` | The root element containing the whole page. | All page markup is inside it. |
| `<head>` | Holds page metadata, stylesheet links, and the document title. | These settings are not the visible page content. |
| `<meta>` | Provides metadata about the document. | The page declares its character encoding and viewport settings. |
| `<link>` | Connects an external resource to the document. | It loads `topbar.css`. |
| `<title>` | Sets the browser-tab title. | It names the page “Lux Omni”. |
| `<body>` | Contains the page content rendered in the browser. | The topbar is inside the body. |
| `<header>` | Represents introductory or navigational content for a page or section. | It is the main application topbar. |
| `<a>` | Creates a hyperlink. | The brand logo and name link back to the site's home page. |
| `<div>` | A general-purpose block container. | It groups related topbar controls and the connection feature. |
| `<span>` | A general-purpose inline container. | It wraps small pieces such as the brand name, slogan, service name, and status dot. |
| `<img>` | Displays an image. | It displays the brand mark, checking indicator, and service icons. |
| `<button>` | Creates an interactive control. | It provides the connection-menu toggle and future per-service actions. |
| `<section>` | Represents a thematic section of a page. | It groups the Connections dropdown and gives it a heading. |
| `<h2>` | A level-two heading. | It names the dropdown content “Service Connections”. |
| `<p>` | Defines a paragraph. | It describes the menu and provides a future feedback area. |
| `<ul>` | Creates an unordered list. | It groups the available service entries. |
| `<li>` | Defines one item in a list. | Each provider has its own row. |
| `</element>` | Closes an element that has an opening tag. | Proper opening and closing tags keep the HTML hierarchy valid. |

### Why both `div` and `span`?

Use a `div` when you need a general block container for a group of elements. Use a `span` when you need a small inline wrapper around part of a line or a small UI item. Both can be styled with CSS; neither automatically adds a visual design.

## 4. HTML attributes: what they do and when to use them

An **attribute** is information written inside an opening HTML tag. For example, in `<a href="./" class="brand">`, `href` and `class` are attributes.

| Attribute | What it means | Use in this page |
|---|---|---|
| `lang="en"` | Declares the page language as English. | Helps browsers and assistive technology interpret the page language. |
| `charset="UTF-8"` | Sets the document character encoding. | Supports standard text characters. |
| `name="viewport"` | Identifies the viewport metadata setting. | Lets the next attribute configure the page's viewport. |
| `content="width=device-width, initial-scale=1.0"` | Sets the viewport width to the device width and the initial zoom scale to 1. | Helps the page render appropriately on mobile screens. |
| `rel="stylesheet"` | Says the linked resource is a stylesheet. | Tells the browser that the linked file contains CSS. |
| `href="./"` | Supplies the destination URL for a link. | Makes the brand link point to the current directory's default page. |
| `href="./css/shell/topbar/topbar.css"` | Supplies the location of the CSS file. | Loads the topbar styles. |
| `class="..."` | Assigns one or more CSS class names. | Lets CSS select and style elements. Class names can also help organize markup. |
| `id="..."` | Assigns an identifier that should be unique within the HTML document. | Names specific elements for accessibility references and future JavaScript. |
| `src="..."` | Specifies the image file URL. | Loads each SVG image. The path must match a real file. |
| `alt=""` | Gives the image an empty alternative text. | Marks these images as decorative because nearby text or the button's accessible name provides the meaning. |
| `type="button"` | Defines a regular button rather than a form-submit button. | Prevents the control from acting as a form submit button if later placed inside a form. |
| `aria-label="..."` | Gives an element an accessible name. | Describes the purpose of the topbar button and the initial checking state of each disabled action. |
| `aria-expanded="false"` | Communicates that the controlled dropdown starts closed. | JavaScript should update it to `true` when the menu opens and back to `false` when it closes. |
| `aria-controls="connection-menu"` | References the ID of the element controlled by the button. | Connects the status button to the dropdown it opens. |
| `aria-labelledby="connection-heading"` | Uses another element's ID as the accessible label. | Gives the dropdown its heading as a name. |
| `aria-describedby="connection-description"` | References an element containing a longer description. | Associates the dropdown with its explanatory paragraph. |
| `aria-hidden="true"` | Hides an element from the accessibility tree. | Used for decorative status dots that should not be announced as separate content. |
| `hidden` | Marks an element as not currently displayed. | Keeps the dropdown hidden on initial page load and hides the initial status dot until its state is known. |
| `data-provider="dropbox"` | Adds a custom data attribute identifying a provider. | Lets future JavaScript know which service a row or button belongs to. |
| `data-connection-state="checking"` | Adds a custom data attribute describing the initial connection state. | Provides a starting state marker for the topbar and each service row. This attribute alone does not check anything. |
| `disabled` | Makes a form control unavailable for user interaction. | Prevents users from pressing a Connect/Disconnect action while its status is still being checked. |
| `role="status"` | Identifies an element as a status message region. | Marks the feedback area as status information for assistive technology. |
| `aria-live="polite"` | Requests that updates be announced without interrupting the current screen-reader task. | Intended for future connection-operation feedback. |

## 5. Classes, IDs, and data attributes are different

These three are easy to confuse:

- **Class:** `class="topbar-service-entry"` — a reusable name for styling a group of similar elements.
- **ID:** `id="active-service-icon"` — a unique name for one particular element. An ID must match exactly when referenced by `aria-controls`, `aria-labelledby`, or `aria-describedby`.
- **Data attribute:** `data-provider="google-drive"` — custom information attached to an element so future JavaScript can identify which provider it represents.

The browser does not automatically execute behaviour because one of these names is present. Classes are not built-in design rules, IDs are not actions, and data attributes do not connect an account.

## 6. What the initial states mean

The current markup intentionally starts conservatively:

- The topbar button starts with the generic spinner icon rather than assuming one provider should be displayed first.
- `data-connection-state="checking"` records a placeholder state in the markup.
- The service rows display “Checking...” as temporary text.
- The per-service action buttons are disabled while the status is unknown.
- The connection dropdown has the `hidden` attribute.
- The active status dot has the `hidden` attribute until the app knows which status it represents.

These are initial HTML values only. No real checking or rotation is happening yet.

## 7. Future work that is not implemented in this HTML

The following work is intentionally outside the current HTML-only stage:

1. **CSS:** Arrange the brand on the left and controls on the right; size the icons; style the dropdown; show green, red, or neutral status dots; preserve the hidden state.
2. **JavaScript:** Open and close the dropdown, keep `aria-expanded` in sync, check service status, update the icon and dots, rotate the topbar indicator every 10 seconds, and choose the correct Connect/Disconnect action.
3. **Provider integration:** Verify the status of each supported provider and carry out connection or disconnection requests.
4. **Error handling:** Show a useful message if a status check fails or a connection action cannot complete.

A red dot should not automatically mean “disconnected” if the app has simply failed to verify the status. The final behaviour should distinguish a confirmed disconnected state from an unknown or failed check.

## 8. Icon-path note

The generic spinner path used in the topbar is:

`./icons/svg/lux-omni-micro-spinner.svg`

The provider image paths currently used in the dropdown are examples:

- `./icons/providers/google-drive.svg`
- `./icons/providers/dropbox.svg`
- `./icons/providers/onedrive.svg`

Before testing the page, make sure these provider files exist in that location or update the paths to match the actual SVG files in the repository. A path written in HTML does not create the referenced file.

## 9. Updating this guide after future pushes

When the HTML changes:

1. Copy the complete current `site/index.html` into Section 2 of this document.
2. Update the element and attribute explanations if new tags, IDs, classes, or attributes were added, removed, or renamed.
3. Update the initial-state or icon-path notes if the behaviour implied by the HTML has changed.
4. Commit this documentation update in the same push as the relevant `index.html` change.

This helps keep the learning reference aligned with the actual code.
