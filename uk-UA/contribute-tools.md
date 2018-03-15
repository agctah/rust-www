---
layout: uk-UA/default
title: Сприяння Rust &mdash; інструменти, IDE та інфраструктура &middot; Мова програмування Rust
---

# Сприяння Rust &mdash; інструменти, IDE та інфраструктура

Інструменти відіграють значну роль для успіху мови і залишилось ще зробити велику справу.
 ***Основна увага у розробці Rust насьогодні - це [покращення умов роботи в IDE][ides]***. 
Це включає в себе роботу всього стеку Rust - від компілятора до вашої улюбленої IDE. 
Прослідуйте за лінком для більш детальної інформації.

Обоє - Cargo (пакетний менеджер Rust) та rustdoc (генератор документації Rust) -
мають повний набір можливостей та повністю функціонують, однак страждають від браку розробників.
Rustdoc має багато відкритих проблем в основному репозиторії із поміткою [A-rustdoc].
Вони здебільшого є вадами і сприяння полягає у виправленні цих вад та надсиланні запитів на забирання
змін. Cargo має [свій власний репозиторій та систему відслідковування помилок][Cargo], тому
ті, хто зацікавлений у сприянні, можливо захочуть представитись у [#cargo].

Хоча Rust може бути запущеною під обома зневаджувачами (gdb та lldb) із незначним успіхом,
залишається багато випадків, коли зневадження не працює так, як очікується.
Помилки [A-debuginfo] відслідковують ці речі.

З приводу ідей для більшого числа інструментів, яким можна посприяти, дивіться
[awesome-rust].

Часто інші цікаві проекти інструментів очікують на своїх людей, які б
втілили їх у життя. Обговоріть це із іншими ентузіастами Rust в [#rust-tools].

[#cargo]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rustc
[#rust-tools]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-tools
[A-debuginfo]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-debuginfo
[A-rustdoc]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-rustdoc
[Cargo]: https://github.com/rust-lang/cargo/issues
[awesome-rust]: https://github.com/kud1ing/awesome-rust
[ides]: https://forge.rust-lang.org/ides.html
