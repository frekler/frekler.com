До классов существовали прототипы
```js
const num = 56
console.log(num.__proto__.__proto__...)
...null
// т.о. все рождается из ничего (null)
// в тоже время и сам null по типу данных - объект (typeof 'object')
```

# Принципы ООП:

## Наследование
Это механизм базирования объекта, class на другом объекте (наследование на основе прототипа) или class (наследование на основе класса).
Когда не нужно писать одни и те же свойства в разных классах

## Полиморфизм
Полиморфизм -  может быть достигнут в том, что у каждого класса есть своя функция, которая (при вызове) выполняется корректно для любого объекта.
Основная идея заключается в способности вызывать один и тот же метод для разных объектов, и при этом каждый объект будет реагировать по-своему.

## Инкапсуляция
Инкапсуляция — это объединение данных и методов, которые воздействуют на эти данные, так что доступ к этим данным ограничен извне, «инкапсуляция — это локальное хранение и защита и скрытие процесса состояния». В ООП это означает, что объект хранит свое состояние в приватном порядке, и только методы объекта имеют доступ для его изменения.
Инкапсуляция включает в себя идею о том, что данные объекта не должны быть напрямую доступны. Нужно вызывать методы вместо прямого доступа к данным. Это защита (некое экранирование).

```js
class Person {
    #bonus = 10;

    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    get myBonus() {
        console.log(`My bonus ${this.#bonus}`)
    }
}

const bob = new Person('Bob', 33)

bob.#bonus // Error
bob.myBonus // 10
```

## Абстракция

Абстракция в объектно-ориентированное программировании - это использование только тех характеристик объекта, которые с достаточной точностью представляют его в данной системе.
Мы создаем некий чертеж-шаблон, и он абстрактный, не конкретный.
В момент создания экземпляра класса мы наполняем все поля смыслом. А до этого - полная абстракция.
