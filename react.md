# React

## https://reactjs.org/docs/error-decoder.html/?invariant=321

https://reactjs.org/docs/error-decoder.html/?invariant=321

1. 依赖版本问题
2. 破坏了 react hooks 的使用规则
3. 同一个应用下有两份 react 代码

基于问题 3

一般都是使用的第三方库在打包时没有将 react 从 dependecnes 出移出，放在 devDependecnes 里。
