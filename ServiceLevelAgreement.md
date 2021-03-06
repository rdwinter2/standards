# Flow Commerce API Service Level Agreement

## Flow Commerce API SLA

During the Term of the applicable Flow Commerce Agreement (the
"Agreement"), the Flow Commerce API will be
operational and available to Customer at least 99.9% of the time in
any calendar month (the "Flow Commerce API SLA"). If Flow Commerce does
not meet the Flow Commerce API SLA, and if Customer meets its obligations
under this Flow Commerce API SLA, Customer will be eligible to receive the
Service Credits described below. This Flow Commerce API SLA states
Customer's sole and exclusive remedy for any failure by Flow Commerce
to meet the Flow Commerce API SLA.

## Definitions

The following definitions shall apply to the Flow Commerce API SLA.

  - Flow Commerce Covered Modules are Localization, Pricing, Landed
    Cost, Payment or Logistics as described at https://docs.flow.io
    and available at https://api.flow.io

  - Downtime means, there is more than one minute of sustained
    unavailability of all of the APIs provided by a Module.

  - Sustained unavailability is defined as all healthcheck requests to
    a Module within a one minute period have failed.

  - Monthly Uptime Percentage means total number of minutes in a
    calendar month minus the number of minutes of Downtime suffered in
    a calendar month, divided by the total number of minutes in a
    calendar month.

  - Monthly Subscription Fee means the platform subscription fee as
    defined in the Agreement in a calendar month.

  - Subscription Credit Percentage means the percentage of the Monthly
    Subscription Fee that will be eligible as a credit to future
    Monthly Subscription Fees.

  - Service Credit means the following:

    | Monthly Uptime Percentage | Subscription Credit Percentage |
    |---------------------------|--------------------------------|
    | < 99.9% & >= 99.0%        | 10%                            |
    | < 99.0% & >= 95.0%        | 25%                            |
    | < 95.0%                   | 50%                            |


  - Customer Must Request Service Credit. In order to receive any of
    the Service Credits described above, Customer must notify Flow
    Commerce within thirty days from the time Customer becomes
    eligible to receive a Service Credit. Failure to comply with this
    requirement will forfeit Customer's right to receive a Service
    Credit.

  - Maximum Service Credit. The aggregate maximum number of Service
    Credits to be issued by Flow Commerce to Customer for all Downtime
    that occurs in a single calendar month shall not exceed 50% of
    that month's subscription fee.

  - Measurement. Flow Commerce API SLA is as measured by NewRelic
    availability report. Flow Commerce reserves the right to change,
    without notice, the measurement party.

  - Flow Commerce API SLA Exclusions. The Flow Commerce API SLA does
    not apply to any services that expressly exclude this Flow
    Commerce API SLA (as stated in the documentation for such
    services) or any performance issues: (i) caused by factors
    described in the "Force Majeure" section of the Agreement; or (ii)
    that resulted from Customer's equipment or third-party equipment,
    or both (not within the primary control of Flow Commerce).
