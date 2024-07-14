# TimestampedDictionary<TKey, TValue>

## Definition

|||
|--|--|
|Namespace|Izayoi.Collections|
|Assembly|Izayoi.Collections.TimestampedDictionary.dll|

Represents a collection of timestamped keys and values.

~~~csharp
TimestampedDictionary<TKey, TValue> :
ITimestampedDictionary<TKey, TValue>
where TKey : struct
~~~

### Type Parameters

#### `TKey`

The type of the keys in the dictionary.

#### `TValue`

The type of the values in the dictionary.

### Inheritance
Object -> TimestampedDictionary<TKey,TValue>

## Constructors

|Name|Summary|
|--|--|
|[TimestampedDictionary(in int capacity, in IDictionary<TKey, TValue>? dictionary, in IEqualityComparer<TKey>? comparer)](TimestampedDictionary.Constructors.md)|Initializes an instance of the TimestampedDictionary class with the specified capacity, dicionary and comparer.|

## Properties

#### `Capacity`

Gets the maximum number of key/value pairs that can be contained in the dicionary.  
`-1` indicates unlimited capacity.  
When adding pairs, the oldest pairs is deleted if the limit is exceeded.

#### `Count`

Gets the number of key/value pairs contained in the dictionary.

## Methods

|Name|Returns|Summary|
|--|--|--|
|Clear()|void|Removes all keys and values from the dictionary.|
|Clear(in int newCapacity)|void|Removes all keys and values from the dictionary and resets its capaticy.|
|[ClearBefore(in DateTimeOffset datetime)](TimestampedDictionary.ClearBefore.md#clearbeforein-datetimeoffset-datetime)|int|Delete all keys and values before the specified datetime.|
|[ClearBefore(in long unixTimeMilliseconds)](TimestampedDictionary.ClearBefore.md#clearbeforein-long-unixtimemilliseconds)|int|Delete all keys and values before the specified unixTimeMilliseconds.|
|ContainsKey(in TKey key)|bool|Determines whether the dictionary contains the specified key.|
|AddOrUpdate(in TKey key, in TValue? value)|TimestampedDictionaryData<TKey, TValue>|Adds a key/value pair to the dictionary if the key does not already exist, or updates a key/value pair in the dictionary if the key already exists.|
|[TryAdd(in TKey key, in TValue? value)](TimestampedDictionary.TryAdd.md)|bool|Attempts to add the specified key and value to the dictionary.|
|[TryUpdate(in TKey key, in TValue? newValue)](TimestampedDictionary.TryUpdate.md#tryupdatein-tkey-key-in-tvalue-newvalue)|bool|Updates the value associated with key to newValue.|
|[TryUpdate(in TKey key, in TValue? newValue, in TValue? comparisonValue)](TimestampedDictionary.TryUpdate.md#tryupdatein-tkey-key-in-tvalue-newvalue-in-tvalue-comparisonvalue)|bool|Updates the value associated with key to newValue.|
|TryRemove(in TKey key, out TValue? value)|bool|Attempts to remove and return the value that has the specified key from the dictionary.|
|TryGetValue(in TKey key, out TValue? value)|bool|Gets the value associated with the specified key.|
|TryGetData(in TKey key, out TimestampedDictionaryData<TKey, TValue>? data)|bool|Gets the data associated with the specified key.|
|GetKeys()|HashSet\<TKey>|Gets a hashset containing the keys in the dictionary.|
|GetAddedKeys()|List\<TKey>|Gets a list containing the keys in the dictionary.|
|GetTimestampedKeys()|List<TimestampedKey\<TKey>>|Gets a list containing the timestamped keys in the dictionary.|
|CheckConsistency()|void|Check the consistency of the dictionary. (This method is for debugging.)|

## Applies to

|Product|Versions|
|--|--|
|.NET Standard|2.1|