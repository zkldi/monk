# `collection.count`

[Mongo documentation <i class="fa fa-external-link" style="position: relative; top: 2px;" />](http://mongodb.github.io/node-mongodb-native/3.2/api/Collection.html#countDocuments)

Returns the count of documents that would match a `find()` query. The `collection.count()` method does not perform the `find()` operation but instead counts and returns the number of results that match a query. The method points to `collection.countDocuments()` in the mongo driver.

#### Arguments

1. `query` *(String|ObjectId|Object)*: The query for the count.

2. [`options`] *(object)*

3. [`callback`] *(function)*

#### Returns

A promise

#### Example

```js
users.count({name: 'foo'})
users.count('id') // a bit useless but consistent with the rest of the API
users.count() 
```

## Getting an estimated count

[Mongo documentation <i class="fa fa-external-link" style="position: relative; top: 2px;" />](http://mongodb.github.io/node-mongodb-native/3.2/api/Collection.html#estimatedDocumentCount)

If you need to get a fast order of magnitude of the count of *all* documents in your collection, you can use the `estimate` option. 

> ⚠️ The `query` argument will be ignored.

```js
users.count({}, { estimate: true })
```
