# Структура курса

Авторы курса поставили перед собой амбициозную цель — создать материал, подходящий каждому, не зависимо от уровня его начальных знаний и конечной цели. Со стандартным «книжным» или «лекционным» подходом сделать это сложнее. Необходимо более динамическое решение, учитывающее возможности современных технологий.

Поэтому было решено разметить весь обучающий материал специальными измерениями, помогающими оценить подаваемую информацию с различных сторон. Измерения могут описать произвольные части материала, целый модуль или подмодуль. Далее, зная начальную точку обучения и конечную цель ученика, с учётом выбранных измерений (глубины проработки, технологий, времени обучения и т.д.), мы можем построить персональный путь в графе всех модулей для освоения выбранных специализаций.

## Методологическая структура курса

Методологическая структура курса представляет собой ориентированный ациклический граф. Его вершинами являются модули курса (с набором тем), а рёбрами — дороги, которые необходимо пройти для освоения этих тем. В этом графе отсутствуют направленные циклы. Т.е. для освоения двух любых модулей вам никогда не потребуется обязательное знание из парного модуля. Но могут быть «параллельные» пути, выходящие из одного начального модуля и разными дорогами приходящие в один конечный модуль.

> :basecamp: TODO: Нарисовать граф в виде roadmap, например как у [Nick Chapsas](https://www.youtube.com/watch?v=1oeMTz7LwrU)

Цель прохождения курса определяет путь, который необходимо будет освоить. Путь состоит из модулей и связей между ними. Он помогает вам добраться от начальной точки знаний, до конечной цели, с учётом ваших требований к материалам.

Примеры путей:
- Автоматизированное тестирование
- Консольные приложения
- Микросервисы
- Настольные (desktop) приложения
- Мобильные приложения

Курс может изменяться со времением. Ибо появляются новые материалы, меняются подходы, устаревают технологии. Поэтому курс планируется постоянно обновлять и держать в актуальном состоянии.

Любую тему можно раскрыть тысячами разных статей и лекций. Экспертный комитет отвечает за то, чтобы в курс попадали оптимальные по качеству и понятности материалы. Именно на основании его мнения и формируется содержимое всех модулей.

## Физическая структура курса

Курс состоит из трёх блоков:

1. [Методология](https://github.com/EduWebDotNet/methodology/wiki) — в нём собраны материалы, помогающие осознать принципы работы с курсом. Этот блок нужен для авторов курса.
2. [Теория](https://edudotnet.gitbook.io/edu-dot-net) — набор модулей, состоящих из теоретических материалов.
3. [Практика](https://github.com/EduWebDotNet/hands-on-personal) — программный код, необходимый для закрепления практических навыков.

### Репозиторий с теорией

Весь теоретический материл должен быть размечен измерениями. Они являются основой для построения индивидуальных путей обучения.

Основой репозитория являются модули. Каждый модуль представляет собой отдельную директорию.

> :basecamp: TODO: Определиться со способом именования и упорядочивания директорий после [METH-6](https://github.com/EduWebDotNet/methodology/issues/6)

Директория состоит из набора [markdown](https://ru.wikipedia.org/wiki/Markdown) файлов с расширением `md`. Они не предназначены для просмотра матерала курса напрямую, но мы стараемся поддерживатьих в читабельном формате.

> :basecamp: TODO: Определиться со способом именования и упорядочивания файлов после [METH-6](https://github.com/EduWebDotNet/methodology/issues/6)

> :basecamp: TODO: Определиться с кодировкой и BOM заголовком после [METH-6](https://github.com/EduWebDotNet/methodology/issues/6)

#### Метаданные

Для построения индивидуального пути изучения курса, мы используем разметку всего материала с помощью измерений. Измерения бывают двух типов: встраиваемые (inline) и блочные (не встраиваемые). Подробнее о всех поддерживаемых измерениях можно почитать в [[отдельной статье|Dimensions]].

Измерения первого типа могут быть встроены в любую часть текста модуля. Таким образом мы обогащаем содержимое метаинформацией об измерении. Для примера можно посмотреть на [[demoji разметку|Dimoji]].

Блочными измерениями можно разметить только весь подмодуль целиком. Это одна из причин выделения подмодуля из цельного модуля. Блочная метаинформация актуальна только в рамках размеченного подмодуля. Подмодуль, следующий за размеченным, начинает с чистого листа измерений и должен быть размечен заново. Это необходимо для того чтобы иметь возможность менять подмодули местами.

#### Подмодуль

Каждый физический markdown файл в папке модуля является подмодулем. В начале содержимого каждого файла может быть указан блок с метаинформацией (ключ-значение) об этом подмодуле. Этот блок оформляется по [стандарту frontmatter YAML](https://jekyllrb.com/docs/front-matter/).

Разбиение модуля на подмодули необходимо, если какую-то часть учебного материала требуется разметить блочными измерениями. Для подобной разметки следует применять латинские названия измерений и их значения. С соблюдением регистра символов (обычно это PascalCase).

Пример разметки файла подмодуля с помощью frontmatter YAML:

```markdown
---
Subject: DevOps
Tool: Kubernetes
---
Давайте поговорим о **несуществующих** профессиях и их игрушках.
```

#### Модуль

Материал модуля собирается из всех markdown файлов (подмодулей) в папке модуля с учётом метаинформации. Получившийся текст размечен специальными служебными тегами — [[Dimoji|Dimoji]]. С помощью этих тегов мы можем определять измерения для более мелких блоков текста. И, в зависимости от выбранного пути, удалять или оставлять необходимые блоки. Таким образом полный текст модуля урезается под нужды конкретных требований. После обработки dimoji-препроцессором, специальные теги удаляются, а выходной документ остаётся с валидным markdown форматом.

### Пример

Рассмотри для примера 3 модуля, содержащие материал различного уровня сложности.

```mermaid
block-beta
columns 5

  block:W
    columns 1
    TW(["Путь"])
    W01(("Войти в IT"))
    W02(("Хочу\nсвой VK"))
    W03(("Нужны\nтестировщики"))
  end

  block:M1
    columns 1
    T1(["Модуль:\nОсновы C#"])
    M11["Начальный"]
    M12["Средний"]
    M13["Продвинутый"]
  end
  block:M2
    columns 1
    T2(["Модуль:\nТестирование"])
    M21["Начальный"]
    M22["Средний"]
    M23["Продвинутый"]
  end
  block:M3
    columns 1
    T3(["Модуль:\nМикросервисы"])
    M31["Начальный"]
    M32["Средний"]
    M33["Продвинутый"]
  end
  block:M4
    columns 1
    T4(["Другие модули\nдля обучения"])
    space
  end

W01 --"1"--> M11
M11 --"1"--> M21
M21 --"1"--> M31

W02 --"2"--> M11
M11 --"2"--> M33

W03 --"3"--> M12
M12 --"3"--> M23

classDef title fill:#fff,stroke:#ccc;
class TW,T1,T2,T3,T4 title
```

1. Если мы хотим быстро вникнуть во все темы, то мы можем выбрать путь, включающий в себя все модули и оставить только материал начального уровня.
2. Если мы хотим быстро построить свой большой сайт, то нам не нужно тратить время на всё лишнее, достаточно начальных знаний языка. А вот в микросервисах придётся стать продвинутым профессионалом.
3. Если нам срочно понадобилось обучить армию продвинутых тестировщиков, то им нужно уверенно владеть языком и быть профессионалами в модуле тестирования.

