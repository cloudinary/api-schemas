# Changelog

## 1.4.0 (2026-09-29)


### Features

* **media-generation:** Add notices array to response envelopes
* **media-generation:** Raise the prompt maxLength to 16384 characters


### Bug Fixes

* **media-generation:** Report none instead of unmapped for id-only model family and tier

## 1.3.0 (2026-09-24)


### Features

* **media-generation:** Add 26 models
* **media-generation:** Add the auto model-selection form

## 1.2.1 (2026-09-03)


### Bug Fixes

* **media-generation:** Drop the early-version note from the API description

## 1.2.0 (2026-07-22)


### Features

* **media-generation:** Add `generate_image_from_images`

## 1.1.0 (2026-07-15)


### Features

* **media-generation-api:** Add support for OAuth2 security scheme


### Bug Fixes

* **media-generation-api:** Use global security in endpoints

## 1.0.2 (2026-07-13)


### Bug Fixes

* **media-generation-api:** Document managed_asset as the default target

## 1.0.1 (2026-06-30)


### Bug Fixes

* **media-generation-api:** Mark used_by_request, remaining and limit as required in AddonQuota

## 1.0.0 (2026-06-28)


### Features

* **media-generation-api:** Add OpenAPI schema and release config
* **media-generation-api:** Release cleanup


### Miscellaneous Chores

* **media-generation-api:** Release 1.0.0

## 1.0.0 (2026-05-07)


### Features

* Initial public OpenAPI schema for Image Generation API (media generation)
