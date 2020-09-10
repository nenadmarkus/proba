---
title: "WAT"
layout: default
date:   2020-01-20
katex:  true
---

wat!!! $3+4^7_2$

$$1+1=2$$


```
// https://www.gamedev.net/blogs/entry/2250902-logarithmic-spiral-distance-field/
function logspi(a, b, R)
{
	return function (x, y) {
		const pi = 3.14156;
		const r = Math.sqrt(x*x + y*y);
		const t = Math.atan2(y, x) + pi;

		const n = (Math.log(r/a)/b - t)/(2*pi);
		const n1 = Math.floor(n);
		const n2 = Math.ceil(n);

		const r1 = a*Math.exp(b*(t + 2*pi*n1));
		const r2 = a*Math.exp(b*(t + 2*pi*n2));

		return Math.abs(Math.min(r2-r, r-r1)) - R;
	}
}

return extrusion(logspi(0.1, 0.1, 0.01), 0.1);
```
