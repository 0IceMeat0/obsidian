Нужен для того, чтобы реакт отрисовывал лучше. 
React использует key, чтобы эффективно сравнивать элементы при обновление. И конечно не стоит делать ключи из индексов элементов, потому что при изменение последовательности(удаление, перемещение) индекс будет меняться, а условия key, что он всегда постоянный.

Поэтому key помогает более эффективно делать рендеринг и перерисовывать не весь список, а определенный объект.