---
layout: uk-UA/default
title: Сприяння Rust &mdash; пошук, сортування та виправлення вад &middot; Мова програмування Rust
---

# Сприяння Rust &mdash; пошук, сортування та виправлення вад

Постійна підтримка проекту обертається навколо 
[системи відслідковування помилок][issue tracker] Rust 
та [запитів на забирання змін][PR], однак завжди потрібно ще більше допомоги. 
Найпростіший шлях почати сприяти Rust - це звернути увагу на помітки [E-easy]
та [E-mentor]. В першу чергу вони передбачають доступність для нових
Rust-програмістів.

При проблемах `E-mentor` досвідчений розробник Rust допомагає в коментарях
щоб провести вас шляхом вирішення проблеми та 
[надіслати запит на забирання змін до GitHub із виправленнями вади][pull]. 
Зв'яжіться із ним щодо проблеми у системі відслідковування помилок,
[згадавши][@mentioning] його ім'я в коментарі, в IRC,
або через email. Зауважте, що розробники Rust отримують багато сповіщень
і їм досить легко деякі із них упустити; не соромтесь полювати на них, чого б
вам це не коштувало!

Інші проекти у Rust підтримують подібні задачі початкового рівня, включаючи веб-браузер [Servo], 
HTTP бібліотеку [hyper], форматтер початкового коду [rustfmt], бібліотечні прив'язки Unix  [nix]
та колекцію підозрілих конструкцій коду [clippy].

У той час як Rust має [обширний набір тестів][test] - завжди є, що потестувати. 
Мітка [E-needstest] вказує на проблеми, які вважаються виправленими, але
не мають тестів. Написання варіантів тестів - чудовий шлях зрозуміти новий проект
і почати допомагати.

Rust завжди потребує людей, які [відсортують][triage] проблеми: відтворять ваду,
мінімізують тестові варіанти, поставлять мітку, закриють вирішені проблеми. 
Зауважте, що вам будуть потрібні підвищені права GitHub для проставляння міток,
але їх легко отримати для будь-кого із невеликим досвідом на проекті. 
Запитайте [представника команди][team].

Після того, як ви знайдете своє місце в проекті і створите декілька
запитів на забирання змін в певній області, розгляньте можливість переглянути 
запити на забирання змін інших учасників: бути хорошим рецензентом - рідкісна майстерність
і завжди високо цінується. Не потрібно попередніх дозволів &mdash; просто почніть конструктивно
та ввічливо коментувати запити на забирання змін, які вас цікавлять. Якщо ви хочете повчитись
проведенню хороших переглядів коду &mdash; [почитайте ці поради][reviews].

<!--
TODO: weekly triage email?
TODO: @nrc says suggesting everybody review w/o training is bad
-->

[@mentioning]: https://github.com/blog/821
[E-easy]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AE-easy
[E-mentor]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AE-easy+label%3AE-mentor
[E-needstest]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AE-needstest
[PR]: https://github.com/rust-lang/rust/pulls
[Servo]: https://github.com/servo/servo
[clippy]: https://github.com/Manishearth/rust-clippy
[hyper]: https://github.com/hyperium/hyper
[issue tracker]: https://github.com/rust-lang/rust/issues
[nix]: https://github.com/nix-rust/nix/
[pull]: https://github.com/rust-lang/rust/blob/master/CONTRIBUTING.md#pull-requests
[reviews]: http://blog.originate.com/blog/2014/09/29/effective-code-reviews/
[rustfmt]: https://github.com/rust-lang-nursery/rustfmt
[team]: team.html
[test]: https://github.com/rust-lang/rust-wiki-backup/blob/master/Note-testsuite.md
[triage]: https://github.com/rust-lang/rust/blob/master/CONTRIBUTING.md#issue-triage
