# FunLan
A simple functional language as a university project
---
Funlan - язык, реализованный на F# для учебного задания по курсу "Функциональное программирование". Этот репозиторий содержит его документацию.  
Команда: Кравцов Алексей, Леонова Елизавета, Бадалян Тигран. Учебная группа: М8О-210Б-22.

## Идея
Наш язык основан на лямбда-исчислении, то есть содержит аппликацию (`App`) и абстракцию (`Lam`). Но это не полностью функциональный язык, например, для удобства были добавлены (`Var`) и (`Let`).

```F#
type id = string 
type expr = 
| App of expr*expr 
| Lam of id*expr 
| Var of id 
| Int of int 
| PFunc of id 
| Cond of expr*expr*expr 
| Let of id*expr*expr 
| LetRec of id*expr*expr 
| Op of id*int*expr list*env 
| Closure of expr*env 
| RClosure of expr*env*id 
| Susp of expr*env 
| EList of expr list 
| ConstE of string 
| ConstL of expr list 
| True 
| False 
and 
  env = Map<id,expr> 
```
