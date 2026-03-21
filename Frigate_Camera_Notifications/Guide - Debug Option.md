### Параметр отладки

В блюпринте есть переключатель, включающий отладочный вывод. Чтобы его активировать, прокрутите автоматизацию в самый низ и переведите параметр `Debug` в состояние `on/true`. Для более удобного и безопасного обмена логами вы также можете скрыть свой базовый URL через переключатель `redacted`.

![image](https://github.com/user-attachments/assets/0201a2df-5c75-422f-b237-4632521832bb)

При необходимости можно увеличить количество хранимых trace, добавив этот блок в начало или конец автоматизации при редактировании в режиме YAML:

```yaml
trace:
  stored_traces: 40
```

После этого, когда автоматизация сработает, вы сможете найти отладочный вывод в trace.

Сначала откройте автоматизацию и выберите `Traces` в правом верхнем углу.

![image](https://github.com/foric27/HA_blueprints/assets/24822223/6d1eee11-a6e0-4685-84e9-da1c519d6628)

Там отображается визуальная схема trace. Позже это можно будет разобрать в отдельном гайде.
Нас интересуют два узла, они отмечены красным. Первый содержит вывод для первоначального уведомления. Второй содержит вывод для всех циклов обновления.

![image](https://github.com/user-attachments/assets/0c4ebd4a-9032-4510-9d9f-28d634e0a938)

Если нажать на любой из этих узлов, вы увидите отладочный вывод, который можно прочитать или скопировать, как в примере ниже.

```text
Executed: September 15, 2024 at 17:05:10
Result:
params:
  domain: logbook
  service: log
  service_data:
    name: Frigate Notification
    message: |-
      DEBUG: 
        Info:
          fps: 5, 
          frigate event id: 1726383908.860047-zjn8r0, 
          object (formatted): person (Person),
        Config: 
          camera(formatted): car_port(Car Port), 
          Base URL: REDACTED, 
          critical: False, 
          tts: False 
          helper: N/A,
          alert once: True, 
          Update Thumbnails: True, 
          Video: , 
          Target: Mobile Device
          cooldown: 10s, 
          loiter timer: 0s, 
          initial delay: 0s, 
          color: grey, 
          sound: default, 
          android_auto: False, 
          Group: car_port-frigate-notification, 
          Channel: , 
          Sticky: False, 
          Title: , 
          Message: A Person was detected on the Car Port camera.,
          Subtitle: , 
          tap_action: REDACTED/api/frigate/notifications/1726383908.860047-zjn8r0/snapshot.jpg, 
          button 1 Text/URL/Icon: View Clip (REDACTED/api/frigate/notifications/1726383908.860047-zjn8r0/car_port/clip.mp4) , 
          button 2 Text/URL/Icon: View Stream (REDACTED/api/camera_proxy_stream/camera.car_port?token=11d76014953a85dcfc1a9d0dea25f3aa3d8234ded506397bfba013019729aef2) , 
          button 3 Text/URL/Icon: Silence New Notifications (REDACTED) , 
          icon: mdi:homeassistant
          tv: False, 
          tv_position: center, 
          tv_size: large, 
          tv_duration: 10, 
          tv_transparency: 0%, 
          tv_interrupt: False, 
        Filters: 
          Zones: 
            Zone Filter toggle on: True, 
            Multi-Zone toggle on: False, 
            Required zones: ['carport', 'front_door'], 
            Zone Order toggle on: False
            Entered Zones: ['front_door'],
            TEST: PASS  , 
          Required objects TEST: 
            Input: ['person'], 
            TEST: PASS
          presence entity (not home):
            Entity: 
            TEST:  PASS, 
          disabled times: [], 
          State Filter: 
            State Filter toggle on: True, 
            State Filter Entity: lock.front_door_lock, 
            Required States: ['locked', 'unavailable'], 
            TEST: PASS,
          Custom Filter: True
  target: {}
running_script: false
```
