1. `Interfaces guided exercise, using Typescript`

<img width="400" alt="image" src="https://user-images.githubusercontent.com/45276763/178380541-e2e06434-cd65-4473-a959-cfc0be1247c3.png">

2. `Build Tower`
```TypeScript
export const towerBuilder = (nFloors: number): string[] => {
  if (nFloors === 1) return ['*'];
  let finalTower: string[] = [];
  for (let i = 1; i <= nFloors; i++) {
    finalTower.push(
      `${' '.repeat(nFloors - i)}${'*'.repeat(2 * i - 1)}${' '.repeat(
        nFloors - i
      )}`
    );
  }
  return finalTower;
}
```

3. `Meeting`
```Typescript
return s
    .toUpperCase()
    .split(';')
    .sort((firstName: string, secondName: string) => {
      const [aFirstName, aLastName] = firstName.split(':');
      const [bFirstName, bLastName] = secondName.split(':');
      if (aLastName === bLastName) {
        return aFirstName > bFirstName ? 1 : bFirstName > aFirstName ? -1 : 0;
      }
      return aLastName > bLastName ? 1 : bLastName > aLastName ? -1 : 0;
    })
    .map((fullName: string) => {
      const [firstName, lastName] = fullName.split(':');
      return `(${lastName}, ${firstName})`;
    })
    .join('');
```
