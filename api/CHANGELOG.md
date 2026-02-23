# Changelog

All notable changes to the Cloudinary OpenAPI specification are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
