# Changelog

All notable changes to the Cloudinary OpenAPI specification are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.5.5] - 2026-05-28

### Added
- **Metadata Rules**: `activate_values` field on a rule's `result` to restrict which datasource option ids are active (accepts `"all"` or `{external_ids, mode}`).
- **Metadata Rules**: `set_mandatory` boolean on a rule's `result` to toggle field mandatoriness.

### Deprecated
- **Metadata Rules**: `enable` action on a rule's `result` — use `disable: false` instead.

### Fixed
- **Metadata Rules**: `apply_value.mode` enum corrected from `[default, force]` to `[default, override, append]` to match the API.
- **Folders**: `create_folder_response` now returns the full `folder` shape (previously only `path` and `name`).

## [0.5.4] - 2026-05-28

### Added
- **Metadata Rules**: `disable` and `hide` boolean fields on a rule's `result`.
- **Metadata Fields**: `hidden_ui` and `excluded_from_search` boolean properties on `restrictions`.

## [0.5.3] - 2026-05-25

### Added
- **Metadata Fields**: `alphabetically_sorted` boolean on metadata fields, enabling case-insensitive alphabetical ordering of datasource options.
- **Search**: `key` label is now required on each `aggregate` range item so buckets carry stable names in the response.

### Changed
- **Search**: `max_results` accepts `0` for aggregation-only queries (previously minimum was `1`).

## [0.5.2] - 2026-05-18

_No schema changes._

## [0.5.1] - 2026-05-07

### Added
- **Initial Backup**: New `POST /initial_backup` and `GET /initial_backup` endpoints to initiate and list initial backup operations.
- **Upload**: New `POST /v1_1/{cloud}/video/concat` endpoint that remuxes an ordered list of video-segment URLs (up to 256) into a single MP4.
- **Upload**: `X-Upload-Part-Number` and `X-Upload-Total-Parts` headers on `/upload_chunked` for uploading parts of uneven size with client-supplied order.

### Changed
- **Upload**: `Content-Range` on `/upload_chunked` is now optional (required only in the default uniform-size flow).

## [0.5.0] - 2026-04-20

### Added
- **Request Bodies**: Missing `description` fields on all `requestBody` definitions across APIs.
- **Shared Components**: Extract `direction_enum`, `state_enum`, `tags_response`, `context_response`, `context_full_response`, `coordinates_response`, and `faces_response` for reuse.
- **Upload**: Consolidate upload parameters into `upload_base_parameters` and `upload_serializable_input` for consistent reuse across `upload` and `explicit` endpoints.
- **Upload Mappings**: Operation-level response examples for create/update/delete/replace endpoints.
- **MCP**: Add `idempotentHint: true` to all `readOnlyHint` operations (including `download-asset-backup`, `test-trigger`).
- **Guidelines**: Expand `open_api_guidelines` with MCP hints, metadata types, build workflow, drift detection, and backward compatibility overlay documentation.

### Changed
- **Audit Reports**: Align response schema property names with backend presenter (`report_id` → `id`, `filter_params` → `params`).
- **Metadata Fields**: Move `required: [type, label]` from the shared `metadata_field` component into the create request body via `allOf`, so the component can be reused for responses and updates.
- **Upload Presets**: `upload_preset_summary.settings` now accepts `oneOf [string, boolean]` to match actual API response types.
- **Folders Search**: `expression` restricted to string-only and `sort_by` to object array, matching backend behavior.
- **Overlay**: Update overlay JSONPath for the new `upload_parameters` wrapper.

### Fixed
- **Speakeasy**: Deduplicate inline enums, remove `contentMediaType`, fix `globals.parameters` null value.
- **Speakeasy**: Flatten `delivery_type_all` path parameter to a single string enum (`delivery_type_all_enum`) so `getResourceByPublicId`, `updateResourceByPublicId`, and `deleteResourcesByPublicId` are no longer skipped by the SDK generator. The `anyOf` variant is retained for request bodies and query parameters.
- **Compat Overlay**: Remove stale `signature_parameters` section.

## [0.4.0] - 2026-02-23

### Added
- **People API**: New endpoints for listing, getting, and updating recognized people (`GET /people`, `GET /people/{id}`, `PUT /people/{id}`).
- **Folder Roles**: New endpoints for managing folder permissions (`GET /folder_operations/invite/{folder_id}`, `POST /folder_operations/invite/{folder_id}`).
- **Triggers**: New `test` endpoint (`POST /triggers/{id}/test`) to verify trigger filters.
- **Upload API**: `animated`, `duration`, `resource_subtype`, `substatus`, and `related_assets` fields to resource responses.
- **Components**: `principal_type`, `folder_role`, `folder_role_assignment`, `permitted_role`, and `success_response` schemas.

### Changed
- **Uploads API**: Delete response description to include "not found" case.
- **Transformations**: `width` and `height` to accept strings (for variable references like `$w`).
- **Search**: `status` enum to include `deleted` and `pending`.

### Fixed
- **Metadata Fields**: `420` response code for concurrent updates.

## [0.3.6] - 2025-11-30

### Fixed
- **Streaming Profiles**: Fix display name in schema.

## [0.3.5] - 2025-11-18

### Added
- **Tools**: Add tool annotations.
- **Provisioning**: Add provisioning API key as an actor.

### Changed
- **MCP**: Drop bloated MCP descriptions.

### Fixed
- **Access Control**: Fix access_control specs.

## [0.3.4] - 2025-09-04

### Fixed
- **Upload**: Fix `access_control` parameter definition.

## [0.3.3] - 2025-09-04

### Changed
- **Documentation**: Improve method descriptions.

### Fixed
- **Search**: Fix `sort_by` value schema.

## [0.3.2] - 2025-08-24

### Added
- **Derived Resources**: Add endpoint to delete derived resources.

### Fixed
- **Linting**: Fix linter issues.
- **Upload**: Fix upload validation.

## [0.3.1] - 2025-07-17

### Added
- **Upload**: Add support for `translate` in `auto_transcription`.
- **Upload Presets**: Add whitelisted params.

### Changed
- **Parameters**: Align shared parameter names and extract parameters.
- **Upload**: Restore `upload_no_resource_type`.

### Deprecated
- **Upload**: Deprecate `callback` parameter.

### Fixed
- **Restore**: Fix OpenAPI restore examples.

## [0.3.0] - 2025-06-19

### Added
- **Auth**: Add `oauth2` support.

## [0.2.5] - 2025-06-15

### Changed
- **Modules**: Rename modules.

## [0.2.4] - 2025-06-12

### Fixed
- **Schema**: Fix schema definition bugs.

## [0.2.3] - 2025-06-12

### Changed
- **MCP**: Keep only `upload-asset` MCP tool.
- **Documentation**: Add examples.

## [0.2.2] - 2025-06-10

### Added
- **Metadata**: Add support for structured metadata module.

## [0.2.1] - 2025-06-09

### Fixed
- **Schema**: Fix schema bug.

## [0.2.0] - 2025-06-09

### Added
- **MCP**: Add MCP descriptions.
- **MCP**: Support uploading local files.
- **MCP**: Enable upload and search in MCP.
