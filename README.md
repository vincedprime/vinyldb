# vinyldb
VinylDB is a DB

### Initial thought process
1. Many times I've done this
```java
mangoRepository.save(mango);
mangoCache.put(mango.getId(), mango);
```

```java
Mango mangoObj = mangoCache.get(id);
if (mangoObj == null) {
  mangoObj = mangoRepository.get(id);
  saveToCache(mangoObj);
}
return mangoObj;
```

If a DB can have disk and in-memory stores, then it can just do this

```java
mangoRepository.save(mango);
```

```java
Mango mangoObj = mangoRepository.get(id);
return mangoObj;
```

2. Why can't user choose, if they want to just use the in-memory capabilities or disk storage or both
