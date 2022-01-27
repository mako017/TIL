# Testing two line segments for intersection

An intersection can only occur if two conditions are met:

- The triangle between A, B, and C is in a different orientation (e.g, clockwise) than the triangle between A, B, and D.
- The triangle between C, D, and A is in a different orientation (e.g, clockwise) than the triangle between C, D, and B.

The code below tests this assumption and returns `true` if there is an intersection and `false` if the lines do not intersect. As long as the points don't overlap this function works, for a more thorough implementation see the source article.

```typescript
interface Coordinate {
	x: number;
	y: number;
}
function testIntersection(
	A: Coordinate,
	B: Coordinate,
	C: Coordinate,
	D: Coordinate
): boolean {
	function ccw(A: Coordinate, B: Coordinate, C: Coordinate) {
		return (C.y - A.y) * (B.x - A.x) > (B.y - A.y) * (C.x - A.x);
	}
	return ccw(A, C, D) != ccw(B, C, D) && ccw(A, B, C) != ccw(A, B, D);
}
```

[source](https://www.geeksforgeeks.org/check-if-two-given-line-segments-intersect/)
