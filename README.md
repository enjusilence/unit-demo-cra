## Привет, проверяющий!
Небольшая памятка-подсказка чтобы пройтись по всем требованиям.

Адрес сайта на GH Pages: https://enjusilence.github.io/unit-demo-cra

Для падения unit-тестов замени в 'condition.ts' `CONDITION = false`

1. Commitlint

      Настроен локально и в GH Actions. Для проверки локально:

      ```sh
      # установит зависимости
      npm ci
      ```
      Внести любое изменение в проект

      ```sh
      # стейдж
      git add .
      # коммит
      git commit -m "test" # либо любое другое сообщение
      ```
2. Запуск тестов на PR

      При создании PR в любую ветку будет запускаться тестирование каждого коммита линтером и автотестами. Для того чтобы убедиться, что тестируется каждый коммит, можно запушить сначала "плохой" коммит, затем "хороший", и сделать PR - тесты должны упасть.
      От "плохих" PR защищен только `master`.
      Для проверки линтера можно запушить командой
      ```sh
      # отключит локальную проверку
      git push --no-verify
      ```
      Тогда коммит пройдёт, но при PR выдаст ошибку.
3. Релиз

      Релиз можно отвести от любой ветки, для этого нужно добавить соотвествующий тег, это запустит необходимые проверки
      ```sh
      # добавит тег с версией <число>
      git tag -a v<число>
      git push origin v<число>
      ```
      Проверяется только последний коммит, к которому прикреплен тег.
      В любом случае отводится ветка с названием `release-v<число>` и создаётся issue.
      При повторном добавлении тега, либо при любом пуше в одну из релизных веток (в т.ч. cherry pick) проверки для релиза запускаются повторно, issue обновляется.
      В случае прохождения тестов сборка деплоится на GH Pages, релиз появляется в списке релизов, issue закрывается.
