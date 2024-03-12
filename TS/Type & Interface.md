### Interface
Можно только с объектами (где мы указываем ключ: значение, а также function с помощью стрелочных функций)

Связан с ООП отличие от type

 Присутствует расширение(extends) и (implements) -
 - Extends - Это когда мы можем брать свойства у другого интерфейса для расширение своего

```
interface Animal {
    name: string;
}

interface Dog extends Animal {
    bark: () => void;
}

--------------------------------------
const dog: Dog = {
    name: 'Бобик',
    bark: () => console.log('Гав')
}
```
 - implements - это когда нужно передать нашему классу требования, какие он должен иметь типы 
 ```
interface Human {
    name: string;
}

class Woman implements Human {
    sex: string = 'woman';
    name: string;
    
    constructor(name: string) {
        this.name = name;
    }
}
```

### Type
Можно использовать с любыми типами данных 