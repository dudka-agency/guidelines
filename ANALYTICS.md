# ANALYTICS

## References
* Google Analytics - https://analytics.google.com/ (просмотры страниц, события, итд)

* Google Tag Manager - https://tagmanager.google.com/ (единый код для подключения других скриптов, той же гугл аналитики. Необходимо настраивать триггеры, теги, переменные итд)

* Google Search Console - https://search.google.com/ (ошибки, ссылочная масса, топ запросы)

## Events

`category` - "Button", "Contact Form"

`action` - "click", "send"

`label` - "Phone", "Link"

### Если на сайте установлен - "Global site tag (gtag.js)"
gtag('event', 'action', {'event_category': 'category', 'event_label': 'label'});

### Если на сайте установлен - "Google Tag Manager"
dataLayer.push({'event': 'category', 'analytics_action': 'action', 'analytics_label': 'label'});

После этого в GTM необходимо создать переменные analytics_action и analytics_label и добавить событие ButtonReservation для отправки его в GA

### Если на сайте установлен - "analytics.js" (старый вариант, надо обновлять)
ga('send', {hitType: 'event', 'category': 'Videos', eventAction: 'action', eventLabel: 'label'});

### Facebook pixel event
fbq('track', 'Purchase', {value: 25, currency: 'USD'});

## UTM метки (отслеживаение рекламных компаний, баннеров итд)
Удобный генератор https://tilda.cc/ru/utm/

`utm_source` - Источник, с которого отправляется трафик: "google", "facebook", "landing covid"

`utm_medium` - Рекламная модель: "cpc", "qr-code", "email"

`utm_campaign` - Название конкретной компании: "booklet", "promo", "sale"

Пример
https://www.publicspendforum.net/landing-govairs/?utm_source=landing-govairs&utm_medium=qr-code&utm_campaign=booklet
