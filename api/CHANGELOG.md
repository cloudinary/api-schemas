# Changelog

All notable changes to the Cloudinary OpenAPI specification are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.5.1] - 2026-04-21

### Added
- **Search**: `examples` array on `expression` covering common query shapes.
- **Search**: `x-enum-descriptions` for every `with_field` value.

### Changed
- **Search**: Spell out the Lucene grammar summary on `expression`; note the Tier 2 plan requirement on `aggregate` and on `with_field`'s `image_metadata` / `image_analysis` / `metadata` values; document the `max_results: 0` aggregation-only mode.

### Fixed
- **Search**: Require `key` (1–20 chars, `^[a-zA-Z0-9_-]+$`) on `aggregate` range items so bucket labels for grouping are returned.
- **Search**: Relax `max_results.minimum` from `1` to `0` for aggregation-only queries.

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
