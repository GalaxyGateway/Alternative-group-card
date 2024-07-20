# Alternative-group-card


```
type: custom:stack-in-card
cards:
  - type: custom:mushroom-template-card
    primary: Alarm
    icon: |-
      {% if is_state (entity, '0') %}
        mdi:home-alert
      {% elif is_state (entity, '1') %}
        mdi:shield-lock 
      {% elif is_state (entity, '2') %}
        mdi:shield-home
      {% elif is_state (entity, '3') %}
        mdi:shield-check
      {% elif is_state (entity, '5') %}
        mdi:shield-moon 
      {% else %}
        mdi:clock-alert-outline 
      {% endif %}
    secondary: |-
      {% if is_state (entity, '0') %}
        Not ready
      {% elif is_state (entity, '1') %}
        Armed
      {% elif is_state (entity, '2') %}
        Armed part
      {% elif is_state (entity, '3') %}
        Ready to arm
      {% elif is_state (entity, '5') %}
        Armed night
      {% else %}
        Time locked
      {% endif %}  
    entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
    tap_action:
      action: none
    double_tap_action:
      action: none
    hold_action:
      action: none
    icon_color: |-
      {% if is_state (entity, '0') %}
        orange
      {% elif is_state (entity, '1') %}
        red 
      {% elif is_state (entity, '2') %}
        red 
      {% elif is_state (entity, '3') %}
        green 
      {% elif is_state (entity, '5') %}
        red 
      {% else %}
        yellow 
      {% endif %}
    fill_container: true
    layout: horizontal
    multiline_secondary: false
    card_mod:
      style: |
        ha-card {
            --card-primary-font-size:16px;
            # --icon-symbol-size: 53px;
            border:none;            
           }
  - type: custom:mushroom-chips-card
    chips:
      - type: conditional
        conditions:
          - entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
            state: '0'
        chip:
          type: template
          double_tap_action:
            action: none
          entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
          icon: mdi:home-alert
          tap_action:
            action: call-service
            service: mqtt.publish
            target: {}
            data:
              qos: 0
              retain: false
              topic: galaxy/f55760/group/A1/cmd/set
              payload: '5'
          hold_action:
            action: none
          icon_color: blue
          card_mod:
            style: |
              ha-card:hover {
                transform: scale(1.2);
                transition: 0s;
              }
              ha-card:active { 
                animation:
                  {% if states('sensor.galaxy_gateway_f55760_group_f55760_a1_alarm') == '0' -%} 
                    blink 1s linear 5;
                  {% else -%} none;
                  {% endif %}
              }
              @keyframes blink {
                0% {opacity: 0;}
                50% {opacity: 100;}
                100% {opacity: 0;}
              }
      - type: conditional
        conditions:
          - entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
            state: '1'
        chip:
          type: template
          double_tap_action:
            action: none
          entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
          icon: mdi:home-alert
          tap_action:
            action: call-service
            service: mqtt.publish
            target: {}
            data:
              qos: 0
              retain: false
              topic: galaxy/f55760/group/A1/cmd/set
              payload: '0'
          hold_action:
            action: none
          icon_color: blue
          card_mod:
            style: |
              ha-card:hover {
                transform: scale(1.2);
                transition: 0s;
              }
              ha-card:active { 
                animation:
                  {% if states('sensor.galaxy_gateway_f55760_group_f55760_a1_alarm') == '0' -%} 
                    blink 1s linear 5;
                  {% else -%} none;
                  {% endif %}
              }
              @keyframes blink {
                0% {opacity: 0;}
                50% {opacity: 100;}
                100% {opacity: 0;}
              }
      - type: conditional
        conditions:
          - entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
            state: '2'
        chip:
          type: template
          double_tap_action:
            action: none
          entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
          icon: mdi:home-alert
          tap_action:
            action: call-service
            service: mqtt.publish
            target: {}
            data:
              qos: 0
              retain: false
              topic: galaxy/f55760/group/A1/cmd/set
              payload: '0'
          hold_action:
            action: none
          icon_color: blue
          card_mod:
            style: |
              ha-card:hover {
                transform: scale(1.2);
                transition: 0s;
              }
              ha-card:active { 
                animation:
                  {% if states('sensor.galaxy_gateway_f55760_group_f55760_a1_alarm') == '0' -%} 
                    blink 1s linear 5;
                  {% else -%} none;
                  {% endif %}
              }
              @keyframes blink {
                0% {opacity: 0;}
                50% {opacity: 100;}
                100% {opacity: 0;}
              }
      - type: conditional
        conditions:
          - entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
            state: '3'
        chip:
          type: template
          double_tap_action:
            action: none
          entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
          icon: mdi:shield-lock
          tap_action:
            action: call-service
            service: mqtt.publish
            target: {}
            data:
              qos: 0
              retain: false
              topic: galaxy/f55760/group/A1/cmd/set
              payload: '1'
          hold_action:
            action: none
          icon_color: blue
          card_mod:
            style: |
              ha-card:hover {
                transform: scale(1.2);
                transition: 0s;
              }
              ha-card:active { 
                animation:
                  {% if states('sensor.galaxy_gateway_f55760_group_f55760_a1_alarm') == '0' -%} 
                    blink 1s linear 5;
                  {% else -%} none;
                  {% endif %}
              }
              @keyframes blink {
                0% {opacity: 0;}
                50% {opacity: 100;}
                100% {opacity: 0;}
              }
      - type: conditional
        conditions:
          - entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
            state: '3'
        chip:
          type: template
          double_tap_action:
            action: none
          entity: sensor.galaxy_gateway_f55760_group_f55760_a1_state
          icon: mdi:shield-home
          tap_action:
            action: call-service
            service: mqtt.publish
            target: {}
            data:
              qos: 0
              retain: false
              topic: galaxy/f55760/group/A1/cmd/set
              payload: '2'
          hold_action:
            action: none
          icon_color: blue
          card_mod:
            style: |
              ha-card:hover {
                transform: scale(1.2);
                transition: 0s;
              }
              ha-card:active { 
                animation:
                  {% if states('sensor.galaxy_gateway_f55760_group_f55760_a1_alarm') == '0' -%} 
                    blink 1s linear 5;
                  {% else -%} none;
                  {% endif %}
              }
              @keyframes blink {
                0% {opacity: 0;}
                50% {opacity: 100;}
                100% {opacity: 0;}
              }
      - type: conditional
        conditions:
          - entity: sensor.galaxy_gateway_f55760_group_f55760_a1_alarm
            state: '2'
        chip:
          type: template
          double_tap_action:
            action: none
          entity: sensor.galaxy_gateway_f55760_group_f55760_a1_alarm
          icon: mdi:lock-reset
          tap_action:
            action: call-service
            service: mqtt.publish
            target: {}
            data:
              qos: 0
              retain: false
              topic: galaxy/f55760/group/A1/cmd/set
              payload: '3'
          hold_action:
            action: none
          icon_color: yellow
          card_mod:
            style: |
              ha-card:hover {
                transform: scale(1.2);
                transition: 0s;
              }
              ha-card:active { 
                animation:
                  {% if states('sensor.galaxy_gateway_f55760_group_f55760_a1_alarm') == '0' -%} 
                    blink 1s linear 5;
                  {% else -%} none;
                  {% endif %}
              }
              @keyframes blink {
                0% {opacity: 0;}
                50% {opacity: 100;}
                100% {opacity: 0;}
              }
      - type: template
        double_tap_action:
          action: none
        entity: sensor.galaxy_gateway_f55760_group_f55760_a1_alarm
        icon: |-
          {% if is_state (entity, '0')%}
            mdi:alarm-light-off
          {% elif is_state (entity, '1')%}
            mdi:alarm-light
          {% else %}
            mdi:shield-alert
          {% endif %}        
        tap_action:
          action: none
        hold_action:
          action: none
        icon_color: |-
          {% if is_state (entity, '0')%}
            green 
          {% elif is_state (entity, '1')%}
            red
          {% else %}
            orange
          {% endif %}
        card_mod:
          style: |
            ha-card {
              border: none;
              animation:
                {% if states('sensor.galaxy_gateway_f55760_group_f55760_a1_alarm') == '2' -%} 
                  blink 2s linear infinite;
                {% else -%} none
                {% endif %}
            }
            @keyframes blink {
              0% {opacity: 0;}
              50% {opacity: 100;}
              100% {opacity: 0;}
            }
    alignment: end
    card_mod:
      style: |
        ha-card {
          --chip-icon-size: 25px;
          margin-top: 18px;
          margin-right: 5px;
          margin-bottom: 10px;
        }
```
