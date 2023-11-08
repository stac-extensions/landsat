# Landsat Extension Specification

- **Title:** Landsat
- **Identifier:** <https://stac-extensions.github.io/landsat/v2.0.0/schema.json>
- **Field Name Prefix:** landsat
- **Scope:** Item
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Stable
- **Owner**: @philvarner

This document explains the Landsat Extension to the [SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.

- Examples:
  - [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:

- [ ] Catalogs
- [ ] Collections
- [x] Item Properties (incl. Summaries in Collections)
- [ ] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections)
- [ ] Links

| Field Name                  | Type   | Description                                                                                                                                         |
| --------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| landsat:scene_id            | string | Landsat Scene Identifier                                                                                                                            |
| landsat:collection_category | string | Collection Category                                                                                                                                 |
| landsat:collection_number   | string | Collection Number                                                                                                                                   |
| landsat:wrs_type            | string | WRS Type                                                                                                                                            |
| landsat:wrs_path            | string | WRS Path                                                                                                                                            |
| landsat:wrs_row             | string | WRS Row                                                                                                                                             |
| landsat:cloud_cover_land    | number | Land Cloud Cover                                                                                                                                    |
| landsat:correction          | string | Product Correction Level                                                                                                                            |
| landsat:product_generated   | string | The datetime that the product (data) was generated, formatted according to [RFC 3339, section 5.6](https://tools.ietf.org/html/rfc3339#section-5.6). |

### Additional Field Information

#### landsat:product_generated

The datetime associated with the generation of the product. This will typically be
the metadata field at the path `LEVEL1_PROCESSING_RECORD/DATE_PRODUCT_GENERATED` or
`LEVEL2_PROCESSING_RECORD/DATE_PRODUCT_GENERATED`.

## Relation types

None.

## Contributing

All contributions are subject to the
[STAC Specification Code of Conduct](https://github.com/radiantearth/stac-spec/blob/master/CODE_OF_CONDUCT.md).
For contributions, please follow the
[STAC specification contributing guide](https://github.com/radiantearth/stac-spec/blob/master/CONTRIBUTING.md) Instructions
for running tests are copied here for convenience.

### Running tests

The same checks that run as checks on PR's are part of the repository and can be run locally to verify that changes are valid.
To run tests locally, you'll need `npm`, which is a standard part of any [node.js installation](https://nodejs.org/en/download/).

First you'll need to install everything with npm once. Just navigate to the root of this repository and on
your command line run:

```bash
npm install
```

Then to check markdown formatting and test the examples against the JSON schema, you can run:

```bash
npm test
```

This will spit out the same texts that you see online, and you can then go and fix your markdown or examples.

If the tests reveal formatting problems with the examples, you can fix them with:

```bash
npm run format-examples
```
