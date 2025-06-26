## pia API Documentation

- [Entities](#entities)
- [Authentication](#authentication)

### Overview

- Data is sent as JSON (Content-Type: application/json) to pia
- The requests have to be authenticated with a token from a pia business

### Entities

- [Business](business.md)
- [Positions](positions.md)
- [Positions/Working Hours](positions/working_hours.md)
- [Positions/Absences](positions/absences.md)
- [Positions/Balances](positions/balances.md)
- [Events](events.md)
- [ShiftAssignments](shift_assignments.md)

### Authentication

You need an API-Token of your pia organisation or pia section.

#### Organisation

Go to the main page of your organisation and there to "Einstellungen -> Integrationen". There you can generate your API-Token to get data of all
your sections.

#### Section

Go to the main page of your section and there to "Einstellungen -> Abteilungseinstellungen". There you can generate your API-Token to get data of the
specific section.

Example usage:

```
curl GET https://app.pia-planer.ch/api/v1/positions \
   -H 'Authorization: Business YOUR_API_KEY'
```
