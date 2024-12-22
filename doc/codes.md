<!--
    created: October 19th, 2024
    updated: October 19th, 2024
-->

# codes

```mermaid
---
title: Level Code
---
flowchart TD
	a[read & verify 7-digit magic number] -->
	b[replace special characters] -->
	c[import level data as level #11]
```

```mermaid
---
title: Replay Code
---
flowchart TD
	a[read & verify 8-digit magic number] -->
	b[split string by special delimiter character] -->
	c[import split elements as replay data]
```

# magic number validation
```js
// for level codes
(code.slice(0, 7) - 1234567) == code.slice(7).length

// for replay codes
(code.slice(0, 8) - 12345678) == code.slice(8).length
```