# π΄ κ°λ°νκ²½

## μλ‘ 

{% hint style="info" %}
_μ΄λ νκ²½μμλ μ§ μκΈ°κ° μ°λ κ°λ° νκ²½μ μΈνν  μ μμ΄μΌ νλ€.μμ£Ό μΈννμ§ μκΈ° λλ¬Έμ ν­μ ν λλ§λ€ μκ°λ³΄λ€ λ§μ μκ°κ³Ό μ€λ₯λ₯Ό κ²½ννλ κ΅¬κ°μ΄λΌκ³  μκ°νκΈ° λλ¬Έμ μ΄ λΆλΆμ λͺννκ³  μ€λ₯ μμ΄ μμλλ‘ ν  μ μμ΄μΌ νλ©° κ°λμ μ μ‘μ λμμΌ λλ€κ³  μκ°νλ€. λ¬Όλ‘  μμλΆλΆμμ λͺ¨λ  κ³Όμ μ μ΄ν΄ν  μλ μκ² μ§λ§, μ΄λμ λλ μκ³  μμ΄μΌ λμ€μ κ°λ° νκ²½μ λν΄μ μ²¨μ­μ΄ κ°λ₯ν  κ²μ΄λΌκ³  μκ°νλ€. νΉν cofing νμΌ κ°μ λΆλΆμ μμ΄μ μμΈν μμλκ³  κΈ°λ‘ν  νμκ° μλ€κ³  μκ°νλ€._
{% endhint %}

## λͺ©μ°¨

1. [κ°λ°νκ²½μΈν](dev\_setting.md#undefined-2)
2. [JavaScript κ°λ°νκ²½ (Node.js) μΈν](dev\_setting.md#javascript-node.js)
3. [TypeScript + React + Jest + ESLint + Parcel κ°λ° νκ²½ μΈν](dev\_setting.md#typescript-+-react-+-jest-+-parcel)

## κ°λ°νκ²½μΈν

κ°λ°νκ²½μΈνμ λΈλ νκ²½μ΄ μ§μμ μΌλ‘ μκ·Έλ μ΄λ λ¨μΌλ‘ κ·Έλλ§λ€ μ€μ μ΄ λ°λμλ μκΈ°λλ¬Έμ μ΄λ ΅λ€κ³  λ³Έλ€. νμ¬ λΈλ λ²μ μ 18.13.0 λλλ‘ LTS μ΅μ  λ²μ μ μ¬μ©νλ κ²μ΄ μ’λ€. fnm or nvm λ± λΈλ κ΄λ¦¬ νλ‘κ·Έλ¨μ μ¬μ©νμ¬ μ΅μ  λ²μ  λΈλλ₯Ό μ¬μ©νμ¬ νλ‘μ νΈλ₯Ό μμνλ κ²μ΄ μ’λ€κ³  μκ°λλ€.

## JavaScript κ°λ°νκ²½ (Node.js) μΈν

* [μ°Έκ³ λ¬Έμ ](https://github.com/ahastudio/til/blob/main/javascript/20181212-setup-javascript-project.md)fnmμ ν΅ν node version κ΄λ¦¬
* [Node.js](https://nodejs.org/en/) ννμ΄μ§
* [fnm](https://github.com/Schniz/fnm)(Fast Node Manager)
* [nvm](https://github.com/nvm-sh/nvm)(Node Version Manager)

λλ λ¬΄μ¨ λ¬Έμ μΈμ§λ λͺ¨λ₯΄κ² μ§λ§, fnmμ΄ μ μλνμ§ μλλ€. κ·Έλμ nvmμ μ΄μ©νμλ€.

1. node μ§μ λ²μ  μ€μΉ

```

nvm install [version]

```

2. node μ§μ λ²μ  μ­μ 

```

nvm uninstall [version]

```

3. node default λ²μ  μ€μ 

```

nvm alias default [version]

```

4. npm μ΅μ λ²μ  μ€μΉ

```

npm install -g npm@latest

```

## TypeScript + React + Jest + Parcel κ°λ°νκ²½μΈν

1. νλ‘μ νΈ ν΄λ λ§λ€κ³  npm μ΄κΈ°ν ν΄μ€λ€.
2. λΉμ°ν <mark style="color:red;">`.gitignore`</mark> λ§λ€μ΄ μ£Όκ³  vscode extentionμ μ΄μ©νλ€.
3. νμμ€ν¬λ¦½νΈ μ€μΉ devλ‘

```

npm i -D typescript

npx tsc --inirt

```

4. npx λΌλκ±΄ devλ‘ νΉμ κΈλ‘λ²λ‘ μ€μΉλ typescript μμ tscλ₯Ό κ°μ Έμμ typescriptλ₯Ό μ΄κΈ° μ€μ νλ κ²μ μλ―Ένλ€. μ΄κ±° νλ©΄ <mark style="color:red;">`tsconfig.json`</mark> μ΄λΌλ νμΌμ΄ μμ±λλλ°, μ¬κΈ°μ jsx μμ± λ³κ²½(react-jsx)νλ€.
5. ESLint μ€μ 

```

npm i -D eslint

npx eslint --init

```

6. <mark style="color:red;">`.eslintrc.js`</mark> μμ νλ€. <mark style="color:red;">`jest:true`</mark>
7. μ¬κΈ°λ <mark style="color:red;">`.eslintignore`</mark> νμΌμ μμ±νλ€.
8. λ¦¬μ‘νΈμ€μΉ

```

npm i react react-dom

npm i -D @types/react @types/react-dom

```

9. jest κ΄λ ¨ λͺ¨λ μ€μΉ

```

npm i -D jest @types/jest @swc/core @swc/jest \
    jest-environment-jsdom \
    @testing-library/react @testing-library/jest-dom
    
```

10. <mark style="color:red;">`jest.config.js`</mark> νμΌμ μμ±ν΄ μ€μΉν swcλ₯Ό μ¬μ©νλ€. confing νμΌ λ΄μ© [μ°Έκ³ ](https://github.com/ahastudio/CodingLife/blob/main/20220726/react/jest.config.js)
11. κΈ°λ³Έ μ½λ μμ±νμ¬ νμ€νΈ λ° λ΄μ©

μμ± νμΌλ€

* <mark style="color:red;">`index.html`</mark>
* <mark style="color:red;">`src/main.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/App.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/App.test.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/components/Greeting.test.tsx`</mark>
* <mark style="color:red;background-color:yellow;">`src/components/Greeting.tsx`</mark>

_<mark style="color:green;">\*\*\*\*</mark>_
