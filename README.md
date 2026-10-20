# compliant-demo
# ShopIndia — Compliant Negative Control

## Purpose

This synthetic e-commerce repository serves as the compliant
negative control for the PrivacyPilot evaluation.

Its executable data handling is designed to match the accompanying
`PRIVACY_POLICY.md`. This is a benchmark fixture, not a certification
that a real application complies with every legal requirement.

## Disclosed processing

- Collects full name, email address, phone number, and delivery address.
- Stores order and purchase details.
- Uses Twilio to send order-confirmation SMS messages to registered
  phone numbers.
- Sends delivery partners only the name and address needed for
  order fulfilment, as described in the policy.

## False-positive controls

Some comments contain references to sensitive identifiers or third-party
SDKs for testing whether a scanner mistakes documentation for executable
data processing.

These references are not executable collection, storage, or transmission
operations. They should not independently produce compliance findings.

The disclosed Twilio integration is also a negative control: a scanner
should not flag third-party transmission merely because an external
provider is involved when the recipient and purpose are disclosed.

## Benchmark expectations

- Do not flag disclosed personal-data collection solely because the
  fields contain personal information.
- Do not flag the disclosed Twilio SMS flow solely because it uses
  a third-party provider.
- Do not interpret comment-only references as evidence of actual
  processing.
- Do not treat this repository alone as proof that PrivacyPilot has
  zero false positives or that the application is legally compliant.

Record expected findings in the benchmark ground-truth manifest before
running the scanner.
