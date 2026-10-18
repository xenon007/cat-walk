<div align="center">

![cat_walk](assets/cat_walk.gif)

# Cat Walk

**Небольшая коллекция плагинов для [Hermes Agent](https://hermes-agent.nousresearch.com/docs/).**

[![Hermes](https://img.shields.io/badge/Hermes-%E2%89%A50.22-blue)](https://hermes-agent.nousresearch.com/docs/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

<sub>**Русский** · [English](README.en.md)</sub>

</div>

---

## Плагины

| Плагин | Что решает | Статус |
|---|---|---|
| [**provider-proxy**](https://github.com/xenon007/hermes-plugin-provider-proxy) | Маршрутизация HTTP-прокси по целям для LLM-трафика. `api.openai.com`, `api.deepseek.com` — через прокси, а `api.awesome-corporation.corp` — напрямую, в одном процессе. Для закрытых сетей, где наружу можно только через прокси. | v1.0.0 · [тесты 75/75](https://github.com/xenon007/hermes-plugin-provider-proxy#тестирование) |

Будет пополняться. Критерий попадания в коллекцию: реальная задача, тесты,
которые её доказывают, и честный раздел об ограничениях.

## Почему «Cat Walk»

Из-за кота в самом верху этой страницы. Это первое, что пришло в голову, когда
первому плагину понадобился дом — и название прижилось. Кот не занимается
маршрутизацией трафика. Кот просто идёт.

## Установка плагина

Все плагины коллекции ставятся одинаково — запись в каталоге не нужна:

```bash
hermes plugins install xenon007/hermes-plugin-provider-proxy
hermes plugins enable provider-proxy
```

После этого перезапустите Hermes. README каждого плагина описывает свою
настройку и — что важнее — свои ограничения. Прочитайте этот раздел до
развёртывания в сети, которая вам важна.

## Структура репозитория

```
cat-walk/
├── assets/          общие медиа, на которые ссылаются README плагинов
├── README.md        этот файл (русский)
├── README.en.md     английская версия
└── LICENSE
```

Медиа лежат здесь, а не внутри репозиториев плагинов, намеренно:
`hermes plugins install` выполняет `git clone`, и тащить гифку на 2 МБ в каждую
установку было бы по меньшей мере невежливо. README плагинов ссылаются на эти
файлы по абсолютному raw-URL:

```markdown
![cat_walk](https://raw.githubusercontent.com/xenon007/cat-walk/main/assets/cat_walk.gif)
```

Путь абсолютный, а не относительный: относительный разрешается относительно
репозитория плагина, а не этого, и дал бы 404. Ссылка, указывающая сюда, заодно
сохраняет корректный рендеринг README в форках плагинов.

## Лицензия

MIT — см. [LICENSE](LICENSE).
