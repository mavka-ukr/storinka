# Сторінка

Реакт, але українською.

## Використання

```мавка
взяти "хмарний.пак.укр/сторінка/0.0.1"
взяти "хмарний.пак.укр/стан/0.0.3"

стан = Стан(дані=(рахунок=1))

дія зменшити_рахунок()
  стан["рахунок"] -= 1
кінець

дія збільшити_рахунок()
  стан["рахунок"] += 1
кінець

модуль інтерфейс
  дія кнопка(назва текст, події словник) словник
    сторінка.створити_елемент(
      "button", 
      (
        class="bg-blue-500 hover:bg-blue-700 active:bg-blue-800 text-white font-bold py-2 px-4 rounded",
        події=події
      ),
      назва
    )
  кінець

  дати кнопка
кінець

дія відмалювати()
  сторінка.показати([
    інтерфейс.кнопка(назва="-1", події=(клік=зменшити_рахунок)),
    стан["рахунок"],
    інтерфейс.кнопка(назва="+1", події=(клік=збільшити_рахунок))
  ])
кінець

стан.слухати(відмалювати)

відмалювати()

показати_вітрину()
```