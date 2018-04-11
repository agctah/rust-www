---
layout: uk-UA/default
title: Долучитись до Rust &mdash; інструменти, IDE та інфраструктура &middot; Мова програмування Rust
---

# Долучитись до Rust &mdash; інструменти, IDE та інфраструктура

Інструменти відіграють значну роль для успіху мови і ще потрібно зробити багато роботи.
 ***Основна увага у розробці Rust насьогодні - це [покращення умов роботи в IDE][ides]***. 
Це включає в себе роботу всього стеку Rust - від компілятора до вашої улюбленої IDE. 
Прослідуйте за лінком для більш детальної інформації.

Cargo (пакетний менеджер Rust) та rustdoc (генератор документації Rust) -
мають повний набір можливостей та повністю функціонують, однак страждають від браку розробників.
У Rustdoc є багато відкритих проблем в основному репозиторії із позначкою [A-rustdoc].
Вони здебільшого є помилками і сприяння полягає у виправленні цих помилок та надсиланні запитів на забирання
змін. Cargo має [свій власний репозиторій та систему відслідковування помилок][Cargo], тому
ті, хто бажає долучитись, можливо захочуть представитись у [#cargo].

Хоча Rust може бути успішно запущеною під обома зневаджувачами (gdb та lldb),
залишається багато випадків, коли зневадження не працює так, як очікується.
Помилки [A-debuginfo] відслідковують ці речі.

З приводу ідей для низки інструментів, до яких можна долучитись, дивіться
[awesome-rust].

Часто інші цікаві проекти інструментів очікують на своїх людей, які б
втілили їх у життя. Обговоріть це із іншими ентузіастами Rust у [#rust-tools].

[#cargo]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rustc
[#rust-tools]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-tools
[A-debuginfo]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-debuginfo
[A-rustdoc]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-rustdoc
[Cargo]: https://github.com/rust-lang/cargo/issues
[awesome-rust]: https://github.com/kud1ing/awesome-rust
[ides]: https://forge.rust-lang.org/ides.html
