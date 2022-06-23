# Базовый Javascript. Структуры данных

#### Предварительные шаги

1. Перейдите в папку `basic-js-ds`
2. Вбейте в командную строку [`npm install`](https://docs.npmjs.com/cli/install) для установки зависимостей
3. Выполните `npm run test` в командой строке.
4. Вы увидите число ожидающих (pending), проходящих и падающих тестов. 100% проходящие тесты сооветствуют максимальному баллу за задание.

---

#### Внимание!

1. Рекомендуется использовать 14.x.x LTS версию Node.js. Если вы используете фичи, которые не поддерживаются 14 версией, могут быть проблемы с автопроверкой задания.
2. Перед отправкой результата убедитесь, что каждый ваш тест проходит не более чем за 30 секунд.

---

## Общее описание задачи

Ваша задача — разобраться с несколькими структурами данных, чтобы решить подзадачи. Описания подзадач, а также инструкции по запуску тестов и отправке решений находятся ниже.

---

### **Бинарное дерево поиска**

![Binary search tree](https://www.tutorialspoint.com/data_structures_algorithms/images/binary_search_tree.jpg)  
**Бинарное дерево** — это иерархическая **структура данных**, в которой каждый **узел** имеет **значение** (оно же является в данном случае и ключом) и **ссылки** на **левого** и **правого** **потомка**. **Узел**, находящийся на самом верхнем уровне (не являющийся чьим либо потомком) называется **корнем**. **Узлы**, не имеющие потомков, называются **листьями**.

**Бинарное дерево поиска** — это **бинарное дерево**, обладающее дополнительными свойствами: значение **левого** потомка **меньше** значения родителя, а значение **правого** потомка **больше** значения родителя для каждого **узла** дерева. То есть, данные в бинарном дереве поиска хранятся в отсортированном виде. При каждой операции **вставки** нового или **удаления** существующего узла отсортированный порядок дерева сохраняется. При **поиске** элемента сравнивается искомое значение с корнем. Если искомое **больше** корня, то поиск продолжается в **правом** потомке корня, если **меньше**, то в **левом**, если **равно**, то значение **найдено** и поиск прекращается.

Ваша задача — реализовать класс `BinarySearchTree`.
Каждый экземпляр `BinarySearchTree` должен обладать следующими методами:

- `root` — возвращает **корневой узел** дерева
- `add(data)` — добавляет **узел** с `data` к дереву
- `has(data)` — возвращает `true`, если **узел** с `data` имеется в дереве и `false`, если нет
- `find(data)` — возвращает **узел** с `data`, если **узел** с `data` имеется в дереве и `null`, если нет
- `remove(data)` — удаляет **узел** с `data` из дерева, если **узел** с `data` имеется в дереве
- `min` — возвращает **минимальное** **значение**, хранящееся в дереве (или `null`, если у дерева нет **узлов**)
- `max` — возвращает **максимальное** **значение**, хранящееся в дереве (или `null`, если у дерева нет **узлов**)

Например:

`const tree = new BinarySearchTree();`

`tree.add(1);`

`tree.add(2);`

`tree.add(3);`

`tree.add(4);`

`tree.add(5);`

`tree.root().data` => `1;`

`tree.min()` => `1`

`tree.max()` => `5`

`tree.remove(5);`

`tree.has(5)` => `false`

`tree.max()` => `4`

Напишите свой код в `src/binary-search-tree.js`.

---

### **Удалить из списка**

Дан **односвязный связный список** целых чисел (`l`) и целое число (`k`), удалите все элементы из списка `l`, содержащие значение `k`.

Например, для `l` = `[3, 1, 2, 3, 4, 5]` и `k` = `3`,
результат будет `[1, 2, 4, 5]`

Узлы односвязного связного списка определяются интерфейсом:

```js
class ListNode {
  constructor(x) {
    this.value = x;
    this.next = null;
  }
}
```

Напишите свой код в `src/remove-from-list.js`.

---

### **Стек**

Реализуйте **стек** с заданным интерфейсом на основе **массива**.

Например:

```js
const stack = new Stack();

stack.push(1); // добавляет элемент в стек
stack.peek(); // возвращает верхний элемент, но не удаляет его, возвращает 1
stack.pop(); // возвращает верхний элемент и удаляет его, возвращает 1
stack.pop(); // undefined
```

Напишите свой код в `src/stack.js`.

---

### **Очередь**

Реализуйте **очередь** с заданным интерфейсом на основе **связного списка** (используйте `ListNode`, расположенный в папке `extensions`).
Каждый экземпляр очереди должен иметь 3 метода:
_ `enqueue(value)` — помещает `value` в конец **очереди**
_ `deque` — извлекает значение с начала **очереди** и удаляет его \* `getUnderlyingList` - возвращает **связный список**, лежащий в основе данной **очереди**

Например:

```js
const queue = new Queue();

queue.enqueue(1); // добавляет элемент в очередь
queue.enqueue(3); // добавляет элемент в очередь
queue.dequeue(); // возвращает элемент из начала очереди и удаляет его, возвращает 1
queue.getUnderlyingList(); // возвращает { value: 3, next: null }
```

Напишите свой код в `src/queue.js`.
