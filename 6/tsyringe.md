# ๐ด TSyringe

* External Store๋ฅผ ๊ด๋ฆฌํ๋๋ฐ ์ฌ์ฉ!
* ์ ์ญ์ฒ๋ผ ์ฌ์ฉํ  ์ ์๋ค.
* props "teleport"
* context๊ฐ ์๋ค. ๊ทผ๋ฐ context๊ฐ ๋ฐ๋๋ฉด ๋ค ๋ฐ๋๋ค.
* ๊ฐ๋จํ๊ฒ TSyringe๋ฅผ ์ด์ฉํ  ์ ์๋ค.

TSyringe / reflect-metadata ์ค์น

```bash
npm i tsyringe reflect-metadata
```

`src/stores/Store.ts` ์์ฑ

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

* `useStore.ts` hook ์ผ๋ก ๋ง๋ ๋ค.

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
  // ์ด๋ถ๋ถ ์ดํด๊ฐ ์๋๋ค. ์๋ง๋ ๋ค๋ฅธ ์ํ๋ค ๋๋ฌธ์ ์ด๋ฐ๋ฏ
  
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

* ์ด๊ฒ ์ ์ญ์ฒ๋ผ ์ฌ์ฉ๋๊ธฐ ๋๋ฌธ์ ํ์คํธ์ ๋ฐ๋ก๋ฐ๋ก ํ๊ธฐ๊ฐ ํ๋ค๋ค.

`App.test.tsx`

```tsx
import {container} from 'tsyringe'

  beforeEach(()=>{
    container.clearInstances()
  })
```

* ์ด๋ ๊ฒ ํ๋ฉด๋๋ค. ํด๋ฆฌ์ด\~

