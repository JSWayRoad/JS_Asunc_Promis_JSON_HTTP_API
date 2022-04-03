# JS_Requests_async_JSON

## Promis   

Promise – это специальный объект в JavaScript, который связывает «создающий» и «потребляющий» коды вместе. В терминах нашей аналогии – это «список для подписки». «Создающий» код может выполняться сколько потребуется, чтобы получить результат, а промис делает результат доступным для кода, который подписан на него, когда результат готов.

![Screenshot_2](https://user-images.githubusercontent.com/66359081/124255595-02b28100-db33-11eb-8030-69814350a2b1.png)  
![Screenshot_1](https://user-images.githubusercontent.com/66359081/124255602-05ad7180-db33-11eb-8d0c-ea0a1f514c34.png)  
![Screenshot_3](https://user-images.githubusercontent.com/66359081/124256234-bf0c4700-db33-11eb-9692-e930ac19119d.png)  
исполнитель выполняет задачу (что-то, что обычно требует времени), затем вызывает resolve или reject, чтобы изменить состояние соответствующего Promise.   

### Потребители: then, catch, finally  

Объект Promise служит связующим звеном между исполнителем («создающим» кодом или «певцом») и функциями-потребителями («фанатами»), которые получат либо результат, либо ошибку. Функции-потребители могут быть зарегистрированы (подписаны) с помощью методов .then, .catch и .finally.    
![Screenshot_4](https://user-images.githubusercontent.com/66359081/124257805-676edb00-db35-11eb-9bb9-952cc7c90a13.png)  

Вызов .catch(f) – это сокращённый, «укороченный» вариант .then(null, f).
```
function loadScript(src) {
  return new Promise(function(resolve, reject) {
    let script = document.createElement('script');
    script.src = src;

    script.onload = () => resolve(script);
    script.onerror = () => reject(new Error(`Ошибка загрузки скрипта ${src}`));

    document.head.append(script);
  });
}
```

async & await (и обработка ошибок)    
https://learn.javascript.ru/async-await


## Формат JSON, метод toJSON

**JSON (JavaScript Object Notation)** – это  формат представления значений и объектов.  
JavaScript предоставляет методы:  
JSON.stringify для преобразования объектов в JSON.  
Полученная строка json называется JSON-форматированным или сериализованным объектом.  
JSON.parse для преобразования JSON обратно в объект.  

Полный синтаксис JSON.stringify:

let json = JSON.stringify(value[, replacer, space])  
value  
Значение для кодирования.  
replacer  
Массив свойств для кодирования или функция соответствия function(key, value).  
space  
Дополнительное пространство (отступы), используемое для форматирования.

JSON – это формат данных, который имеет собственный независимый стандарт и библиотеки для большинства языков программирования.  
JSON поддерживает простые объекты, массивы, строки, числа, логические значения и null.  
JavaScript предоставляет методы JSON.stringify для сериализации в JSON и JSON.parse для чтения из JSON.  
Оба метода поддерживают функции преобразования для интеллектуального чтения/записи.  
Если объект имеет метод toJSON, то он вызывается через JSON.stringify.

## localstorage,sessionstorage,Куки, document.cookie  
 
 https://www.youtube.com/watch?v=nyIpDs2DJ_c
 
## HTTP - это 
 
 https://developer.mozilla.org/ru/docs/Web/HTTP/Overview  
 https://habr.com/ru/post/215117/  
 с помощью протокола HTTP — обмен данными между пользовательским приложением, осуществляющим доступ к веб-ресурсам (обычно это веб-браузер) и веб-сервером.  
 https://developer.mozilla.org/ru/docs/Web/HTTP/Methods
 
 
 **Геттеры и сеттеры?**  
https://learn.javascript.ru/property-accessors
свойства-аксессоры (accessor properties). По своей сути это функции, которые используются для присвоения и получения значения, но во внешнем коде они выглядят как обычные свойства объекта.  
Свойства-аксессоры представлены методами: «геттер» – для чтения и «сеттер» – для записи. 


**Какие конструкции осуществляют обработку ошибок в js?**  
Конструкция try..catch  throw  Объект Error  
https://medium.com/webbdev/js-6c7a3c5b4e61

**Что такое синхронное и асинхронное исполнение?**  
Синхронные действия процесса – те, которые выполняются в основном потоке, в рамках одного экземпляра процесса.  
Ключевое отличие синхронного режима: следующее действие начинается только тогда, когда завершено предыдущее.  
Соответственно, пока одно действие не завершено, процесс стоит колом.
Асинхронные действия – те, которые выполняются параллельно основному потоку, либо в том же экземпляре процесса, либо вообще в другом процессе. Ключевое отличие асинхронного режима: параллельное выполнение двух и более ветвей процесса.

**Промисификация - это?**  
Промисификация – это длинное слово для простого преобразования. Мы берём функцию, которая принимает колбэк и меняем её, чтобы она вместо этого возвращала промис.


//75.Map, Set, WeakMap, WeakSet?!!!!!
//75.Map, Set, WeakMap, WeakSet?!!!!!
//75.Map, Set, WeakMap, WeakSet?!!!!!
//75.Map, Set, WeakMap, WeakSet?!!!!!

**Что делает встроенная в js функция eval?**  
https://learn.javascript.ru/eval#:~:text=%D0%92%D1%81%D1%82%D1%80%D0%BE%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F%20%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D1%8F%20eval%20%D0%BF%D0%BE%D0%B7%D0%B2%D0%BE%D0%BB%D1%8F%D0%B5%D1%82%20%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D1%8F%D1%82%D1%8C%20%D1%81%D1%82%D1%80%D0%BE%D0%BA%D1%83%20%D0%BA%D0%BE%D0%B4%D0%B0.&text=%D0%A1%D1%82%D1%80%D0%BE%D0%BA%D0%B0%20%D0%BA%D0%BE%D0%B4%D0%B0%20%D0%BC%D0%BE%D0%B6%D0%B5%D1%82%20%D0%B1%D1%8B%D1%82%D1%8C%20%D0%B1%D0%BE%D0%BB%D1%8C%D1%88%D0%BE%D0%B9,%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B9%2C%20%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5%20%D0%B8%20%D1%82.&text=%D0%A0%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D0%BE%D0%BC%20eval%20%D0%B1%D1%83%D0%B4%D0%B5%D1%82%20%D1%80%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%20%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F%20%D0%BF%D0%BE%D1%81%D0%BB%D0%B5%D0%B4%D0%BD%D0%B5%D0%B9%20%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8.   

Функция Eval получает строковый аргумент и интерпретирует содержимое строки так, словно это реальный код в тек. точке программы и позволяет изм. лексическуб обл. видимости на стадии выполнения.
В режиме strict она не изменяет внеш.обл.вид.
 
