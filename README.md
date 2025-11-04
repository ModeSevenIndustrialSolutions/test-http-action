# HTTP API Tool - Test Repository

This repository contains test workflows for the [http-api-tool-docker](https://github.com/modeseven-lfreleng-actions/http-api-tool-docker) GitHub Action.

**Note**: This test repository uses the development branch `add-uvx-deploy` from the fork `modeseven-lfreleng-actions/http-api-tool-docker` for testing purposes.

## Purpose

This repository is used to test and validate both deployment modes of the HTTP API Tool action:
- **UVX mode** (default): Fast deployment using `uvx` to run the tool directly from PyPI
- **Docker mode**: Containerized deployment using the published Docker image from GHCR

## Workflows

### Test Deployment Modes

**Workflow**: `.github/workflows/test-deployment-modes.yaml`

This workflow runs on manual trigger (`workflow_dispatch`) and performs parallel testing of both deployment modes against the Linux Foundation website.

**Features**:
- ✅ Two parallel jobs testing the same endpoint
- ✅ Configurable URL and expected HTTP status code via workflow inputs
- ✅ Detailed performance metrics in job summaries
- ✅ Comparison of both deployment modes

**Default Test**:
- URL: `https://linuxfoundation.org`
- Expected HTTP Code: `200`
- Retries: `3`

## Running the Tests

1. Go to the **Actions** tab in this repository
2. Select "Test HTTP API Tool - Both Deployment Modes"
3. Click "Run workflow"
4. (Optional) Customize the URL and expected status code
5. Click "Run workflow" to start

## Results

After the workflow completes, check the job summaries for:
- HTTP status code received
- Success/failure status
- Total request time
- Connection time
- Time delay (retry wait time)

The workflow will show which deployment mode (if any) performs better for the given endpoint.

## Action Repository

This test repository uses:
- **Fork**: [modeseven-lfreleng-actions/http-api-tool-docker](https://github.com/modeseven-lfreleng-actions/http-api-tool-docker)
- **Branch**: `add-uvx-deploy`

Official repositories:
- GitHub: [lfreleng-actions/http-api-tool-docker](https://github.com/lfreleng-actions/http-api-tool-docker)
- Docker Image: [ghcr.io/lfreleng-actions/http-api-tool-docker](https://ghcr.io/lfreleng-actions/http-api-tool-docker)
- PyPI Package: [http-api-tool](https://pypi.org/project/http-api-tool/)

## License

Apache-2.0