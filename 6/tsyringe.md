# 🔴 TSyringe

* External Store를 관리하는데 사용!
* 전역처럼 사용할 수 있다.
* props "teleport"
* context가 있다. 근데 context가 바뀌면 다 바뀐다.
* 간단하게 TSyringe를 이용할 수 있다.

TSyringe / reflect-metadata 설치

```bash
npm i tsyringe reflect-metadata
```

`src/stores/Store.ts` 생성

```tsx

import { singleton } from 'tsyringe';

@singleton()
export default class Store{
  count =0;
}

```

`src/components/Couter.tsx`

```tsx

import {container} from 'tsyringe'

const store  = container.resolve(Store)

```

* `useStore.ts` hook 으로 만든다.

```tsx
import { useEffect } from 'react';
import { container } from 'tsyringe'
import CounterStore from '../stores/CounterStore';
import useForceUpdate from './useForceUpdate';

const useStore = () => {
  const store  = container.resolve(CounterStore)
  const forceUpdate = useForceUpdate()

  useEffect(() => {
    store.addListener(forceUpdate);
    return () => {
      store.removeListener(forceUpdate);
    }
  }, [store, forceUpdate])
  // 이부분 이해가 안된다. 아마도 다른 상태들 때문에 이런듯
  
  return store;
}

export default useStore
```

`src/stores/CountStore.ts`

```typescript
import { singleton } from 'tsyringe';

type Listener = () => void;

@singleton()
export default class CounterStore{
  count = 0;

  listeners = new Set<Listener>();

  increase(){
    this.count +=1
    this.publish()
  }

  decrease(){
    this.count -=1
    this.publish()
  }

  publish(){
    this.listeners.forEach((listener)=>{
      listener()
    })
  }

  addListener(listener:Listener){
    this.listeners.add(listener)
  }

  removeListener(listener:Listener){
    this.listeners.delete(listener)
  }
}
```

* 이게 전역처럼 사용되기 때문에 테스트시 따로따로 하기가 힘들다.

`App.test.tsx`

```tsx
import {container} from 'tsyringe'

  beforeEach(()=>{
    container.clearInstances()
  })
```

* 이렇게 하면된다. 클리어\~

