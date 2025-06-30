# Advanced Shell Scripting – Pokémon API Automation

## Repository

**GitHub repository:** ALXprodev-Devops
**Directory:** Advanced\_shell

---

## Project Overview

This project automates the process of making API requests to the Pokémon API, extracting and summarizing data using advanced shell scripting with robust error handling and parallel processing. It practices:

* API request automation
* Advanced text manipulation using `jq`, `awk`, `sed`
* Batch processing with error handling
* Parallel data fetching
* Generating human-readable and CSV summaries

This is aligned with **ALX Advanced Shell Scripting module**.

---

## Tasks Included

### 0️⃣ API Request Automation (`apiAutomation-0x00`)

* Makes an API request to fetch **Pikachu data** from the Pokémon API.
* Saves response to `data.json`.
* Logs errors to `errors.txt` if the request fails.
* Uses `curl` for API requests.

**Run example:**

```bash
./apiAutomation-0x00
jq . < data.json | head -n 50
```

---

### 1️⃣ Extract Pokémon Data (`data_extraction_automation-0x01`)

* Uses `jq`, `awk`, and `sed` to extract Pikachu’s:

  * Name
  * Height
  * Weight
  * Type
* Outputs in a human-readable sentence:

> "Pikachu is of type Electric, weighs 6kg, and is 0.4m tall."

**Run example:**

```bash
./parse_pikachu
```

---

### 2️⃣ Batch Pokémon Data Retrieval (`batchProcessing-0x02`)

* Loops through a list of Pokémon:

  * Bulbasaur
  * Ivysaur
  * Venusaur
  * Charmander
  * Charmeleon
* Fetches API data for each and saves into `pokemon_data/<pokemon>.json`.
* Includes delay to handle potential rate limiting.

**Run example:**

```bash
./fetch_multiple_pokemon
```

---

### 3️⃣ Summarize Pokémon Data (`summaryData-0x03`)

* Reads all JSON files from `pokemon_data/`.
* Extracts name, height, and weight.
* Generates a **CSV report (`pokemon_report.csv`)**.
* Uses `awk` to calculate average height and weight.

**Run example:**

```bash
./pokemon_report
```

**Sample CSV:**

```
Name,Height (m),Weight (kg)
Bulbasaur,0.7,6.9
Charmander,0.6,8.5
...
```

---

### 4️⃣ Error Handling and Retry Logic (`batchProcessing-0x02`)

* Enhances Task 2 to include retry logic:

  * Retries failed API requests up to 3 times before logging and skipping.
  * Handles network errors and invalid Pokémon names gracefully.

**Run example:**

```bash
./fetch_multiple_pokemon
```

---

### 5️⃣ Parallel Data Fetching (`batchProcessing-0x04`)

* Fetches data for Pokémon in **parallel** to speed up retrieval:

  * Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon
* Manages background processes efficiently.
* Ensures all processes complete before summarizing or proceeding.

**Run example:**

```bash
./fetch_parallel_pokemon
```

---

### 6️⃣ Manual Review

Scripts will undergo manual QA to ensure:

* Correct data retrieval
* Clean, readable outputs
* Robust error handling
* Efficient use of shell scripting best practices

---

## Usage Notes

✅ Ensure all scripts are executable:

```bash
chmod +x script_name
```

✅ Dependencies:

* `curl`
* `jq`
* `awk`
* `sed`

✅ Ensure internet connectivity for API requests.

✅ Validate outputs using `jq` for readable JSON views.

---

## Progress & Next Steps

* [x] Script skeletons prepared for each task.
* [ ] Manual QA review for all scripts.
* [ ] Automated checks validation.

---

