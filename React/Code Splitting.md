Это подход как lazy loading, то есть реакт загружает только то что видит пользователь
Хороший видос - https://www.youtube.com/watch?v=-4fyyyQjsz8

Как же он выглядит 
Код без Code Splitting![[Pasted image 20240222124942.png]]

Код без с Code Splitting
![[Pasted image 20240222124903.png]]

У нас есть явные изменения, это то, что мы делаем import через lazy, а после добавляем Suspense, который в то время когда наш код рендерит страницу вставляет что-то другое.

А так все как в html - loading='lazy'