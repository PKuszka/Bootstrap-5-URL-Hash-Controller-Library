# Bootstrap Hash Controller

A JavaScript library that handles Bootstrap components (such as modals, tooltips, dropdowns, etc.) based on URL hash changes. This library allows you to open or interact with Bootstrap elements directly via the URL, making it easier to control UI components dynamically.

## Features

- Automatically processes the hash in the URL and triggers corresponding Bootstrap elements (e.g., modal, tooltip, toast, etc.).
- Supports dynamic elements, such as modals, collapses, toasts, tooltips, popovers, and dropdowns.
- Handles auto-hide and delay animatioon functionality for components based on custom ```data-bs-fadeout``` and ```data-bs-delay``` attributes.
- Provides smooth scrolling to the target element if specified in the ```data-bs-scroll``` attribute.
- Supports custom event handlers for additional component types.

## Installation

Simply include the BootstrapHashController class in your project, and make sure you have Bootstrap 5 loaded for the library to function correctly.

```
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/PKuszka/Bootstrap-5-URL-Hash-Controller-Library@main/BootstrapHashController.js"></script>
```

## Usage

Collapse:
```
<div class="collapse collapse-horizontal" id="Examplecollapse" data-bs-delay="1000" data-bs-scroll="true">
      this text will only be displayed if you add #Examplecollapse in the url
</div>
```
Modal:
```
<div class="modal fade" id="exampleModal" tabindex="-1" data-bs-fadeout="10000">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
    </div>
  </div>
</div>
```

### Hash Processing

The controller listens for changes in the URL hash and attempts to process it. For example, if the URL is Examplecollapse,exampleModal, it will try to open both #Examplecollapse and #exampleModal if they exist on the page.

```
Example URL: https://example.com#Examplecollapse,exampleModal
```

### Custom HTML Attributes

You can control the behavior of components via custom attributes:

- ```data-bs-fadeout:``` Time in milliseconds after which the component will automatically hide (only supported for modal, toast, offcanvas, popover, and tooltip).
- ```data-bs-delay:``` Delay in milliseconds before the component is shown (only supported for modal, toast, offcanvas, popover, and tooltip).
- ```data-bs-scroll:``` Scrolls the page to the element with smooth scrolling (supported for all elements).

## Available Bootstarp components

The library comes with default handlers for the following Bootstrap components:

- Modal 
- Collapse
- Fade 
- Alert
- Tooltip 
- Offcanvas 
- Popover 
- Toast 
- Tab Pane
- Dropdown 
