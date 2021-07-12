# priorityQueue
priorityQueue by JS
用JS编写的优先级队列，支持自定义comparator<br>
调用方式如 <code>const pq=new PriorityQueue((a,b)=>a-b)</code>,默认的comparator是(a,b)=>(a-b),即入队的element越小，优先级越大。

## API

### `constructor`([comparator: [Function][]])

队列初始化.

**Arguments**

- (optional) `comparator` ([Function][]) - 自定义的比较函数。


不传任何参数的情况下将会是值越小的element优先级越高。
```javascript

const priorityQueue = new PriorityQueue()//相当于new PriorityQueue((a,b)=>a-b)
```
可传入自定义的comparator.

```javascript

const customQueue = new PriorityQueue((a, b) => {
  return b - a
})
```

### `enqueue`(element: `any`)

入队

**Arguments**

- `element` (`any`) - 入队的元素

element可以是除了null和undefined的任意类型
```javascript
// 可以是数字
priorityQueue.enqueue(2)

// 可以是字符串
priorityQueue.enqueue('let's go')

// 可以是任意类型（除了undefined和null)
priorityQueue.enqueue({ name: 'jarvey' })
```

### `dequeue`(): `any`

弹出队头元素并返回。

**returns** `any`: 队头元素

```javascript
// priorityQueue: [12, 3, 5], comparator: default

const item1 = priorityQueue.dequeue() // 3
const item2 = priorityQueue.dequeue() // 5
const item3 = priorityQueue.dequeue() // 12
```

### `peek`(): `any`

返回队头元素

**returns** `any`: 队头元素

```javascript
// priorityQueue: [12, 3, 5], comparator: default

const item1 = priorityQueue.peek() // 3
const item2 = priorityQueue.peek() // 3
const item3 = priorityQueue.peek() // 3
```

### `size`(): [Number][]

返回队列长度

**returns** [Number][]: 队列长度

```javascript
priorityQueue.enqueue(1)
priorityQueue.enqueue(2)
priorityQueue.enqueue(3)

const size = priorityQueue.size() // 3
```

### `isEmpty`(): [Boolean][]

判断队列是否为空。

**returns** [Boolean][]: `true` 代表队列为空, `false` 代表非空。

```javascript
const empty1 = priorityQueue.isEmpty() // true

priorityQueue.enqueue(1)
const empty2 = priorityQueue.isEmpty() // false
```

### `toArray`(): `any`

以数组形式返回

**returns** `Array`: 数组

```javascript
// priorityQueue: [12, 3, 5], comparator: default

const arr=priorityQueue.toArray() // [12,3,5]
```

[Function]: https://mdn.io/function
[Number]: https://mdn.io/number
[Boolean]: https://mdn.io/boolean
