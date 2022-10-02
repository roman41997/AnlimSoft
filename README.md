# Test

## 1. Какой из двух фрагментов кода не сработает и почему?
```
Фрагмент 1:
	console.log( doubleNum(10) );

	let doubleNum = (num) => {
		let result = num * 2;
		return result;
	}
Фрагмент 2:
	console.log( doubleNum(10) );

	function doubleNum(num) {
    	let result = num * 2;
		return result;
	}

Ответ: Фрагмент 2
Поднятие или hoisting — это механизм в JavaScript, в котором переменные и объявления функций,
передвигаются вверх своей области видимости перед тем, как код будет выполнен.
Ещё до выполнения кода интерпретатор JavaScript загружает в память функции, 
объявленные как function declaration, а также объявления переменных и функций function expression,
но не их значения. В результате функцию function declaration можно вызвать ещё до того, как до неё дойдёт построчное выполнение кода.

```
## 2. Исправьте ошибку в фрагменте коде так, чтобы после компиляции в шаблоне не было лишних тегов:
```
	<template>
	    <component-name
		v-for="i of count" 
		:key="i"
		v-if="i < 10" 
	/>
	</template>

	<script>
        export default {
            data() {
                return {
                    count: 20
                }
            }
        }
	</script>  

Ответ
Использование директив в v-if и v-for одновременно не является хорошей практикой.

<template v-for="i of count" :key="i">
  <component-name
     v-if="i < 10"
 />
</template>

<script>
   export default {
      data() {
        return {
            count: 20
        }
    }
}

```
## 3. Есть массив некоторых строительных материалов, каждый элемент массива - объекты с ключами id и количества материала. Напишите функцию, которая будет возвращать oбьект в формате { "id":"count" }
```
resources = [
                {
                    id: 1,
                    count: 13,
                },
                {
                    id: 2,
                    count: 5,
                }, 
                {
                    id: 3,
                    count: 24,
                },
                {
                    id: 4,
                    count: 101,
                }, 
                {
                    id: 5,
                    count: 72,
                }, 
                {
                    id: 6,
                    count: 64,
                }, 
                {
                    id: 7,
                    count: 305,
                }, 
                {
                    id: 8,
                    count: 67,
                }, 
                {
                    id: 9,
                    count: 95,
                }, 
                {
                    id: 10,
                    count: 21,
                }, 
                {
                    id: 11,
                    count: 37,
                }
            ]

Ожидаемый результат:

   {
        1: 13,
        2: 5,
        3: 24,
        4: 101,
        5: 72,
        6: 64,
        7: 305,
        8: 67,
        9: 95,
        10: 21,
        11: 37,
	}

Ответ

let arrOfObj = resources.map(item => {
  const obj = {}
  obj[item.id] = item.count
  return obj
})

```
