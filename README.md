# MUUNGANO FAMILY CBOs Management System — Starter MVP

## Kilichopo
- `index.html`: responsive Kiswahili portal, dashboard, forms, search, CSV export and print/PDF through browser.
- `Code.gs`: Google Apps Script backend starter and Google Sheets tab setup function.
- `logo.png`: nembo iliyotolewa.

## Muhimu kuhusu hali ya sasa
Hii ni **starter MVP**, si mfumo uliokwishaidhinishwa kwa matumizi ya taarifa nyeti. Bila backend URL, fomu zinaonyesha demo ya kivinjari na data haitadumu. Backend hii ni msingi wa kuunganisha Google Sheets; haijatekeleza kikamilifu login/role authorization. **Usiweke UNHCR ID, namba za simu, sahihi, au taarifa za familia kwenye deployment ya umma kabla ya kuweka uthibitishaji wa seva na ruhusa.**

## Kusakinisha Google Sheets
1. Tengeneza Google Spreadsheet mpya.
2. Nakili Spreadsheet ID kutoka URL: `https://docs.google.com/spreadsheets/d/SPREADSHEET_ID/edit`.
3. Fungua **Extensions → Apps Script**.
4. Bandika yaliyomo `Code.gs`; badilisha `PASTE_GOOGLE_SHEET_ID_HERE` kwa ID yako.
5. Chagua kazi `setupSheets` na ubonyeze Run; ruhusu access. Tabs zote zitatengenezwa.
6. Deploy → New deployment → Web app. Chagua execute as owner. Weka access kwa watu waliokusudiwa pekee kulingana na sera za shirika. Ikiwa deployment hairuhusu watumiaji wako kuifikia, tumia backend yenye authentication inayofaa badala ya kufungua public.
7. Nakili URL ya Web App inayoishia `/exec`.
8. Fungua `index.html` kupitia web host (si file:// kama browser inazuia fetch), nenda **Muunganisho**, bandika URL, hifadhi na ujaribu.

## Kuchapisha portal
- Kwa jaribio: fungua `index.html` kwenye browser.
- Kwa matumizi ya shirika: host HTML assets kwenye hosting ya HTTPS inayodhibitiwa na shirika, au urekebishe `doGet()` ili kutoa HTML kutoka Apps Script. Hakikisha logo iko pamoja na HTML.
- PDF/A4: tumia kitufe cha Chapisha kisha chagua Save as PDF. Ripoti ina muundo wa kuchapisha wa browser; mpangilio wa A4 unaweza kuchaguliwa kwenye print dialog.

## Kabla ya kwenda live
- Tekeleza login salama na uthibitishaji wa ruhusa upande wa seva (Founder/CEO/President/Secretary/Treasurer/Team Member/Viewer).
- Ongeza CSRF/abuse protection, validation ya kila field, backup ya Sheets, audit logs na sera ya retention.
- Hakikisha sheria na taratibu za Kenya kuhusu data binafsi zinafuatwa. Punguza watu wanaoweza kuona UNHCR ID, maelezo ya familia na sahihi za kidijitali.
- Tathmini duplicate detection kwa kila aina ya rekodi, approvals na digital signature canvas kabla ya matumizi rasmi.
- Tumia data ya majaribio pekee mpaka usalama upitiwe.

## Akiba ya 10%
Fomu ya akiba huhesabu `RequiredAmount = BaseAmount × Rate / 100` na `Balance = max(0, RequiredAmount − PaidAmount)`. Kiwango cha awali ni 10%; hakikisha msingi wa hesabu umeidhinishwa na shirika.
