# Tic-Tac 🍬

A function which pushes a new task into the queue in order to provide convenient way to wait for completion of micro-tasks. It's quite useful for testing.

# How to use?

```
npm i tic-tac --save-dev
```

```ts
import tick from 'tic-tac';

class Service {
  foo(promise) {
    promise.then(data => this.bar(data));
  }

  bar(data) {
    // do stuff
  }
}

describe('async module', () => {
  let service;

  beforeEach(() => {
    service = new Service();
  });

  it('should work', async () => {
    const spy = spyOn(service, 'bar');
    service.foo(Promise.resolve({ foo: 'bar' }));

    await tick();

    expect(spy).toHaveBeenCalled();
  });
});
```

# License

MIT

