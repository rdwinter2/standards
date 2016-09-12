# Events

Our core systems are built to be transactional and event driven.

Couple notes:

  - Use auditing in psql databases - https://github.com/flowcommerce/lib-postgresql
  - Define events in standalone apidoc projects - see apidoc.me/flow/catalog-event as an example
  - Event types should be union types (allowing for future expansion)
  - Creating an instance of an event must happen in exactly one place in our entire codebase
    - we do not want multiple source of 'truth' that generate events