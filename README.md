# Broker Catalog & Zip Code Searcher

This project contains a Node-RED application that provides two main functionalities:
1. A **Broker Catalog**, which fetches a list of brokers from the BrazilAPI and displays them on a web page.
2. A **Zip Code Searcher**, which allows users to search for details of a provided zip code (CEP) using the BrazilAPI.

## Features
- **Broker Catalog**: Lists all available brokers in the format `${Nome_Social} - ${Municipio} / ${CNPJ}`.
- **Zip Code Searcher**:
  - Allows searching for CEP using a route parameter (e.g., `/zipcode/12345678`).
  - Allows searching for CEP using an input field.
  - Displays detailed information about the CEP (street, neighborhood, city, state, etc.).
  - Shows a popup notification if the CEP is not found.
- **Styling**: The web pages are styled using the Bootstrap framework for a clean and responsive design.

## Prerequisites

Before running the project, ensure that you have the following installed:

- [Node.js](https://nodejs.org/en/)
- [Node-RED](https://nodered.org/docs/getting-started/local)
- An active internet connection to access the [BrazilAPI](https://brasilapi.com.br/)

## Installation

1. Clone this repository:

    ```bash
    git clone https://github.com/vfmoraes/BrokerCatalog-ZipCodeSearcher.git
    ```

2. Navigate to the project directory:

    ```bash
    cd BrokerCatalog-ZipCodeSearcher
    ```

3. Install Node-RED if you haven't already:

    ```bash
    npm install -g node-red
    ```

4. Start Node-RED:

    ```bash
    node-red
    ```

5. Open the Node-RED editor by visiting `http://localhost:1880` in your browser.

6. Import the project flows:
    - Open the Node-RED editor.
    - Click on the hamburger menu in the top-right corner.
    - Select **Import**.
    - Paste the contents of the `flows.json` file from this repository.

7. Deploy the flows.

## Usage

### Broker Catalog

1. Access the Broker Catalog by navigating to:

    ```
    http://localhost:1880/brokers
    ```

2. You will see a list of brokers fetched from the [BrazilAPI](https://brasilapi.com.br/docs#tag/Corretoras), displayed in the format:

    ```
    ${Nome_Social} - ${Municipio} / ${CNPJ}
    ```

### Zip Code Searcher

#### Option 1: Route Parameter

1. Use the following URL format to search for a CEP:

    ```
    http://localhost:1880/zipcode/{cep}
    ```

    Replace `{cep}` with the actual zip code you want to search for (e.g., `http://localhost:1880/zipcode/89010025`).

2. The page will display details for the given CEP, such as:
    - Street
    - Neighborhood
    - City
    - State

3. If the CEP is not found, a pop-up notification will appear and an error message will be displayed on the page.

#### Option 2: Input Field

1. Access the form to search for a CEP by navigating to:

    ```
    http://localhost:1880/zipcode
    ```

2. Enter a valid CEP in the input field and click **Search**.

3. The page will display the details for the entered CEP, or show a pop-up notification if the CEP is not found.
