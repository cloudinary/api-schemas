# API Schemas

This repository contains publicly accessible OpenAPI schemas for various APIs, each describing endpoints, request/response structures, and relevant documentation.

## Available Schemas

- **Assets API**: Manages Cloudinary assets including images, videos, and raw files with comprehensive upload, retrieval, and management capabilities.
- **Config API**: Handles configuration management including upload presets, metadata fields, streaming profiles, and various settings.
- **Structured Metadata API**: Manages structured metadata fields, rules, and associated data for enhanced asset organization and searchability.
- **Analysis API**: Provides endpoints for performing and retrieving various analytical operations including AI-powered content analysis.
- **Permissions API**: Manages user permissions, roles, and related access controls.
- **Provisioning API**: Handles resource provisioning, management, and related tasks.
- **Video Live Streaming API**: Enables streaming functionalities including live broadcasts and stream management.

## Tools

### 🔍 MCP Operations Viewer

An advanced web-based tool for analyzing and visualizing MCP (Model Context Protocol) operations from OpenAPI schemas.

**👉 [Launch MCP Operations Viewer](https://cloudinary.github.io/api-schemas/mcp-operations-viewer.html)**

#### Features

- **Schema Selection**: Choose from predefined Cloudinary API schemas or upload your own OpenAPI YAML files
- **Comprehensive Analysis**: View detailed information about each API operation including:
  - Operation ID and HTTP method
  - MCP tool names and scopes
  - API summaries and descriptions
  - MCP-specific descriptions
  - Missing MCP configuration detection
- **Advanced Filtering**: Filter operations by category, tool name, scopes, HTTP method, or MCP status
- **Data Export**: Export analysis results to CSV format
- **Interactive Table**: Sortable, searchable DataTable with hover tooltips for long content
- **Real-time Statistics**: Summary cards showing total operations, MCP coverage, and category counts
- **Responsive Design**: Works on desktop and mobile devices

#### Usage

1. **Select a Schema**: Click on one of the predefined schema tabs (Assets, Config, Analysis, etc.) or upload your own YAML file
2. **Analyze Operations**: The table will populate with all API operations and their MCP configurations
3. **Filter Results**: Use the filter dropdowns to narrow down operations by specific criteria
4. **Export Data**: Click the "Export Data" button to download results as CSV
5. **Examine Details**: Hover over cells to see full content for truncated text

#### Technical Details

- **Framework**: Pure HTML/CSS/JavaScript with Bootstrap 5 for styling
- **Data Processing**: Uses js-yaml library for YAML parsing
- **Table Management**: DataTables library for advanced table functionality
- **File Support**: Accepts `.yml` and `.yaml` files
- **Browser Compatibility**: Modern browsers with ES6+ support

#### Configuration

The tool automatically loads schemas listed in `schemas.yml`. To add new schemas:

1. Create a new directory with your schema name
2. Add a `schema.yml` file containing your OpenAPI specification
3. Update `schemas.yml` to include your new schema directory
4. The tool will automatically discover and display your schema

## Interactive Documentation

An interactive documentation viewer is also available:

👉 **[View Interactive Documentation](https://cloudinary.github.io/api-schemas/index.html)**

## How to Use Schemas

Each API schema is provided in YAML format (`schema.yml`) and can be consumed using common OpenAPI viewers:

- [Redocly](https://redocly.com/redoc/)
- [Swagger UI](https://swagger.io/tools/swagger-ui/)
- [Stoplight Elements](https://stoplight.io/open-source/elements)

## Contributing

To add or modify API schemas:

1. Fork this repository
2. Create or update the schema YAML file (`schema.yml`) within the appropriate directory
3. Update the `schemas.yml` configuration file if adding a new schema
4. Test your changes using the MCP Operations Viewer tool
5. Submit a pull request

## License

This repository and its schemas are open-sourced under the [MIT License](LICENSE).
