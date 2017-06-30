# Events

Our core systems are built to be transactional and event driven.

Couple notes:

  - Use auditing in psql databases - https://github.com/flowcommerce/lib-postgresql
  - Define events in one of our core api projects - https://github.com/flowcommerce/api or https://github.com/flowcommerce/api-internal or https://github.com/flowcommerce/api-partner
  - Event types should be union types (allowing for future expansion)
  - Creating an instance of an event must happen in exactly one place in our entire codebase
    - we do not want multiple source of 'truth' that generate events
