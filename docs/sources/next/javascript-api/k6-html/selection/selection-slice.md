---
title: 'Selection.slice(start [, end])'
excerpt: 'Reduce the set of matched elements to a subset specified by a range of indices.'
---

# Selection.slice(start [, end])

Reduce the set of matched elements to a subset specified by a range of indices.
Mimics [jquery.slice](https://api.jquery.com/slice/)

| Parameter | Type                                                                                   | Description                                                                            |
| --------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| start     | Number                                                                                 | An integer indicating the 0-based position at which the elements begin to be selected. |
| end       | Number                                                                                 | An integer indicating the 0-based position at which the elements stop being selected.  |
| selector  | [Selection](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-html/selection) | A selection.                                                                           |

### Returns

| Type                                                                                   | Description        |
| -------------------------------------------------------------------------------------- | ------------------ |
| [Selection](https://grafana.com/docs/k6/<K6_VERSION>/javascript-api/k6-html/selection) | The new selection. |

### Example

{{< code >}}

```javascript
import { parseHTML } from 'k6/html';
import { sleep } from 'k6';

export default function () {
  const content = `
<dl>
  <dt id="term-1">term 1</dt>
  <dd>definition 1-a</dd>
  <dd>definition 1-b</dd>
  <dd>definition 1-c</dd>
  <dd>definition 1-d</dd>

  <dt id="term-2">term 2</dt>
  <dd>definition 2-a</dd>
  <dd>definition 2-b</dd>
  <dd>definition 2-c</dd>

  <dt id="term-3">term 3</dt>
  <dd>definition 3-a</dd>
  <dd>definition 3-b</dd>
</dl>
  `;
  const doc = parseHTML(content);

  const els = doc.find('dl').children();

  console.log(els.slice(4).text());

  console.log(els.slice(2, 4).text());

  sleep(1);
}
```

{{< /code >}}
