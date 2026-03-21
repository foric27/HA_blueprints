## Уведомления Frigate

Этот блюпринт отправляет уведомление на ваше устройство, когда для выбранной камеры происходит событие Frigate. В первом уведомлении будет миниатюра обнаружения, а также интерактивное уведомление, позволяющее открыть клип и снимок.

С этим блюпринтом вы можете отправлять уведомления сразу на несколько устройств, оставив поле `Device` пустым и используя вместо него [группу уведомлений][1].

### STABLE
[![Import blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/foric27/HA_blueprints/main/Frigate_Camera_Notifications/Stable.yaml)

### BETA
[![Import blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/foric27/HA_blueprints/main/Frigate_Camera_Notifications/Beta.yaml)

### Требования к версиям ПО

- Минимальная версия Home Assistant: 2024.11
- Минимальная версия Frigate: 0.14
- Минимальная версия интеграции Frigate: 5.7.0
  - Во время настройки должна быть включена опция `Enable the unauthenticated notification event proxy`
- MQTT-брокер, подключённый к Home Assistant и Frigate.
- Минимальная версия iOS: 15.0

### Обязательные сущности

- [Камера Frigate](./Guide%20-%20Configuration%20Options.md)
- [Устройство мобильного приложения **или** имя группы уведомлений/ТВ](./Guide%20-%20Configuration%20Options.md)

### Возможности

- Удобный выбор одной или нескольких [камер](./Guide%20-%20Configuration%20Options.md) или [мобильного устройства](./Guide%20-%20Configuration%20Options.md) из выпадающего списка.
- Отправка уведомлений:
  - на мобильное устройство Android или iOS;
  - на Android TV через [nfandroidtv](https://www.home-assistant.io/integrations/nfandroidtv/);
  - в [группу](./Guide%20-%20Configuration%20Options.md), содержащую любую комбинацию этих устройств.
- Настройка [заголовка](./Guide%20-%20Configuration%20Options.md) и [текста](./Guide%20-%20Configuration%20Options.md) уведомления.
- Добавление миниатюры, снимка, GIF или видео события с рамкой объекта и обрезкой для изображений.
- Динамическая обработка типа объекта, зон и распознавания лиц через Double Take.
- Автоматическая обработка типичных ошибок вроде несовпадения регистра или неверных URL.
- Возможность отправлять уведомление как [критическое](./Guide%20-%20Configuration%20Options.md).
- Возможность ограничить воспроизведение звука для повторных обновлений уведомления и настроить звук на iOS. [Alert Once](./Guide%20-%20Configuration%20Options.md)
- Настройка [цвета](./Guide%20-%20Configuration%20Options.md) и [иконки](./Guide%20-%20Configuration%20Options.md) уведомления.

#### Фильтры

- Указание зон, о которых нужно уведомлять. [Zone Filter](./Guide%20-%20Configuration%20Options.md)
- Выбор между обязательным входом во все зоны или в любую одну. [Multi Zone](./Guide%20-%20Configuration%20Options.md)
- Возможность требовать определённый порядок прохождения зон.
- Указание типа [объектов][3], о которых нужно уведомлять. [Object Filter](./Guide%20-%20Configuration%20Options.md)
- Отключение уведомлений, если сущность присутствия или группа находится в состоянии `home`. [Presence Filter](./Guide%20-%20Configuration%20Options.md)
- Ограничение уведомлений по состоянию другой сущности. [State Filter](./Guide%20-%20Configuration%20Options.md)
- Ограничение уведомлений по времени суток. [Time Filter](./Guide%20-%20Configuration%20Options.md)
- Настройка [cooldown](./Guide%20-%20Configuration%20Options.md) для камеры, чтобы уменьшить число уведомлений при частых событиях подряд.
- Возможность [временно отключить новые уведомления](./Guide%20-%20Configuration%20Options.md) на заданный период. Полезно, если вы знаете, что сами будете долго вызывать срабатывания, например когда дети играют на улице.
- Настройка [таймера loitering](./Guide%20-%20Configuration%20Options.md), чтобы получать уведомление о неподвижных объектах, остающихся в кадре заданное время.
- Пользовательские шаблонные фильтры.

#### Действия

- Настройка действия при нажатии на уведомление. [Tap Action](./Guide%20-%20Configuration%20Options.md)
- Настройка 3 [кнопок действий](./Guide%20-%20Configuration%20Options.md), которые могут открывать почти что угодно. По умолчанию это: открыть клип, открыть снимок и отключить новые уведомления.
- Настройка размера, прозрачности, позиции и длительности [уведомлений на ТВ](./Guide%20-%20Configuration%20Options.md).

#### Дополнительно

- Режим отладки для [диагностики](./Guide%20-%20Configuration%20Options.md) и возможность скрыть базовый URL в отладочном выводе.
- Поддержка нескольких экземпляров Frigate через [Client ID](./Guide%20-%20Configuration%20Options.md) и [MQTT topic](./Guide%20-%20Configuration%20Options.md).
- Пользовательские [звуки](./Guide%20-%20Configuration%20Options.md) на iOS.
- Возможность отправлять [live view](./Guide%20-%20Configuration%20Options.md) на iOS.
- Настройка пользовательских [каналов уведомлений](./Guide%20-%20Configuration%20Options.md) на Android.
- Параметры Android Sticky, описанные в [этой теме сообщества](https://community.home-assistant.io/t/frigate-mobile-app-notifications/311091/1043).
- Поддержка Android Auto.

[1]: https://www.home-assistant.io/integrations/group/#notify-groups
[3]: https://docs.frigate.video/configuration/objects/
