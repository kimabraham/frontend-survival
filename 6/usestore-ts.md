# 🟠 usestore-ts

```typescript
import { singleton } from 'tsyringe';
import { Store } from 'usestore-ts';
import { Action } from 'usestore-ts/dist/esm/src/decorators';

@singleton()
@Store()
export default class CounterStore{
  count = 0;

  // @Action을 먹으면 알아서 publish
  @Action()
  increase(step?:number){
    this.count +=step??1
    //this.publish()
  }
  
  @Action()
  decrease(step?:number){
    this.count -=step??1
    //this.publish()
  }
}
```

```tsx
import useCounterStore from '../hooks/useCounterStore'

// UI
const CountControl = () => {
  const [{count}, store] = useCounterStore()

  return (
    <div>
      <button type='button' onClick={()=>store.increase()}>Increase</button>
      <button type='button' onClick={()=>store.increase(10)}>Increase 10</button>
      <button type='button' onClick={()=>store.decrease()}>Decrease</button>
      <button type='button' onClick={()=>store.decrease(10)}>Decrease 10</button>
    </div>
  )
}

export default CountControl
```

```tsx
import useCounterStore from '../hooks/useCounterStore'

// UI
const Counter = () => {
  const [{count}] = useCounterStore()
  
  return (
    <div>
      <p>Count : {count}</p>
    </div>
  )
}

export default Counter
```

```typescript
import { container } from 'tsyringe'
import useStore from 'usestore-ts/dist/esm/src/useStore';
import CounterStore from '../stores/CounterStore';
// import useObjectStore from './useObjectStore';

const useCounterStore = () => {
  const store = container.resolve(CounterStore)

  return useStore(store) 
  // return useObjectStore(store)
}

export default useCounterStore
```
