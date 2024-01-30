# Основные сведения о техническом задании (ТЗ)

## Зачем нужно техническое задание?

Правильно составленное техническое задание исключает 90% правок (проблем) впоследствии, ускоряя процесс исполнения порученной работы. Разработчик не знает пожелания заказчика, потому требуется более подробно их рассписывать!

## Пример из реальной жизни

❌ **Неправильно**

```markdown
Сходи, купи хлеба
```

_После чего следуют вопросы:_

- _Какой хлеб?_
- _Когда купить?_
- _Где купить?_

✔️ **Правильно**

```markdown
Мне нужен хлеб:

- Купи его сегодня до 19:00.
- Мне нужен хлеб из пекарни около дома.
  Если нет, тогда из супермаркета.
- Хлеб должен быть весом от 400 до 500 грамм.
- Он должен быть либо из ржаной муки
  Если нет, тогда из пшеничной муки.
```

_Вопросов больше не остается, а значит:_

- _нет ожидание ответа от разработчика (время исполнения затягивается)_
- _нет необдуманных ответов от заказчика (которые впоследствии часто меняются, из-за чего приходится вносить правки)_

**Это не запрещает вносить правки осознанные правки в дальнейшем! Лишь исключает неопределенность при озвучивании своих пожеланий.**


## Пару нюансов

1. При составлении технического задания желательно использовать форматирование. Это позволяет понимать написанный текст обеим сторонам.  Можете посмотреть его пример в этом документе.
2. Желательно команды логически разделять на группы: модерация, экономика, информативные и т.п.
3. При написании текстов команд, пожалуйста, проверйте грамотность и пунктуацию, включая пробелы (как лишние, так и недостающие).
4. Придерживайтесь одного стиля при написании текста - так пользоавтелям будет гораздо приятнее использовать ваш продукт!
5. Не копируйте точь-в-точь у других. Это нарушает авторские права! Если вы берёте откуда-то идею, привносите в неё что-то свое - будьте более уникальны. 
6. Если техническое задание составляете в первый раз и не понимаете что-то, можете всегда обратиться к разработчику (мы не кусаемся 😈).  


## Пример составления технического значения

1. **Для начала давайте определимся с видом бота:** централизованное или децентрализованное?

**Централизованное управление** - в данном контексте подразумевается как управление владельцем или группой администраторов бота всеми группами, куда добавлен бот.

**Децентрализованное управление** - у каждого чата есть возможность назначать своих администраторов бота, отдельные настройки, собственную экономику (и управление ею).
В целях безопасности, даже у владельца бота отсутствуют права на управление им в определенном чате.


2. **Использование:** приватное или публичное?

**Приватное** - боты могут работать лишь в определенных группах.

**Публичное** - бота может добавить в свою группу любой пользователь.


3. **Администраторы бота:** системные или персонально указанные?

**Системные** - берутся права из прав администратора в самой группе.

**Персонально указанные** - создается собственная иерархия администраторов или особые права на группы команд.

## Пример команды

`[]` - параметр коменды.

`?[]` - необязательные параметры команды.

`{}` - значение, которое впоследствии заменяется.

### **Блокировка пользователя**

**Доступ к команде:**

- Только в основной группе
- Только старшими администраторами

**Использование команды**

**Внимание!** Сначала указываются обзательные параметры, а потом необязательные.

По идентификатору (ID), упоминанию или текстовому упоминанию (когда отсутствует имя пользователя)

```markdown
/ban [12345 | @KioGia | Kio Gia] ?[время]
?[причина]
```

Ответом на сообщение

```markdown
/ban ?[время]
?[причина]
```

`[12345 | @KioGia | Kio Gia]` - пользователь, которого требуется заблокировать.

`?[причина]` - причина по которой заблокирован пользователь

`?[время]` - время на которое заблокирован пользователь.

- Минуты - 1м или 1m
- Часы - 1ч или 1h
- Дни - 1д или 1d
- Недели - 1н или 1w

По умолчанию если флаг (буква возле числа) не указана, используются дни.

**Текста**

Если время не указано

```markdown
✔️ Администратор {администратор} заблокировал пользователя {пользователь} навсегда
```

Если время указано

```markdown
✔️ Администратор {администратор} заблокировал пользователя {пользователь} на {время}
```

Если причина указана

```markdown
✔️ Администратор {администратор} заблокировал пользователя {пользователь} навсегда
Причина: {причина}
```

Если у пользователя недостаточно прав

```markdown
❌ Для использования команды нужен ранг «старший администратор»!
```

Если это не основная группа

```markdown
❌ Эту команду можно использовать только в основной группе!
```

`{время}` - значение, указанное в параметре `?[время]` при использовании команды.

`{причина}` - значчение, указанное в парамерте `?[причина]` при использовании команды.

`{пользователь}` - участник, которому выдано наказание.

`{администратор}` - администратор, который использовал команду.

