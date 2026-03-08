# Security Fix: jQuery Prototype Pollution (CVE-2019-11358)

## Issue reported
`jQuery` versions **1.1.4 through 3.4.0** are vulnerable to prototype pollution when
`jQuery.extend(true, {}, source)` is called with unsanitized input that contains an
enumerable `__proto__` property.

## What was fixed in this repository
- Verified that the portfolio site does **not** load jQuery in `index.html`.
- Updated project documentation to remove jQuery as a listed technology.
- Documented that interactivity is implemented with vanilla JavaScript.

## Impact
Because jQuery is not used by the site, the vulnerable `jQuery.extend(...)` code path is not
present in this project.

## Preventive guidance
If jQuery is added in the future, use a non-vulnerable version (**>= 3.5.0**, preferably latest)
and avoid deep-merging untrusted objects.
