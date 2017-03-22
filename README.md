# sbot-gatherings

> '[patchcore](https://github.com/ssbc/patchcore) gatherings [depject](https://github.com/depject/depject) plugin for [secure scuttlebutt](https://github.com/ssbc/secure-scuttlebutt)'

## About
`gives` pull-stream sources and observables for building views of gatherings on patchwork

## Needs
```js
exports.needs = nest({
  'sbot.pull.messagesByType': 'first',
  'sbot.pull.links': 'first',
})
```

## Gives
```js
exports.gives = nest({
  'gatherings.pull': [
    'upcoming',
    'hosting',
  ],
  'gatherings.async': [
    'create',
    'setName',
    'setUTCDateTime',
    'setLocation',
    'setDescription',
    'host',
    'rsvp',
  ]
})
```

## Message types

## API

### gatherings.async.create(opts={}, cb)

Creates a new gathering message and calls cb when done. Valid `opts` keys include

- `name` (optional) - The name of the gathering 
- `utcDateTime` (optional) - The utc date and time of the gathering 
- `location` (optional) - The location of the gathering
- `description` (optional) - The desctription of the gathering 
- `hosts` (optional) - Hosts of the gathering

### gatherings.async.setName(opts={}, cb)

Sets the name of the gathering and calls cb when done. Valid `opts` keys include

- `id` (required) - The id of the gathering to name
- `name` (required) - The name of the gathering 

### gatherings.async.setUTCDateTime(opts={}, cb)

Sets the time of the gathering and calls cb when done. Valid `opts` keys include

- `id` (required) - The id of the gathering to name
- `utcDateTime` (required) - The time of the gathering 

### gatherings.async.setLocation(opts={}, cb)

Sets the physical location of the gathering and calls cb when done. Valid `opts` keys include

- `id` (required) - The id of the gathering to name
- `location` (required) - The time of the gathering 

### gatherings.async.setDescription(opts={}, cb)

Sets the physical location of the gathering and calls cb when done. Valid `opts` keys include

- `id` (required) - The id of the gathering to name
- `location` (required) - The time of the gathering 

### gatherings.async.host(opts={}, cb)

Adds or removes a host of the gathering and calls cb when done. Valid `opts` keys include

- `id` (required) - The id of the gathering to name
- `host` (required) - The id of the host 
- `val` (required) - `1` if hosting, `0` if not

### gatherings.async.rsvp(opts={}, cb)

Sets user's rsvp of the gathering to attending / maybe / notGoing and calls cb when done. Valid `opts` keys include

- `id` (required) - The id of the gathering to name
- `host` (required) - The id of the host 
- `val` (required) - `1` if attending, `0` if maybe, `-1` if not

## Install

With [npm](https://npmjs.org/) installed, run

```
$ npm install sbot-gatherings
```

## Acknowledgments

sbot-gatherings was inspired by..

## See Also


## License

ISC

