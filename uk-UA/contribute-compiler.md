---
layout: uk-UA/default
title: Сприяння Rust &mdash; мова, компілятор та стандартна бібліотека &middot; Мова програмування Rust
---

# Сприяння Rust &mdash; мова, компілятор та стандартна бібліотека


Сирцевий код компілятора та стандартної бібліотеки знаходяться у
головному репозиторії і тому їх обслуговування та підтримка є основною метою
даного репозиторію, багато міток в системі відслідковування помилок пов'язані із ними. 
Деякі із міток, які часто зустрічаються, включають в себе [A-codegen] - для трансляції
Rust до LLVM IR; [A-debuginfo] - генерація метаданих, що використовуються зневаджувачем;
[A-diagnostics] - для зворотнього зв'язку, що компілятор надає при помилках; [A-libs] -
проблеми із стандартною бібліотекою; [A-macros] та [A-syntaxext]- обоє пов'язані із синтаксичними
розширеннями, а також [A-typesystem] - стосовно теми типів.

Немає належного керівництва по архітектурі компілятора,
але [є невеличкий внутрішній огляд][rustc-guide]. [Документація API
для пакетів, які формують компілятор][internals-docs] може допомогти із навігацією по коду, 
так само як браузер коду [Rust DXR]. [Керівництво по набору тестів Rust][testsuite] 
навчить вас як ефективно користуватись системою побудови Rust,
наподобі того, як запустити [`make tips`][tips] в командному рядку.

На найближче майбутнє однією із найважливіших задач розробки компілятора Rust є перехід
його внутрішньої логіки від оперування безпосередньо AST до роботи із [проміжним представленням, знаним як MIR][mir]. 
Очікується, що ця робота відкриє багато нових можливостей завдяки спрощенню
компілятора і допоможе, для прикладу, створити, базований на MIR, етап трансляції,
додати, базовані на MIR, оптимізації і реалізувати
інкрементальну компіляцію. Ще немає єдиного джерела інформації по роботі, яку стосовно цього
слід виконати, однак скерувати вас в правильному напрямку зможуть на [internals.rust-lang.org] або
[#rust-internals].

[Дуже неприємно, коли компілятор виходить з ладу][ice] &mdash; страшна 'internal compiler error' (ICE). Мітка [I-ICE]
слідкує за подібними речами і їх часто є досить багато. Подібні речі часто є
хорошими помилками, щоб почати із них, тому що легко визначити, коли ви їх виправили
і вони часто є відносно самодостатніми.

Продуктивність коду Rust є однією з його великих переваг, з іншого боку - продуктивність
компілятора Rust є однією з його великих слабкостей. Будь-які поліпшення в середовищі виконання
або &mdash; особливо &mdash; часу компіляції - широко вітаються. 
Мітки [I-slow] та [A-optimization] стосуються продуктивності середовища виконання, а [I-compiletime] - часу компіляції.
У нас є [сайт, який відстежує продуктивність часу компіляції][rustc-perf] на множині робочих навантажень.
Прапорець компілятора `-Z time-passes` може допомогти відслідкувати продуктивність компілятора,
і код Rust можна відпрофілювати зі стандартним профайлером, як то `perf` на Linux.

Значні нові функції проходять через процес [заявок на обговорення (RFC)][rfc],
за яким узгоджується їх дизайн. Хоча цей процес відкритий для всіх, однак
це соціальна співпраця між розробниками, які часто мають різний досвід співпраці, тому
пропонуємо долучатись повільно &mdash; подання поспішної RFC без розуміння історичного, технічного
чи соціального контексту - простий шлях сформувати погане враження і піти розчарованим.
Читайте прикріплений readme файл, щоб краще зрозуміти як це все працює. Багато ідей було обговорено
за історію Rust, деякі відкинуто, деякі відкладено на майбутнє, а [система відслідковування помилок][rfc-issues] RFC
каталогізує деякі бажані ідеї які ще мають потрапити в мову. Незадовго до прийняття RFC в реалізацію вона потрапляє у
'період фінальних коментарів', що позначається [міткою final-comment-period
у rust-lang/rfcs репозиторії][rfc-fcp]. Аналогічно, перед тим, як функцію буде активовано
в стабільному компіляторі (називається 'відправка') вона переходить у [final-comment-period у rust-lang/rust
репозиторії][issue-fcp]. Обидва FCP є критичними моментами, щоб долучитись до участі
і висловити свою думку щодо напрямку розвитку мови, про що повідомляється у щотижневих
звітах підкоманд [internals.rust-lang.org].

Зустрічайтесь із іншими розробниками компілятора Rust у [#rustc], архітекторами мови - у [#rust-lang] і архітекторами бібліотеки - у [#rust-libs].

<!--
TODO: guide to compile-time benchmarking
TODO: using the triage bot?
TODO: some of this RFC description could probably go in the RFC readme
-->


[#rust-internals]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-internals
[#rust-lang]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-lang
[#rust-libs]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust-libs
[#rustc]: https://client00.chat.mibbit.com/?server=irc.mozilla.org&channel=%23rustc
[A-codegen]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-codegen
[A-debuginfo]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-debuginfo
[A-diagnostics]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-diagnostics
[A-libs]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-libs
[A-macros]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-macros
[A-optimization]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-optimization
[A-syntaxext]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-syntaxext
[A-typesystem]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AA-typesystem
[I-ICE]: https://github.com/rust-lang/rust/labels/I-ICE
[I-compiletime]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AI-compiletime
[I-slow]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AI-slow
[Rust DXR]: https://dxr.mozilla.org/rust/source/src
[ice]: https://users.rust-lang.org/t/glacier-a-big-ol-pile-of-ice/3380
[internals-docs]: https://manishearth.github.io/rust-internals-docs
[internals.rust-lang.org]: https://internals.rust-lang.org/
[issue-fcp]: https://github.com/rust-lang/rust/issues?q=is%3Aopen+is%3Aissue+label%3AB-unstable+label%3Afinal-comment-period
[mir]: https://github.com/rust-lang/rust/issues/27840
[rfc-fcp]: https://github.com/rust-lang/rfcs/pulls?q=is%3Aopen+is%3Apr+label%3Afinal-comment-period
[rfc-issues]: https://github.com/rust-lang/rfcs/issues
[rfc]: https://github.com/rust-lang/rfcs#table-of-contents
[rustc-guide]: https://github.com/rust-lang/rust/blob/master/src/librustc/README.md
[rustc-perf]: http://ncameron.org/perf-rustc/
[testsuite]: https://github.com/rust-lang/rust-wiki-backup/blob/master/Note-testsuite.md
[tips]: https://github.com/rust-lang/rust/blob/3d1f3c9d389d46607ae28c51cc94c1f43d65f3f9/Makefile.in#L48
