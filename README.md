# SaskPower (saskpower)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

SaskPower — the Saskatchewan Power Corporation — is the Crown corporation that owns and runs essentially the whole electricity value chain in the province of Saskatchewan, Canada. Established in 1929 as the Saskatchewan Power Commission and continued as the Saskatchewan Power Corporation in 1949 under The Power Corporation Act, it is owned by the provincial government through Crown Investments Corporation and reports to a Minister Responsible rather than to shareholders. It generates, transmits, distributes and retails power to more than 550,000 customers across roughly 652,000 square kilometres on more than 160,000 kilometres of line, from a fleet of coal, natural gas, hydro, wind and solar facilities totalling about 5,437 MW. Unlike Ontario or Alberta there is no competitive wholesale market operator sitting beside it — SaskPower is generator, wires company and retailer at once. Its API posture is the exact inverse of a regulated open-banking-style utility: no consumer energy data mandate applies to it at all. Saskatchewan has no Green Button regulation (Ontario and Nova Scotia do), Canada has no national energy consumer data right, and the Green Button Alliance states plainly that it has no information about any Green Button deployment in Saskatchewan. Smart meter usage data is visible only to the account holder inside MySaskPower behind an Azure AD B2C login; there is no consented third-party data-sharing API, no ESPI/Green Button surface, and no accreditation scheme. What SaskPower does publish — and publishes wide open, anonymously, with no key, no signup and no rate limit — is grid and system data: a live JSON feed of provincial system demand, generation by fuel type, net interchange and historical peak demand behind the public "Where Your Power Comes From" page, an RSS feed of planned outages, and two KML feeds driving the outage and smart-meter installation maps. None of it is documented as an API, versioned, or covered by a developer program: the former SaskPower ESB developer portal at api-info.saskpower.com no longer resolves, and api.saskpower.com is a live TIBCO/Mashery gateway that answers every public path with ERR_596_SERVICE_NOT_FOUND. Open market data, closed consumer data, and no published door for a developer to knock on.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/saskpower/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/saskpower/refs/heads/main/apis.yml)

## Tags

- Energy
- Canada
- Utilities
- Electricity
- Grid
- Smart Metering
- Crown Corporation
- Outages
- Renewables
- Open Data

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### SaskPower Power Use Dashboard Data

The undocumented JSON endpoint behind SaskPower's public "Where Your Power Comes From" page. A single anonymous GET — no key, no signup, no referer check — returns the province's current supply picture: systemDemand, systemSupply, generation, netInterchange (negative when Saskatchewan is exporting), historicalPeakDemand with its date, and a generationByType array giving each fuel type (Hydro, Coal, Natural Gas, Wind, Solar, Other) its percentOfTotalGeneration, totalGenerationForType in MW, and the named powerUseFacilities contributing to it. Verified 2026-07-27 as HTTP 200, application/json, 7,917 bytes, valid JSON. SaskPower publishes no reference, no schema, no version and no rate limit for it.

- **Human URL:** [https://www.saskpower.com/our-power-future/our-electricity/electrical-system/where-your-power-comes-from](https://www.saskpower.com/our-power-future/our-electricity/electrical-system/where-your-power-comes-from)
- **Base URL:** `https://www.saskpower.com/ignitionapi/PowerUseDashboard/GetPowerUseDashboardData`

#### Tags

- Grid
- System Data
- Generation Mix
- Demand
- Open Data
- Undocumented

#### Properties

- [Documentation](https://www.saskpower.com/our-power-future/our-electricity/electrical-system/where-your-power-comes-from)
- [Terms of Service](https://www.saskpower.com/terms)

### SaskPower Planned Outages RSS Feed

A genuinely published, anonymous RSS 2.0 feed of SaskPower's planned power outages, opened by the visible "RSS feed" link on the Outages Planned for Necessary Maintenance page. Each item carries the affected area and date, a pubDate, and a CDATA description listing towns affected, the outage window, the reason, and reschedule notes. The feed's own atom:link self-reference (`/feeds/outages.xml`) is dead, so the working location is the `/ignitionapi/Content/GetRSSFeed` endpoint the page's JavaScript opens. Verified 2026-07-27 as HTTP 200, text/xml, 13,058 bytes, valid XML.

- **Human URL:** [https://www.saskpower.com/outages/power-outages/outages-planned-for-necessary-maintenance](https://www.saskpower.com/outages/power-outages/outages-planned-for-necessary-maintenance)
- **Base URL:** `https://www.saskpower.com/ignitionapi/Content/GetRSSFeed`

#### Tags

- Outages
- RSS
- Grid
- Open Data

#### Properties

- [Documentation](https://www.saskpower.com/outages/power-outages/outages-planned-for-necessary-maintenance)
- [Terms of Service](https://www.saskpower.com/terms)

### SaskPower Outage Map KML Feed

The KML data feed behind SaskPower's public outage map, referenced directly in the markup of the Outage Map and Updates page and served anonymously from the outagemap.saskpower.com host. Returns a KML 2.1 document with styles for planned and unplanned outages and polygon geometry for affected areas. Verified 2026-07-27 as HTTP 200, text/xml, 633,252 bytes, valid XML.

- **Human URL:** [https://www.saskpower.com/outages/power-outages/outage-updates](https://www.saskpower.com/outages/power-outages/outage-updates)
- **Base URL:** `https://outagemap.saskpower.com/Files/GetKmlFile`

#### Tags

- Outages
- KML
- Geospatial
- Grid
- Open Data
- Undocumented

#### Properties

- [Documentation](https://www.saskpower.com/outages/power-outages/outage-updates)
- [Terms of Service](https://www.saskpower.com/terms)

### SaskPower Smart Meter Installation Map KML Feed

The KML data feed behind SaskPower's Smart Meter Installation Map, requested by the site's own SP.scripts.js bundle and served anonymously from the Sitecore content handler. Returns a KML 2.1 document with styles for in-progress, coming-up, complete and unassigned deployment zones and polygon geometry for each named area. Verified 2026-07-27 as HTTP 200, 856,869 bytes, valid XML (served as Content-Type text/html despite the XML payload). This is deployment-programme data, not metering data — it shows where smart meters are being installed, never a reading.

- **Human URL:** [https://www.saskpower.com/our-power-future/investing-in-a-reliable-power-grid/smart-meters/meter-installation-map](https://www.saskpower.com/our-power-future/investing-in-a-reliable-power-grid/smart-meters/meter-installation-map)
- **Base URL:** `https://www.saskpower.com/api/sitecore/Content/GetSmartMeterKmlFile`

#### Tags

- Smart Metering
- KML
- Geospatial
- Open Data
- Undocumented

#### Properties

- [Documentation](https://www.saskpower.com/our-power-future/investing-in-a-reliable-power-grid/smart-meters/meter-installation-map)
- [Terms of Service](https://www.saskpower.com/terms)

## Common Properties

- [Website](https://www.saskpower.com/)
- [About](https://www.saskpower.com/about-us)
- [Terms of Service](https://www.saskpower.com/terms)
- [Privacy](https://www.saskpower.com/footer/how-we-do-business/privacy)
- [Blog](https://www.saskpower.com/about-us/Our-Company/Blog)
- [News Releases](https://www.saskpower.com/about-us/media-information/news-releases)
- [LinkedIn](https://www.linkedin.com/company/saskpower)
- [YouTube](http://www.youtube.com/user/Poweringthefuture)
- [Documentation](https://www.saskpower.com/our-power-future/our-electricity/electrical-system/where-your-power-comes-from)

## Mandate and Access Posture

- **Mandate regime:** none. Saskatchewan has enacted no Green Button regulation; Ontario (O. Reg. 633/21) and Nova Scotia have. Canada has no national energy consumer data right.
- **Mandate status:** none — verified against the Green Button Alliance Canadian Initiatives page, which states it has no information about Green Button deployments in Saskatchewan, and against a site-wide probe of saskpower.com that found no Green Button page.
- **Data standard:** no standard reference found. No ESPI, CDR, OCPP, OCPI, OpenADR, IEEE 2030.5, or IEC CIM.
- **Consumer data API:** none. Smart meter usage is visible only to the account holder inside MySaskPower behind Azure AD B2C.
- **Open market data:** yes, but undocumented — four anonymous, unauthenticated feeds carrying grid, outage and deployment data.
- **Access gate:** none published. There is nothing to sign up for. The former SaskPower ESB developer portal at api-info.saskpower.com no longer resolves, and api.saskpower.com (TIBCO/Mashery) returns ERR_596_SERVICE_NOT_FOUND on every public path.
- **Downloadable contracts:** none. No OpenAPI, Swagger, WSDL, GraphQL schema, or Postman collection exists.

Full probe log and evidence: [review.yml](review.yml)

## Maintainers

- **Kin Lane** — kin@apievangelist.com
