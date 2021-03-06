# hashparams.js

A simple library for getting/setting/unsetting query string key-value format hash parameters e.g.

``https://example.com/test#parameter1=value1&parameter2&parameter3=&parameter4=value4``

## Basic Usage

### Get

The following ``Get`` examples will use the uri ``https://example.com/test#parameter1=value1&parameter2&parameter3=&parameter4=dfg%24!``

```js
HashParameters.get('parameter1');
> value1
```

```js
HashParameters.get('parameter2');
> null
```

```js
HashParameters.get('parameter3');
> ''
```

```js
HashParameters.get('parameter4');
> dfg$!
```

### Set

```js
HashParameters.set('parameter1', 'value1');
> https://example.com/test#parameter1=value1
```

```js
HashParameters.set('parameter2', null);
> https://example.com/test#parameter1=value1&parameter2
```

```js
HashParameters.set('parameter3', '');
> https://example.com/test#parameter1=value1&parameter2&parameter3=
```

```js
HashParameters.set('parameter3', '');
> https://example.com/test#parameter1=value1&parameter2&parameter3=
```

```js
HashParameters.set('parameter4', 'dfg$!');
> https://example.com/test#parameter1=value1&parameter2&parameter3=&parameter4=dfg%24!
```

### Unset

The following ``Unset`` examples will use the uri ``https://example.com/test#parameter1=value1&parameter2&parameter3=``

```js
HashParameters.unset('parameter2');
> https://example.com/test#parameter1=value1&parameter3=
```

```js
HashParameters.unset('parameter1');
> https://example.com/test#parameter3=
```

```js
HashParameters.unset('parameter3');
> https://example.com/test#
```
