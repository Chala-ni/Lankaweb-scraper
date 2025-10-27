# Automated Real Estate Scraper for LankaPropertyWeb

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

This project is a powerful and maintainable web scraper designed to automate the extraction of real estate data from LankaPropertyWeb.com. It uses Python and the Playwright library to mimic human behavior, navigate the website, gather information across multiple pages, and save the results into a structured Excel file.

This project demonstrates skills in web automation, data extraction, handling dynamic web pages, and writing clean, modular code.

## Key Features

- **Automated Navigation**: The script launches a browser and automatically navigates from the homepage to the "Land" listings category.
- **Multi-Page Scraping**: It intelligently handles pagination by finding and clicking the "next" button to continuously scrape data from every page in the category.
- **Dual-Level Data Extraction**:
  - **Summary Data**: Scrapes key information from the search results page (status, title, location, price, and detail page link).
  - **Detailed Data**: Navigates to each individual property link to extract more detailed information (full address, seller name, property type, land size, and full description).
- **Structured Output**: All scraped data is saved into a clean, multi-sheet Excel file (`.xlsx`), with separate sheets for summary and detailed views.
- **Modular and Maintainable Design**: The project is split into logical files:
  - `scraper.py`: Core automation and scraping logic.
  - `elements.yml`: Stores all CSS selectors, allowing for easy updates if the website layout changes without altering the Python code.
  - `excel_writer.py`: A dedicated module for handling all Excel file operations.
  - `config.py`: A simple configuration file to toggle settings like headless mode.


## Technologies Used

- **Python**: The core programming language.
- **Playwright**: For robust browser automation and interaction with dynamic web pages.
- **PyYAML**: To manage UI selectors in a clean, separate `.yml` file.
- **OpenPyXL**: For creating and writing to the final `.xlsx` Excel file.

## Project Structure

```
/
├── scraper.py         # Main scraping logic and browser automation.
├── elements.yml       # All CSS and XPath selectors for easy maintenance.
├── excel_writer.py    # Module to handle all Excel writing operations.
├── config.py          # Basic configuration (e.g., headless mode).
└── requirements.txt   # A list of all project dependencies.
```

## Setup and Usage

To run this project on your local machine, follow these steps.

### Prerequisites

- Python 3.8+
- `git` for cloning the repository.

### 1. Create `requirements.txt`

Create a file named `requirements.txt` in the project directory and add the following lines:

```
playwright
pyyaml
openpyxl
```

### 2. Clone the Repository

git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name
```

### 3. Create a Virtual Environment

It's highly recommended to use a virtual environment to manage project dependencies.

# Create the virtual environment
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

### 4. Install Dependencies

Install all the required libraries from your `requirements.txt` file.

pip install -r requirements.txt


### 5. Install Playwright Browsers

Playwright requires you to download browser binaries. This command will do that for you.

python -m playwright install

### 6. Run the Scraper

You are now ready to run the scraper!

python scraper.py

The script will launch a browser window, perform the scraping, and you will see the progress printed in the terminal. Once complete, you will find the `lankapropertyweb_land_listings.xlsx` file in the project directory.

## Configuration

You can modify the `config.py` file to change the scraper's behavior:
- `HEADLESS = True`: The browser will run in the background without a visible UI.
- `HEADLESS = False`: You will see the browser window and can watch the automation in real-time.