1.`Duplicate Encoder`
```Typescript
const appereances = (word: string[], charToCount: string) => {
    return word.filter((char: string) => char === charToCount).length;
};

export function duplicateEncode(word: string) {
    let result = '',
        encodeChar = '';
    const characters = [...word.toLowerCase()];
    characters.forEach((char) => {
        encodeChar = ')';
        if (appereances(characters, char) === 1) {
            encodeChar = '(';
        }
        result += encodeChar;
    });
    return result;
}
```

2.`Find The Odd Int`
```Typescript
const appereances = (numbers: number[], nToCount: number) => {
    return numbers.filter((n: number) => n === nToCount).length;
};

export const findOdd = (xs: number[]): number => {
    const nonRepeatNumbers = new Set(xs);
    for (let n of nonRepeatNumbers) {
        if (appereances(xs, n) % 2 !== 0) return n;
    }
    return -1;
};
```
