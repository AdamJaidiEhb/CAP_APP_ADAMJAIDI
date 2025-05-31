# CAP iFlow Viewer

Een SAP CAP + Fiori Elements applicatie die data ophaalt uit een iFlow API via de SAP Integration Suite, en deze read-only weergeeft in een Fiori List Report UI.

---

## 📦 Projectstructuur

- **Backend**: Node.js met SAP Cloud Application Programming Model (CAP)
- **Frontend**: Fiori Elements (List Report Page)
- **Externe API**: iFlow gepubliceerd via SAP Integration Suite
- **Authenticatie**: OAuth 2.0 met client credentials

---

## ⚙️ Setup en installatie

1. **Clone het project**

```bash
git clone <repo-url>
cd cap-api-fiori
```

2. **Installeer afhankelijkheden**

```bash
npm install
```

3. **Voeg `.env` toe in rootfolder**

```dotenv
IFLOW_URL=https://...
CLIENT_ID=...
CLIENT_SECRET=...
TOKEN_URL=https://.../oauth/token
```

4. **Start de app**

```bash
npm run dev
```

De CAP-service is dan bereikbaar op [http://localhost:4004](http://localhost:4004)

---

## 🧠 Functionaliteit

- Ophaal van iFlow-data via OAuth2 + axios
- Mapping naar een CDS-entiteit (`IFlowEntity`)
- Read-only presentatie via Fiori UI (ListReport)
- Live herlaadbaar via `cds watch`

---

## 📁 Belangrijke bestanden

| Bestand                          | Doel                          |
|----------------------------------|-------------------------------|
| `srv/external-api-service.js`    | Custom handler met API-call  |
| `srv/external-api-service.cds`   | CAP service-definitie        |
| `db/data-model.cds`              | Entiteitdefinitie            |
| `app/iflow-ui/`                  | Fiori frontend-app           |
| `.env`                           | Config voor API-authenticatie |

---

## 🚫 Beperkingen

- Alleen `READ`-functionaliteit (geen create/update/delete)
- Geen Launchpad integratie (standalone AppRouter)
- Test enkel lokaal of op BTP trial

---

## 🧑‍💻 Auteur

Adam  
Student toegepaste informatica, Erasmushogeschool Brussel  
Opdracht: *Fiori Elements + CAP + iFlow Integratie*