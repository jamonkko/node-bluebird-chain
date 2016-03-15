# node-bluebird-chain
Compose your async program flow from pure style functions and promises.
Sorry [await](https://tc39.github.io/ecmascript-asyncawait/#examples), it does not really get any better than this!

## tl;dr
```javascript
  P.chain(
    ['John', 'Mary', 'Spirit'],
    _.reduce((res, name) => _.assign(res, {[name]: getBooksReadAsync(name)}), {}),
    _.mapValues((books) => calculateTasteScoreAsync(books)),
    _.toPairs,
    _.map(_.zipObject(['name', 'score'])),
    _.maxBy('score'),
    _.tap(({name}) => console.log(`${name} has the best taste!`))
  )
```
