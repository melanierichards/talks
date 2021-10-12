# Speaking of Accessibility: How Screen Readers Present Your Content

October 13, 2021 at [An Event Apart Fall Summit](https://aneventapart.com/event/fall-summit-2021#s29276)

The following resources are structured similarly to the talk outline.

## How This Works

### Accessibility APIs

| Operating System | Accessibility API |
| :--------------- | :---------------- |
| Android          | Various APIs in [android.view.accessibility](https://developer.android.com/reference/android/view/accessibility/package-summary), e.g. [AccessibilityNodeInfo](https://developer.android.com/reference/android/view/accessibility/AccessibilityNodeInfo) |
| Chrome OS        | [Proprietary API](https://chromium.googlesource.com/chromium/src/+/master/docs/accessibility/overview.md) closely related to Chromium’s internal accessibility API |
| Linux/Gnome      | **User apps:** [Accessibility Toolkit (ATK)](https://developer.gnome.org/platform-overview/stable/tech-atk.html.ca). **Assistive tech:** [Assistive Technology Service Provider Interface (AT-SPI)](https://wiki.gnome.org/Accessibility)|
| MacOS, iOS       | [NSAccessibility (AXAPI)](https://developer.apple.com/documentation/appkit/accessibility_for_macos) |
| Windows          | [Microsoft Active Accessibility](https://docs.microsoft.com/en-us/windows/win32/winauto/microsoft-active-accessibility) + [IAccessible2](https://wiki.linuxfoundation.org/accessibility/iaccessible2/start) (MSAA + IA2) or [UI Automation](https://docs.microsoft.com/en-us/windows/win32/winauto/entry-uiauto-win32) (UIA) |

### Accessibility API Mappings

* [Accessible Name and Description Computation](https://w3c.github.io/accname/)
* [Core AAM](https://w3c.github.io/core-aam/)
* [Digital Publishing AAM](https://w3c.github.io/dpub-aam/)
* [Graphics AAM](https://w3c.github.io/graphics-aam/)
* [HTML AAM](https://w3c.github.io/html-aam/)
* [SVG AAM](https://w3c.github.io/svg-aam/)

### Accessibility Tree

* [Chromium: Element not exposed to accessibility tree when it is set to display: contents](https://bugs.chromium.org/p/chromium/issues/detail?id=835455)
* [Tweet thread on Webkit's list-style heuristics](https://twitter.com/cookiecrook/status/1337226933822603270)
* [Exposing attributes that do not directly map to accessibility API properties](https://w3c.github.io/core-aam/#mapping_nodirect): cheatsheet to identify items that might take longer for assistive tech to pick up ([same in HTML AAM](https://w3c.github.io/html-aam/#mapping_nodirect))

### Text Interfaces

* [How to visually hide content](https://www.a11yproject.com/posts/2013-01-11-how-to-hide-content/)
* [IA2: IAccessibleText](https://accessibility.linuxfoundation.org/a11yspecs/ia2/docs/html/interface_i_accessible_text.html)
* [NSAccessibility](https://developer.apple.com/documentation/appkit/nsaccessibilityprotocol) > "Configuring Text Elements" section
* [UI Automation Support for Textual Content](https://docs.microsoft.com/en-us/windows/win32/winauto/uiauto-ui-automation-textpattern-overview)

### Events

* [Android AccessibilityEventSource](https://developer.android.com/reference/android/view/accessibility/AccessibilityEventSource)
* [Core AAM: Events](https://w3c.github.io/core-aam/#mapping_events)
* [IA2EventID](https://accessibility.linuxfoundation.org/a11yspecs/ia2/docs/html/_accessible_event_i_d_8idl.html#ae26846b6d521727ab696d20c3f43c0b5)
* [MSAA: WinEvents and Active Accessibility](https://docs.microsoft.com/en-us/windows/win32/winauto/winevents-overview)
* [NSAccessibility notifications](https://developer.apple.com/documentation/appkit/nsaccessibility/notificationuserinfokey/2899676-init)
* [UI Automation Events](https://docs.microsoft.com/en-us/windows/win32/winauto/uiauto-eventsoverview)

## Testing

### Checkers and Linters

* [Accessibility Insights](https://accessibilityinsights.io/)
* [ARC Platform](https://www.tpgi.com/arc-platform/)
* [axe Tools](https://www.deque.com/axe/)
* [Lighthouse](https://developers.google.com/web/tools/lighthouse/)
* [Tenon](https://tenon.io/)
* [WAVE (Web Accessibility Evaluation Tool)](https://wave.webaim.org/)
* [Webhint](https://webhint.io/)
* [Web Accessibility Evaluation Tools List](https://www.w3.org/WAI/ER/tools/)
* [WebAIM Million](https://webaim.org/projects/million/)
* [WebAIM surveys and other projects](https://webaim.org/projects/)

### Manual Testing

* [A11y Project Checklist](https://www.a11yproject.com/checklist/)
* [Accessibility Support](https://a11ysupport.io/)
* [Dragon speech recognition tools](https://www.nuance.com/dragon/business-solutions/accessibility-solutions-for-business.html) (check out [Accessible Text Labels For All](https://www.sarasoueidan.com/blog/accessible-text-labels/) for thoughts on naming elements for speech recognition access)
* [Emulate vision deficiencies](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/accessibility/emulate-vision-deficiencies)
* [forced-colors](forced-colors)
* [How to Meet WCAG (Quick Reference)](https://www.w3.org/WAI/WCAG21/quickref/)
* [prefers-color-scheme](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-color-scheme)
* [prefers-contrast](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-contrast) and [Styling for Windows high contrast with new standards for forced colors](https://blogs.windows.com/msedgedev/2020/09/17/styling-for-windows-high-contrast-with-new-standards-for-forced-colors/)
* [prefers-reduced-motion](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)
* [prefers-reduced-transparency](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-transparency)
* [The Importance Of Manual Accessibility Testing](https://www.smashingmagazine.com/2018/09/importance-manual-accessibility-testing/)
* [Testing with Screen Readers](https://webaim.org/articles/screenreader_testing/)
* [Web Accessibility Perspectives](https://www.w3.org/WAI/perspective-videos/): gives some quick tips on what to think about for particular scenarios

### Potential Browser + Screen Reader Combinations

These suggestions are largely based on common pairings from the [WebAIM screen reader user surveys](https://webaim.org/projects/), and anecdotal knowledge about accessibility API support. This is not a fully exhaustive list, so there are other valid combinations you might want to test. Screen reader names are linked to user docs.

| Operating System | Browser           | Screen Reader |
| :--------------- | :---------------- | :-------------|
| Android          | Chrome            | Talkback |
| MacOS, iOS       | Safari            | VoiceOver |
| Windows          | Chrome            | JAWS |
| Windows          | Microsoft Edge    | Narrator |
| Windows          | Firefox           | NVDA |
| Windows          | Internet Explorer | JAWS |

### Installing and Using Screen Readers

* **JAWS:** [purchase a license for JAWS](https://www.freedomscientific.com/Products/software/JAWS/) (User docs under "Documentation"). [Download latest version of JAWS](https://support.freedomscientific.com/Downloads/JAWS).
* **NVDA:** [download NVDA for free](https://www.nvaccess.org/download/), but consider making a donation. [NVDA user docs](https://www.nvaccess.org/files/nvda/documentation/userGuide.html?)
* **Narrator:** comes pre-installed on Windows. [Narrator user docs](https://support.microsoft.com/en-us/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)
* **Talkback:** comes pre-installed on Android. [Talkback user docs](https://support.google.com/accessibility/android/answer/2633135?hl=en&ref_topic=3529932)
* **VoiceOver:** comes pre-installed on MacOS, iOS. [VoiceOver user docs](https://help.apple.com/voiceover/mac/10.14/), [VoiceOver on iOS user docs](https://help.apple.com/iphone/10/#/iph3e2e415f)
* [Windows Virtual Machines (VMs)](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/)

**Handy cheatsheets:** [Screen Reader Keyboard Shortcuts and Gestures](https://dequeuniversity.com/screenreaders/) (some commands may differ based on your screen reader's current configuration; check the user docs if something isn't working)

### Some Screen Reader Actions to Try

* Read line by line
* Read continuously from a point
* Jump by headings, landmarks, and links
* Search the page
* Interact with tables using table commands
* Jump by form field
* Interact with all interactive elements
* Testing any changes in content or context

### Testing with Users

* [Involving Users in Evaluating Web Accessibility](https://www.w3.org/WAI/test-evaluate/involving-users/)
* [Professional testers](https://www.a11yproject.com/resources/#professional-testers)

## Bug Sleuthing

### Mappings & Web Dev Guidance

* [ARIA in HTML](https://w3c.github.io/html-aria/)
* [ARIA Specification](https://w3c.github.io/aria/)
* [Accessible Name and Description Computation](https://w3c.github.io/accname/)
* [Core AAM](https://w3c.github.io/core-aam/)
* [Digital Publishing AAM](https://w3c.github.io/dpub-aam/)
* [Graphics AAM](https://w3c.github.io/graphics-aam/)
* [HTML AAM](https://w3c.github.io/html-aam/)
* [HTML Living Standard](https://html.spec.whatwg.org/multipage/)
* [SVG AAM](https://w3c.github.io/svg-aam/)
* [Using ARIA](https://w3c.github.io/using-aria/)

### Debugging Tools

#### Browser Dev Tools

* [Chrome DevTools: Accessibility features reference](https://developer.chrome.com/docs/devtools/accessibility/reference/)
* [Microsoft Edge (Chromium) DevTools: Accessibility reference](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/accessibility/reference)
* [Firefox Accessibility Inspector](https://developer.mozilla.org/en-US/docs/Tools/Accessibility_inspector)
* [Safari Webkit Audits](https://webkit.org/web-inspector/audit-tab/)
* [Safari Webkit Node Inspector](https://webkit.org/blog/3302/aria-and-accessibility-inspector/) (may be outdated)

#### Desktop OS API Debuggers

* [Accessibility Insights for Windows](https://accessibilityinsights.io/docs/en/windows/overview/): for UIA Automation
* [AccProbe](https://www.ibm.com/able/accprobe.html) for MSAA + IA2
* [Testing for Accessibility on OS X](https://developer.apple.com/library/archive/documentation/Accessibility/Conceptual/AccessibilityMacOSX/OSXAXTestingApps.html) for AXAPI (a little outdated but should still be pretty accurate; refer also to [these WWDC videos](https://developer.apple.com/videos/play/wwdc2019/257/))

### Where to Report Bugs

* [Apple Accessibility Support Communities](https://discussions.apple.com/community/accessibility)
* [Chromium accessibility bugs](https://bugs.chromium.org/p/chromium/issues/list?can=2&q=component%3ABlink%3EAccessibility) (all Chromium-based browsers, including MS Edge)
* [Gecko accessibility bugs](https://bugzilla.mozilla.org/buglist.cgi?product=Core&component=Disability%20Access%20APIs&resolution=---)
* [Google accessibility](https://www.google.com/accessibility/get-in-touch/)
* [JAWS / VFO accessibility bugs](https://github.com/FreedomScientific/VFO-standards-support/issues)
* [Microsoft Disability Answer Deck](https://www.microsoft.com/en-us/Accessibility/disability-answer-desk?activetab=contact-pivot%3aprimaryr9)
* [NVDA bugs](https://github.com/nvaccess/nvda/issues)
* [Webkit accessibility bugs](https://bugs.webkit.org/buglist.cgi?quicksearch=component%3Aaccessibility)

## Misc

* [24 Accessibility](https://www.24a11y.com/)
* [A11y Project Resources](https://www.a11yproject.com/resources/)
* [A11y Style Guide](https://a11y-style-guide.com/)
* [Accessibility enables resilience](https://www.microsoft.com/en-us/resilience/accessibility-solutions)
* [Accessibility Object Model: explainer](https://github.com/WICG/aom/blob/gh-pages/explainer.md)
* [Accessibility on iOS](https://developer.apple.com/accessibility/ios/)
* [Adrian Roselli's blog](https://adrianroselli.com/tag/accessibility)
* [An adventurer’s guide to W3C specs](https://www.24a11y.com/2019/an-adventurers-guide-to-w3c-specs/)
* [ARIA Authoring Practices](https://w3c.github.io/aria-practices/)
* [The Business Case for Digital Accessibility](https://www.w3.org/WAI/business-case/)
* [Custom Control Accessible Development Checklist](https://w3c.github.io/using-aria/#checklist)
* [Deque University](https://dequeuniversity.com/resources/)
* [Eric Bailey's blog](https://ericwbailey.design/writing/)
* [HTML5 Accessibility](https://html5accessibility.com/)
* [Inclusive Components](https://inclusive-components.design/)
* [Inclusive Design Principles](https://inclusivedesignprinciples.org/)
* [Marco Zehe's blog](https://www.marcozehe.de/)
* [Marcy Sutton's blog](https://marcysutton.com/writing/)
* [Microsoft: Inclusive Design](https://www.microsoft.com/design/inclusive/)
* [Sarah Higley's blog](https://sarahmhigley.com/writing/)
* [Scott O'Hara's blog](https://www.scottohara.me/writing/)
* [Tink (Leonie Watson's blog)](https://tink.uk/)
* [W3C Web Accessibility Initiative: Accessibility Fundamentals Overview](https://www.w3.org/WAI/fundamentals/)
* [WebAIM Articles](https://webaim.org/articles/)
* [Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/)

### Browser Rendering Engine Documentation

* [Chromium: Accessibility Technical Documentation](https://www.chromium.org/developers/design-documents/accessibility)
* [Chromium: Accessibility Overview](https://chromium.googlesource.com/chromium/src/+/master/docs/accessibility/overview.md)
* [Gecko/Mozilla Accessibility](https://wiki.mozilla.org/Accessibility)
* [Webkit blog: accessibility](https://webkit.org/blog/category/accessibility/)

## Image Credits

* [Keeler Oak Tree - distance photo](https://commons.wikimedia.org/wiki/File:Keeler_Oak_Tree_-_distance_photo,_May_2013.jpg) by Msact
* [Scarlet Oak in Oakwood Park, N14](https://commons.wikimedia.org/wiki/File:Scarlet_Oak_in_Oakwood_Park,_N14_-_geograph.org.uk_-_307007.jpg) by Christine Matthews
* [Selective Focus Photography of Green Fern Plant](https://www.pexels.com/photo/selective-focus-photography-of-green-fern-plant-678751/) by Avinash Patel
* [Photo of Snow Field Near Trees](https://www.pexels.com/photo/photo-of-snow-field-near-trees-1978126/) by Burak K
* [Sakura Tree](https://www.pexels.com/photo/sakura-tree-2033997/) by Oleg Magni
* [Trees With Pathway](https://www.pexels.com/photo/trees-with-pathway-1080400/) by Felix Mittermeier
* [Bamboo Tree](https://www.pexels.com/photo/bamboo-tree-320029/) by Alexandr Podvalny
* [Dragon made of tyres in yard](https://www.pexels.com/photo/dragon-made-of-tyres-in-yard-5745009/) by Ryutaro Tsukata
