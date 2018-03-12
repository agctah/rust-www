---
layout: uk-UA/default
title: Команда Rust &middot; Мова Програмування Rust
extra_css:
  - team.css

localized-teams:
  Core team:
    name: Основна команда
    responsibility: "загальний напрямок розвитку проекту, керування підкомандами, наскрізна відповідальність"
  Language team:
    name: Команда мови
    responsibility: "дизайн нових можливостей мови"
  Language team shepherds:
    name: Пастори команди мови
    responsibility: "допомагає просувати заявки RFC до завершення, допомагаючи тим самим команді мови в їх роботі"
  Library team:
    name: Команда бібліотеки
    responsibility: "стандартна бібліотека Rust, основні пакети та стандарти організації коду"
  Compiler team:
    name: Команда компілятора
    responsibility: "внутрішня будова компілятора та його оптимізація"
  Dev tools team:
    name: Команда інструментів розробника
    responsibility: "інструменти роботи із кодом Rust"
  Dev tools peers:
    name: Побратими інструментів розробника
    responsibility: "моніторинг конкретних інструментів Rust і координація з командою інструментів розробника"
  Cargo team:
    name: Команда Cargo
    responsibility: "дизайн та реалізація Cargo"
  Release team:
    name: Команда релізу
    responsibility: "відстеження регресії, стабілізація та випуск релізів Rust"
  Documentation peers:
    name: Побратими документації
    responsibility: "моніторинг конкретної документації та координація з командою документації"
  Style team:
    name: Команда стилю
    responsibility: "тимчасова 'ударна група' яка покликана приймати рішення щодо правил оформленя коду та налаштування Rustfmt (процес специфіковано у <a href='https://github.com/rust-lang/rfcs/blob/master/text/1607-style-rfcs.md'>RFC 1607</a>)"
  Infrastructure team:
    name: Команда інфраструктури
    responsibility: "інфраструктура, на якій тримається сам проект: CI, побудова релізів, боти, метрики"
  Community team:
    name: Команда спільноти
    responsibility: "координація зустрічей, зв'язки з громадськістю, комерційні користувачі, навчальні матеріали та реклама"
  Documentation team:
    name: Команда документації
    responsibility: "стежить за тим, щоб Rust мала чудову документацію"
  Moderation team:
    name: Команда модераторів
    responsibility: "дотримання <a href='https://www.rust-lang.org/conduct.html'>кодексу поведінки</a>"
  Rust team alumni:
    name: Випускники команди Rust
    responsibility: "б'ють байдики на пенсії"
---

# Команда Rust

Проект Rust [регулюється](https://github.com/rust-lang/rfcs/blob/master/text/1068-rust-governance.md)
рядом команд, кожна з яких має свою зону відповідальності. Нижче наведено списки
в алфавітному порядку.

Щоб зв'язатись із командою, залиште своє запитання чи коментар у [групі розробки](https://internals.rust-lang.org/)
і позначте міткою категорії, що відповідає назві команди. Майте на увазі, що розкриття безпеки має відповідати
[процесу розкриття безпеки Rust](security.html). 

{% for team in site.data.team.teams %}
<section id="{{ team.name | replace:' ','-' }}">
<h2> {{ page.localized-teams[team.name].name | default: team.name }} </h2>

<strong>Відповідальність</strong>: <em>{{ page.localized-teams[team.name].responsibility | default: team.responsibility }}</em>

<br />

{% if team.email %}
  <strong>Контакт</strong>:
  <a href="mailto:{{ team.email | uri_escape }}">{{ team.email }}</a>
{% endif %}

<ul class="headshots">
{% for nick in team.members %}
  {% assign person = site.data.team.people[nick] %}
  {% if person.site %}
    {% assign sitename = person.site %}
  {% else %}
    {% assign sitename = "github" %}
  {% endif %}
  {% assign website = site.data.team.sites[sitename] %}
  <li class="person {% if team.lead and team.lead == nick %}lead{% endif %}">
  <a href="{{ website.url | replace:'%nick',nick }}">
    <div class="name">{{ person.name }}</div>
    <div class="details">
      <div>irc: {% if person.irc %}{{ person.irc }}{% else %}{{ nick }}{% endif %}</div>
      {% if person.ex-teams %}
      <div>teams: {% for ex-team in person.ex-teams %}{% if forloop.first == false %}, {% endif %}{{ page.localized-ex-teams[ex-team] | default: ex-team }}{% endfor %}</div>
      {% endif %}
    </div>
    <img class="headshot" src="{{ website.avatar | replace:'%nick',nick }}" alt="{{ person.name }}">
  </a>
</li>
{% endfor %}
</ul>
</section>
{% endfor %}
