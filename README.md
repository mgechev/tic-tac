# Tick IT!

A function which pushes a new task into the queue in order to wait completion of a micro-task before it. It's very convenient for testing:

```ts
import tick from 'tick-it';

describe('async module', () => {
  let service;

  beforeEach(() => {
    service = new Service();
  });

  it('should work', async () => {
    const spy = spyOn(service, 'bar');
    service.bar(Promise.resolve(data));

    await tick();

    expect(spy).toHaveBeenCalled();
  });
});
```

# License

MIT

