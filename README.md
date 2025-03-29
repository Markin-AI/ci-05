# Домашнее задание к занятию "`Teamcity`" - `Маркин Алексей`

## Основная часть

1. Создайте новый проект в teamcity на основе fork.
2. Сделайте autodetect конфигурации.

![2](https://github.com/Markin-AI/ci-05/blob/main/img/2.png)

3. Сохраните необходимые шаги, запустите первую сборку master.

![3](https://github.com/Markin-AI/ci-05/blob/main/img/3.png)

4. Поменяйте условия сборки: если сборка по ветке `master`, то должен происходит `mvn clean deploy`, иначе `mvn clean test`.

![4](https://github.com/Markin-AI/ci-05/blob/main/img/4.png)

5. Для deploy будет необходимо загрузить [settings.xml](./teamcity/settings.xml) в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
6. В pom.xml необходимо поменять ссылки на репозиторий и nexus.
7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.

![7](https://github.com/Markin-AI/ci-05/blob/main/img/7-1.png)

![7](https://github.com/Markin-AI/ci-05/blob/main/img/7-2.png)

8. Мигрируйте [`build configuration` в репозиторий](https://github.com/Markin-AI/example-teamcity/blob/master/.teamcity/settings.kts).
9. Создайте отдельную ветку `feature/add_reply` в репозитории.
10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово `hunter`.

```
	public String sayHunterwho() {
    	return "I am hunter!)";
```

11. Дополните тест для нового метода на поиск слова `hunter` в новой реплике.

```
	@Test
	public void welcomerSaysHunterwho() {
    	assertThat(welcomer.sayHunterwho(), containsString("hunter"));
```

12. Сделайте push всех изменений в новую ветку репозитория.
13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.

![13](https://github.com/Markin-AI/ci-05/blob/main/img/13.png)

14. Внесите изменения из произвольной ветки `feature/add_reply` в `master` через `Merge`.
15. Убедитесь, что нет собранного артефакта в сборке по ветке `master`.
16. Настройте конфигурацию так, чтобы она собирала `.jar` в артефакты сборки.

![16](https://github.com/Markin-AI/ci-05/blob/main/img/16.png)

17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.

![17](https://github.com/Markin-AI/ci-05/blob/main/img/17-1.png)

![17](https://github.com/Markin-AI/ci-05/blob/main/img/17-2.png)

18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.
19. В ответе пришлите [ссылку на репозиторий](https://github.com/Markin-AI/example-teamcity).

---