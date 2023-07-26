# Fern Docs

[![Contributors](https://img.shields.io/github/contributors/fern-api/docs.svg)](https://GitHub.com/dotnet/docs/graphs/contributors/)
[![Pulls-opened](https://img.shields.io/github/issues-pr/fern-api/docs.svg)](https://GitHub.com/dotnet/docs/pulls?q=is%3Aissue+is%3Aopened)
[![Pulls-merged](https://img.shields.io/github/issues-search/fern-api/docs?label=merged%20pull%20requests&query=is%3Apr%20is%3Aclosed%20is%3Amerged&color=darkviolet)](https://github.com/dotnet/docs/pulls?q=is%3Apr+is%3Aclosed+is%3Amerged)

This repository contains the conceptual documentation for [Fern](https://buildwithfern.com), the open source toolkit for designing, building, and consuming REST APIs. The [Fern documentation website](https://buildwithfern.com/docs/intro) is built on Fern's own technology available through the Fern CLI.

Issues pertaining to documentation are tracked in this repository. If you feel there is anything wrong in the documentation, or we are missing something important, feel free to open up an issue and we'd be happy to discuss it!

## Project Structure

This project is built on top of Fern's own documentation generation tooling. This means that the content lives in its own `./fern` directory.

The structure of the documentation, including navigation elements, is outlined in `fern/api/docs/docs.yml`. These are all based on Fern's own built-in docs definitions, available in the main repository.

## Contributions

We welcome contributions to to help complete the documentation and make it more elaborate.

- For smaller contributions, e.g., grammatical corrections or smaller fixes, feel free to open a pull request directly.
- If your contribution is more sizable, e.g., documenting a new feature, please open an issue before starting your work, so we have a chance to review and ask any questions beforehand.
