## v1.2.3

Fix `whenResult` callback execution

## v1.2.2

Update new API that normalize the inputs for tasks

## v1.2.1

Update latest API changes that removes error field

## v1.2.0

Export `api` for application to be able to access any api from the core

## v1.1.2

Use better communication system between service and MESG Core

## v1.1.1

Fix issue with input conversion for tasks

## v1.1.0

Add library for applications accessible with `require('mesg-js').application()`

- **whenEvent(eventDetails, taskDetails)** that triggers a task when an event occurs
- **whenResult(resultDetails, taskDetails)** that triggers a task when a result occurs

```
require('mesg-js')
  .application()
  .whenEvent({ serviceID: 'xxx', filter: 'request' }, {
    serviceID: 'yyy',
    task: 'taskX',
    inputs: (x, event) => ({
      ...
    })
  })
```

## v1.0.0

Add library for services accessible with `require('mesg-js').service()`

- **listenTask(map<task, function(inputs, outputs)>)** that takes a map of task handlers that are functions with the following signature `taskX(inputs, outputs)`
```
MESG.listenTask({
  taskX: (inputs, outputs) => {
    outputs.outputX({ foo: inputs.valueX })
  }
})
```
- **emitEvent(event, data)** that takes the name of the event and the associated data
```
MESG.emitEvent('eventX', { foo: 'bar' })
```

