# Extract Substring with RegEx

If a substring encased by a certain pattern is to be extracted, this can be achieved by using RegEx as shown below.

```typescript
const baseString =
	"uninteresting text, marker(needed information), more unimportant text";
const regEx = /marker\((.*?)\)/g;

const matches = baseString.match(regEx) || [];

const informationToBeExtracted = matches.map((map) => map.replace(regEx, "$1"));

//returns informationToBeExtracted = ['needed information']
```

First, with `(.*?)` a matching group is defined, which can later on be accessed with `"$1"` from the `replace` function. This means, in a first step, all substrings matching the pattern will be extracted _including_ the marker (e.g., "marker(needed information)"). Then in a second step, the extracted substring will be replaced by the matching group.
