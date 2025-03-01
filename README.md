<!-- readme-start -->

<!-- readme-content-start -->

# braze-api

[![NPM](https://nodei.co/npm/braze-api.png)](https://nodei.co/npm/braze-api/)

[![NPM version](https://img.shields.io/npm/v/braze-api.svg)](https://www.npmjs.com/package/braze-api)
[![build](https://github.com/remarkablemark/braze-api/actions/workflows/build.yml/badge.svg)](https://github.com/remarkablemark/braze-api/actions/workflows/build.yml)
[![codecov](https://codecov.io/gh/remarkablemark/braze-api/branch/master/graph/badge.svg?token=QHPI1I0XI3)](https://codecov.io/gh/remarkablemark/braze-api)
[![NPM downloads](https://badgen.net/npm/dm/braze-api)](https://www.npmjs.com/package/braze-api)

Node.js library for [Braze](https://www.braze.com/). See [docs](https://b.remarkabl.org/braze-api) and [demo](https://replit.com/@remarkablemark/braze-api). The types are from [Braze's Postman collection](https://documenter.getpostman.com/view/4689407/SVYrsdsG).

## Quick Start

```ts
import { Braze } from 'braze-api'

const braze = new Braze('YOUR_API_URL', 'YOUR_API_KEY')

await braze.messages.send({
  external_user_ids: ['your_external_user_id'],
  messages: {
    email: {
      app_id: 'your_app_id',
      from: 'Company <company@example.com>',
      email_template_id: 'your_email_template_id',
    },
  },
})
```

## Documentation

- [TypeDoc](https://b.remarkabl.org/braze-api)
- [Braze API Guide](https://www.braze.com/docs/api/)
- [Braze's Postman collection](https://documenter.getpostman.com/view/4689407/SVYrsdsG)

## Prerequisites

- [Node.js](https://nodejs.org/)
- [Braze account](https://www.braze.com/get-started)

## Installation

[NPM](https://www.npmjs.com/package/braze-api):

```sh
npm install braze-api
```

[Yarn](https://yarnpkg.com/package/braze-api):

```sh
yarn add braze-api
```

## Usage

The package needs to be configured with your account's REST endpoint and API key:

```ts
const { Braze } = require('braze-api')

const braze = new Braze('YOUR_API_URL', 'YOUR_API_KEY')
```

The same can be done with ES Modules:

```ts
import { Braze } from 'braze-api'

const braze = new Braze('YOUR_API_URL', 'YOUR_API_KEY')
```

### API URL

Use the [REST endpoint](https://www.braze.com/docs/api/basics#endpoints) provisioned to your account when you log in to the dashboard:

| Instance | REST Endpoint                 |
| -------- | ----------------------------- |
| US-01    | https://rest.iad-01.braze.com |
| US-02    | https://rest.iad-02.braze.com |
| US-03    | https://rest.iad-03.braze.com |
| US-04    | https://rest.iad-04.braze.com |
| US-05    | https://rest.iad-05.braze.com |
| US-06    | https://rest.iad-06.braze.com |
| US-08    | https://rest.iad-08.braze.com |
| EU-01    | https://rest.fra-01.braze.eu  |
| EU-02    | https://rest.fra-02.braze.eu  |

### API Key

The [API key](https://www.braze.com/docs/api/basics#creating-and-managing-rest-api-keys) can be created in your Braze dashboard.

## API Methods

This library currently supports a subset of the [Braze API endpoints](https://www.braze.com/docs/api/home). Pull requests are welcome.

### User data

- [x] /users/alias/new
- [x] /users/delete
- [x] /users/export/global_control_group
- [x] /users/export/ids
- [x] /users/export/segment
- [x] /users/external_ids/rename
- [x] /users/external_ids/remove
- [x] /users/merge
- [x] /users/identify
- [x] /users/track

### Send messages

- [x] /campaigns/trigger/send
- [x] /canvas/trigger/send
- [x] /messages/send
- [x] /sends/id/create
- [x] /transactional/v1/campaigns/{{CAMPAIGN_ID}}/send

### Schedule messages

- [x] /campaigns/trigger/schedule/create
- [x] /campaigns/trigger/schedule/delete
- [x] /campaigns/trigger/schedule/update
- [x] /canvas/trigger/schedule/create
- [x] /canvas/trigger/schedule/delete
- [x] /canvas/trigger/schedule/update
- [x] /messages/schedule/create
- [x] /messages/schedule/delete
- [x] /messages/schedule/update
- [x] /messages/scheduled_broadcasts

### Subscription groups

- [x] /subscription/status/set
- [x] /v2/subscription/status/set
- [x] /subscription/status/get
- [x] /subscription/user/status

### Email and email templates

- [x] /email/blacklist
- [x] /email/bounce/remove
- [x] /email/spam/remove
- [ ] /email/status
- [ ] /templates/email/create
- [ ] /templates/email/update
- [ ] /email/hard_bounces
- [ ] /email/unsubscribes
- [ ] /templates/email/info
- [ ] /templates/email/list

### Campaigns

- [ ] /campaigns/data_series
- [ ] /campaigns/details
- [ ] /campaigns/list
- [ ] /sends/data_series

### Canvas

- [ ] /canvas/data_series
- [ ] /canvas/data_summary
- [ ] /canvas/details
- [ ] /canvas/list

### Segments

- [ ] /segments/data_series
- [ ] /segments/details
- [ ] /segments/list
- [ ] /sessions/data_series

### Custom events

- [ ] /events/data_series
- [ ] /events/list

### Content Blocks

- [ ] /content_blocks/create
- [ ] /content_blocks/update
- [x] /content_blocks/info
- [x] /content_blocks/list

### KPI

- [ ] /kpi/dau/data_series
- [ ] /kpi/mau/data_series
- [ ] /kpi/new_users/data_series
- [ ] /kpi/uninstalls/data_series

### News Feed

- [ ] /feed/data_series
- [ ] /feed/details
- [ ] /feed/list

### SMS

- [ ] /sms/invalid_phone_numbers/remove
- [ ] /sms/invalid_phone_numbers

### Purchases

- [ ] /purchases/product_list

### Catalogs

- [ ] /synchronous/catalogs/delete
- [x] /synchronous/catalogs/get
- [ ] /synchronous/catalogs/post
- [ ] /synchronous/catalog-items/delete
- [x] /synchronous/catalog-items/list
- [x] /synchronous/catalog-items/get
- [ ] /synchronous/catalog-items/update
- [ ] /synchronous/catalog-items/create
- [ ] /asynchronous/catalog-items/delete-multiple
- [ ] /asynchronous/catalog-items/update-multiple
- [ ] /asynchronous/catalog-items/create-multiple

## Contributing

Contributions are welcome! See our [contributing guide](https://github.com/remarkablemark/braze-api/blob/master/.github/CONTRIBUTING.md) on how to proceed. :wave:

## License

[MIT](https://github.com/remarkablemark/braze-api/blob/master/LICENSE)

<!-- readme-content-end -->

<!-- readme-content-placeholder -->

<!-- readme-end -->
