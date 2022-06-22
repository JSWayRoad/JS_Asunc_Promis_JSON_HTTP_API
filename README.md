**REST**

https://www.techtarget.com/searchapparchitecture/definition/REST-REpresentational-State-Transfer  
https://en.wikipedia.org/wiki/Representational_state_transfer  
https://developer.mozilla.org/en-US/docs/Glossary/REST  

REST (REpresentational State Transfer) is an architectural style for developing web services. 

# JS_Requests_async_JSON

https://blog.logrocket.com/understanding-asynchronous-javascript/

Promis это объект, который красиво организовывает  асинхронный код. Мы подписываемся на асинхронный код

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

**Что такое AJAX?**

https://developer.mozilla.org/en-US/docs/Glossary/AJAX  

https://developer.mozilla.org/en-US/docs/Glossary/XML  
https://developer.mozilla.org/en-US/docs/Glossary/XHR_(XMLHttpRequest)    
https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest
https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API

AJAX (аббревиатура от «Asynchronous Javascript And Xml») – технология обращения к серверу без перезагрузки страницы.  
https://habr.com/ru/post/14246/  
Приложения работают быстрее и становятся более отзывчивыми к действиям пользователей.  


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

JSON — это формат, который хранит структурированную информацию и в основном используется для передачи данных между сервером и клиентом.  
https://learn.javascript.ru/json  

## localstorage,sessionstorage,Куки, document.cookie  
 
 https://www.youtube.com/watch?v=nyIpDs2DJ_c


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

**Чем полезны атрибуты defer и async?**  

ПорядокDOMContentLoaded
asyncПорядок загрузки (кто загрузится первым, тот и сработает).Не имеет значения. Может загрузиться и выполниться до того, как страница полностью загрузится. Такое случается, если скрипты маленькие или хранятся в кеше, а документ достаточно большой.  
deferПорядок документа (как расположены в документе).Выполняется после того, как документ загружен и обработан (ждёт), непосредственно перед DOMContentLoaded.




 
