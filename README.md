# Slurp AI 🥤

![Slurp AI Logo](https://img.shields.io/badge/Slurp%20AI-Tool%20for%20Scraping%20Documentation-blue?style=flat&logo=github)

Welcome to **Slurp AI**! This tool helps you scrape and consolidate documentation from various websites into a single Markdown file. With Slurp AI, you can streamline your documentation process, making it easier to manage and reference all your resources in one place.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## Features

- **Easy Scraping**: Automatically gather documentation from multiple sources.
- **Consolidation**: Merge all scraped content into a single Markdown file.
- **User-Friendly**: Simple command-line interface for quick access.
- **Customizable**: Adjust settings to fit your specific scraping needs.
- **Cross-Platform**: Works on Windows, macOS, and Linux.

## Installation

To get started with Slurp AI, download the latest release from our [Releases page](https://github.com/Hritik590/slurp-ai/releases). Once downloaded, follow the instructions provided in the release notes to execute the tool.

### Prerequisites

- Python 3.x
- pip (Python package installer)

### Steps to Install

1. **Clone the Repository**: 
   ```bash
   git clone https://github.com/Hritik590/slurp-ai.git
   cd slurp-ai
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Tool**:
   After installation, you can start using Slurp AI by executing the following command:
   ```bash
   python slurp.py
   ```

## Usage

Using Slurp AI is straightforward. Here’s how you can get started:

1. **Set Up Configuration**: Create a configuration file to specify the websites you want to scrape. An example configuration file (`config.json`) might look like this:
   ```json
   {
     "urls": [
       "https://example.com/docs",
       "https://anotherexample.com/api"
     ],
     "output_file": "consolidated_documentation.md"
   }
   ```

2. **Run the Scraper**: Execute the scraper with your configuration:
   ```bash
   python slurp.py config.json
   ```

3. **Check Output**: After running, check the specified output file for your consolidated documentation.

## Contributing

We welcome contributions to Slurp AI! Here’s how you can help:

1. **Fork the Repository**: Click on the "Fork" button at the top right of the page.
2. **Create a Branch**: 
   ```bash
   git checkout -b feature/YourFeature
   ```
3. **Make Changes**: Implement your changes and test them.
4. **Commit Your Changes**:
   ```bash
   git commit -m "Add your message here"
   ```
5. **Push to Your Fork**:
   ```bash
   git push origin feature/YourFeature
   ```
6. **Create a Pull Request**: Go to the original repository and submit your pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Support

If you encounter any issues or have questions, feel free to open an issue on our GitHub page or check the [Releases section](https://github.com/Hritik590/slurp-ai/releases) for updates and fixes.

---

Thank you for using Slurp AI! We hope this tool helps you streamline your documentation processes. Happy scraping! 🥤