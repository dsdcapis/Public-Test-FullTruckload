# Why is there an LTL spec in the FTL eBOL folder?

`ltl-ebol-2.1.0-openapi.yaml` is **not** a separate FTL standard and is not offered as a download on the docs site. It is a supporting file for the FTL eBOL spec.

The FTL eBOL endpoint accepts a bill of lading in **either** of two formats:

1. **LTL format**: the Digital LTL Council eBOL v2.1.0 request and response.
2. **FTL format**: the Digital FTL Council request and response, defined in `../ftl-ebol.schemas.yaml`.

This file supplies the LTL option. The FTL eBOL spec (`../../ftl-ebol.openapi.yaml`) references three definitions from it:

| Definition | Used for |
|---|---|
| `BOL_Request` | Request body, LTL option |
| `BOL_Response` | 200 response, LTL option |
| `Result_Status_Codes` | 400 error response, LTL option |

When the site is built, these definitions are combined into the single eBOL file people download (`ftl-ebol-v1.0-public-preview.openapi.yaml`) and into the eBOL preview page. **Do not delete this file**: the eBOL build will fail without it.

## Source

This file is a copy of the LTL eBOL v2.1.0 spec from [dsdcapis/less-than-truckload](https://github.com/dsdcapis/less-than-truckload) (`api-specs/eBOL/v2.1.0/ebol.openapi.yaml`), with these small changes:

- The titles `LTL BOL Request` and `LTL BOL Response` are added, so the two options are labeled "LTL" and "FTL" on the preview page.
- One example value is quoted as a string (`'3'`).

If the LTL Council publishes a new eBOL version that FTL should accept, replace this file and update the three references in `ftl-ebol.openapi.yaml`.
