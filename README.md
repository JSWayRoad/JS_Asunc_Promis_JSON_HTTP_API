# JS_Requests_async

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
