---
layout: uk-UA/default
title: Долучитись до Rust &mdash; документація &middot; Мова програмування Rust
---

# Долучитись до Rust &mdash; документація

Документація ніколи не буває достатньо хорошою і її ніколи не буває забагато.
Багато аспектів документації Rust не вимагають глибоких знань для того, щоб
покращити, написати, перевірити і відредагувати її, проте це є ефективним шляхом
вивчення Rust. Крім того, місця покращення документації легко визначити і їм кінця-краю немає.
Не подобається, як щось читається? Знайшли інформацію, яка не документована?
З радістю приймемо ваші запити на забирання змін.

***Найбільш вагома документація, яку ви можете написати - [для пакетів, що формують
екосистему Rust][crate_docs]***. В той час, як основна документація відносно завершена,
зовсім інша ситуація із [багатьма пакетами та інструментами][awesome-rust] із якими розробники Rust
мають справу щодня. Написавши документацію до API популярного Rust-проекту,
ви заслужите міцну любов її супроводжуючого.

[Книга][The Book] - основна документація по Rust, що супроводжується в
головному репозиторії. Вона має власну позначку проблем, [A-book], і постійно
вдосконалюється. Інша документація в головному репозиторії включає в себе
[еталонне джерело][The Rust Reference], [документацію API
стандартної бібліотеки][std], [The Rustonomicon] (керівництво з правильного
використання `unsafe`). [Рекомендації по стилю Rust][Rust Style Guidelines] 
настільки неповні, що на них неможливо посилатись; співучасник із значними амбіціями
може досягти в цьому питанні значних успіхів. [Індекс помилок][err] надає розширені пояснення
щодо помилок, які повертаються компілятором. При додаванні нових помилок дану
документацію [слід оновити][err-issue], тому завжди є помилки, які
не відображені в індексі і які потрібно додати. Більшість внутрішньої
документації знаходиться в директорії [src/doc]. Всі вище наведені моменти
позначені мітками [A-docs] в системі відслідковування помилок. Зрештою, цей документ
та інші матеріали веб-сайту супроводжуються у [репозиторії веб-сайту Rust][Rust website Git repository].
Щоб внести вклад &mdash; просто внесіть корективи і надішліть запит на забирання змін.

Велика частина документації Rust не знаходиться в головному репозиторії
або не супроводжується проектом, але при цьому вона, все ж, критично важлива
для успіху Rust. Приклади зразкової документації Rust, що активно розробляється
і потребує сприяння, включають в себе [Rust By Example], [Rust Design Patterns] і [rust-rosetta].
Щоб ознайомитись із іншими проектами документації, до яких можна долучитись, дивіться [rust-learning].

Подивитись іншу документацію Rust можна в [#rust-docs].

<!--
TODO: blogging, translation
-->

[#rust-docs]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-docs
[A-book]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-book
[A-docs]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-docs
[Rust By Example]: https://github.com/rust-lang/rust-by-example
[Rust Design Patterns]: https://github.com/nrc/patterns
[Rust Style Guidelines]: https://doc.rust-lang.org/style/index.html
[The Book]: https://doc.rust-lang.org/book/index.html
[The Rust Reference]: https://doc.rust-lang.org/reference
[The Rustonomicon]: https://doc.rust-lang.org/nomicon/index.html
[awesome-rust]: https://github.com/kud1ing/awesome-rust
[crate_docs]: https://users.rust-lang.org/t/lets-talk-about-ecosystem-documentation/2791
[err-issue]: https://github.com/rust-lang/rust/issues/24407
[err]: https://doc.rust-lang.org/error-index.html
[rust-learning]: https://github.com/ctjhoa/rust-learning
[rust-rosetta]: https://github.com/Hoverbear/rust-rosetta
[src/doc]: https://github.com/rust-lang/rust/tree/master/src/doc
[std]: https://doc.rust-lang.org/std/index.html
[Rust website Git repository]: https://github.com/rust-lang/rust-www
