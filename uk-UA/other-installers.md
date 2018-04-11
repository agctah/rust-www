---
layout: uk-UA/default
title: Інші шляхи встановлення &middot; Мова програмування Rust
---

# Інші шляхи встановлення Rust

- [Який встановлювач вам слід використати?](#which)
- [Інші шляхи встановлення `rustup`](#more-rustup)
- [Автономні встановлювачі](#standalone)
- [Початковий код](#source)

## Який встановлювач вам слід використати?
<span id="which"></span>

Rust працює на багатьох платформах і існує багато способів встановлення Rust. Якщо ви бажаєте встановити Rust
у найпростіший, рекомендований, спосіб - тоді притримуйтесь вказівок на головній [сторінці встановлення][installation page].

Та сторінка описує встановлення через [`rustup`] - інструмент, який впевнено оперує багатьма інструментами розробки 
Rust на всіх платформах, що підтримуються Rust. Чому ж хтось може _не_ захотіти встановлювати відповідно цих вказівок?

- Оффлайн встановлення. `rustup` завантажує компоненти із інтернету за необхідності. 
  Якщо вам потрібно встановити Rust без доступу до інтернету - `rustup` не підходить.
- Надається перевага системному менеджеру пакетів. У Linux зокрема, але також і в
  macOS із [Homebrew] та Windows із [Chocolatey], розробники інколи вважають за краще
  встановити Rust, використовуючи системний менеджер пакетів.
- Небажання використовувати `curl | sh`. У Unix ми зазвичай встановлюємо `rustup` шляхом виконання 
  скрипта командної оболонки через `curl`. Дехто хвилюється з приводу безпеки даного підходу 
  і надає перевагу завантаженню та запуску встановлювача самотужки.
- Перевірка підписів. Хоча `rustup` здійснює завантаження через HTTPS,
  єдиний спосіб перевірки підписів встановлювачів Rust, на сьогоднішній день - це ручний спосіб із автономними встановлювачами.
- Встановлювач із графічним інтерфейсом та інтеграція із "Add/Remove Programs" у
  Windows. `rustup` виконується в консолі і не реєструє своє встановлення на зразок типових Windows-програм.
  Якщо ви надаєте перевагу більш типовому встановленню у Windows із графічним інтерфейсом - у нас є автономний `.msi` встановлювач.
  В майбутньому `rustup` також матиме графічний встановлювач для Windows.
  
Підтримка платформ у Rust визначається [трьома рівнями][three tiers], які тісно пов'язані
із доступними методами встановлення: загалом проект Rust надає бінарні збірки для всіх платформ рівня 1 та рівня 2
і всі вони піддаються встановленню через `rustup`. Деяким платформам рівня 2, все-таки, доступна лише стандартна 
бібліотека, але не сам компілятор; це означає, що вони є лише цілями крос-компіляції; код Rust може виконуватись на таких
платформах, але на них не можна запустити компілятор. Такі цілі можуть бути встановлені завдяки команді `rustup target add`.

## Інші шляхи встановлення `rustup`
<span id="more-rustup"></span>

Шляхи встановлення `rustup` відрізняються для різних платформ:

* Unix - виконайте `curl https://sh.rustup.rs -sSf | sh` в командній оболонці.
  Це призведе до завантаження та запуску [`rustup-init.sh`], який в свою чергу
  завантажить та запустить правильну версію виконуваного файла `rustup-init`
  для вашої платформи.
* Windows - завантажте та запустіть [`rustup-init.exe`].

`rustup-init` можна налаштовувати інтерактивно і всі опції можуть додатково
контролюватись аргументами командного рядка, що можуть бути передані через
скрипт командної оболонки. Передайте `--help` до `rustup-init`, як показано нижче, 
для того, щоб показати аргументи, які приймає `rustup-init`:

```
curl https://sh.rustup.rs -sSf | sh -s -- --help
```

Якщо ви надаєте перевагу варіанту без використання скриптів оболонки - можете
безпосередньо завантажити
`rustup-init` для платформи за вашим вибором:

<div class="rustup-init-table">
  {% for column in site.data.platforms.rustup %}
  <div>
    {% for target in column %}
    {% if target contains 'windows' %}
    <a href="https://static.rust-lang.org/rustup/dist/{{ target }}/rustup-init.exe">
      {{ target }}
    </a>
    {% else %}
    <a href="https://static.rust-lang.org/rustup/dist/{{ target }}/rustup-init">
      {{ target }}
    </a>
    {% endif %}
    {% endfor %}
  </div>
  {% endfor %}
</div>

## Автономні встановлювачі
<span id="standalone"></span>

Офіційні автономні встановлювачі Rust містять один випуск Rust і підходять для
встановлення в оффлайн режимі. Вони можуть бути трьох різних видів: архів tar
(розширення `.tar.gz`), який працює у будь-якому Unix-подібному середовищі, встановлювач Windows
 (`.msi`) і встановлювач Mac (`.pkg`). Ці встановлювачі постачаються із
`rustc`, `cargo`, `rustdoc`, стандартною бібліотекою і стандартною документацією,
 але не надають доступу до додаткових можливостей на відміну від
`rustup`.

Найчастіше причинами їх використання є:

- Оффлайн встановлення
- Надання переваги більш інтегрованому в платформу, графічному встановлювачу Windows

Кожен із цих бінарників підписано [ключем підписування Rust][Rust signing key], який
[доступний на keybase.io][available on keybase.io], інфраструктурою побудови Rust із
[GPG]. Підписи знаходяться у файлах `.asc`, що наведені в таблицях нижче.

Попередні випуски можна знайти в [архіві][the archives].

{% for channel in site.channels %}

### {{ channel.name | capitalize }} ({{ channel.vers }})
<span id="{{ channel.name }}"></span>

<div class="installer-table {{ channel.name }}">
  {% for column in site.data.platforms[channel.name] %}
  <div>
    {% for target in column %}
    <div>
      <span>{{ target }}</span>
      <a href="https://static.rust-lang.org/dist/rust-{{ channel.package }}-{{ target }}.tar.gz">.tar.gz</a>
      <a href="https://static.rust-lang.org/dist/rust-{{ channel.package }}-{{ target }}.tar.gz.asc">.asc</a>
    </div>
    {% if target contains 'windows' %}
    <div>
      <span>{{ target }}</span>
      <a href="https://static.rust-lang.org/dist/rust-{{ channel.package }}-{{ target }}.msi">.msi</a>
      <a href="https://static.rust-lang.org/dist/rust-{{ channel.package }}-{{ target }}.msi.asc">.asc</a>
    </div>
    {% elsif target contains 'darwin' %}
    <div>
      <span>{{ target }}</span>
      <a href="https://static.rust-lang.org/dist/rust-{{ channel.package }}-{{ target }}.pkg">.pkg</a>
      <a href="https://static.rust-lang.org/dist/rust-{{ channel.package }}-{{ target }}.pkg.asc">.asc</a>
    </div>
    {% endif %}
    {% endfor %}
  </div>
  {% endfor %}
</div>

{% endfor %}

## Початковий код
<span id="source"></span>

<div class="installer-table">
  <div>
    <div>
      <span>Стабільний</span>
      <a href="https://static.rust-lang.org/dist/rustc-{{ site.stable }}-src.tar.gz">.tar.gz</a>
      <a href="https://static.rust-lang.org/dist/rustc-{{ site.stable }}-src.tar.gz.asc">.asc</a>
    </div>
  </div>
  <div>
    <div>
      <span>Бета</span>
      <a href="https://static.rust-lang.org/dist/rustc-beta-src.tar.gz">.tar.gz</a>
      <a href="https://static.rust-lang.org/dist/rustc-beta-src.gz.asc">.asc</a>
    </div>
  </div>
  <div>
    <div>
      <span>Нічний</span>
      <a href="https://static.rust-lang.org/dist/rustc-nightly-src.tar.gz">.tar.gz</a>
      <a href="https://static.rust-lang.org/dist/rustc-nightly-src.tar.gz.asc">.asc</a>
    </div>
  </div>
</div>

[installation page]: install.html
[`rustup`]: https://github.com/rust-lang-nursery/rustup.rs
[other-rustup]: https://github.com/rust-lang-nursery/rustup.rs#other-installation-methods
[`rustup-init.exe`]: https://static.rust-lang.org/rustup/dist/i686-pc-windows-gnu/rustup-init.exe
[`rustup-init.sh`]: https://static.rust-lang.org/rustup/rustup-init.sh
[Homebrew]: http://brew.sh/
[Chocolatey]: http://chocolatey.org/
[three tiers]: https://forge.rust-lang.org/platform-support.html
[Rust signing key]: https://static.rust-lang.org/rust-key.gpg.ascii
[GPG]: https://gnupg.org/
[available on keybase.io]: https://keybase.io/rust
[the archives]: https://static.rust-lang.org/dist/index.html
