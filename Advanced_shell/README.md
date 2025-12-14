# Advanced Shell Scripting - Pokemon API Automation

A collection of shell scripts for automating Pokemon API requests, data extraction, and processing.

## Tasks Overview

### Task 0: API Request Automation
**File:** `apiAutomation-0x00`

Automates API requests to the Pokémon API and saves results.

```bash
./apiAutomation-0x00
```

**Output:**
- `data.json` - Pikachu data from Pokemon API
- `errors.txt` - Error logs (if request fails)

---

### Task 1: Extract Pokémon Data
**File:** `data_extraction_automation-0x01`

Extracts specific data from JSON using jq, awk, and sed.

```bash
./data_extraction_automation-0x01
```

**Output:**
```
Pikachu is of type Electric, weighs 6kg, and is 0.4m tall.
```

---

### Task 2: Batch Pokémon Data Retrieval
**File:** `batchProcessing-0x02`

Fetches data for multiple Pokemon with error handling and retry logic.

**Features:**
- Loops through Pokemon list
- Saves each to separate JSON file
- Retry mechanism (up to 3 attempts)
- Rate limiting with delays
- Error logging

```bash
./batchProcessing-0x02
```

**Pokemon fetched:**
- Bulbasaur
- Ivysaur
- Venusaur
- Charmander
- Charmeleon

**Output:**
- `pokemon_data/*.json` - Individual Pokemon data files
- `fetch_errors.txt` - Error log

---

### Task 3: Summarize Pokémon Data
**File:** `summaryData-0x03`

Generates CSV report with Pokemon statistics.

```bash
./summaryData-0x03
```

**Features:**
- Reads all JSON files from Task 2
- Extracts name, height, weight
- Generates CSV report
- Calculates average height and weight

**Output:**
- `pokemon_report.csv` - CSV summary
- Console output with averages

---

### Task 4: Parallel Data Fetching
**File:** `batchProcessing-0x04`

Fetches Pokemon data in parallel for improved performance.

```bash
./batchProcessing-0x04
```

**Features:**
- Parallel processing using background processes
- Process management and synchronization
- Faster data retrieval
- Error handling

**Output:**
- `pokemon_data/*.json` - Pokemon data files
- `parallel_fetch_errors.txt` - Error log

---

## Requirements

### System Requirements
- Ubuntu 20.04 LTS or later
- Bash shell

### Dependencies
```bash
sudo apt update
sudo apt install curl jq -y
```

- **curl** - API requests
- **jq** - JSON parsing
- **awk** - Text processing
- **sed** - Stream editing

---

## Installation

1. Clone the repository:
```bash
git clone https://github.com/BillyMwangiDev/ALXprodev-Devops.git
cd ALXprodev-Devops/Advanced_shell
```

2. Make scripts executable:
```bash
chmod +x apiAutomation-0x00
chmod +x data_extraction_automation-0x01
chmod +x batchProcessing-0x02
chmod +x summaryData-0x03
chmod +x batchProcessing-0x04
```

---

## Usage Examples

### Complete Workflow

```bash
# Step 1: Fetch Pikachu data
./apiAutomation-0x00

# Step 2: Extract and display Pikachu info
./data_extraction_automation-0x01

# Step 3: Batch fetch multiple Pokemon
./batchProcessing-0x02

# Step 4: Generate summary report
./summaryData-0x03

# Step 5: Parallel fetch (alternative to step 3)
./batchProcessing-0x04
```

### View Results

```bash
# View Pikachu data
jq . < data.json | head -n 50

# View batch fetched data
jq . < pokemon_data/bulbasaur.json | head -n 30

# View CSV report
cat pokemon_report.csv

# Check for errors
cat fetch_errors.txt
```

---

## Project Structure

```
Advanced_shell/
├── apiAutomation-0x00              # Task 0: API request
├── data_extraction_automation-0x01  # Task 1: Data extraction
├── batchProcessing-0x02             # Task 2: Batch fetch with retry
├── summaryData-0x03                 # Task 3: Summary report
├── batchProcessing-0x04             # Task 4: Parallel fetch
├── data.json                        # Pikachu data
├── pokemon_data/                    # Batch fetched data
│   ├── bulbasaur.json
│   ├── ivysaur.json
│   ├── venusaur.json
│   ├── charmander.json
│   └── charmeleon.json
├── pokemon_report.csv               # Summary report
├── errors.txt                       # Error logs
├── fetch_errors.txt                 # Batch fetch errors
└── parallel_fetch_errors.txt        # Parallel fetch errors
```

---

## API Reference

**Pokemon API:** https://pokeapi.co/

**Endpoints used:**
- `https://pokeapi.co/api/v2/pokemon/{name}` - Get Pokemon data

---

## Troubleshooting

### Error: curl command not found
```bash
sudo apt install curl -y
```

### Error: jq command not found
```bash
sudo apt install jq -y
```

### Error: Permission denied
```bash
chmod +x script_name
```

### Error: data.json not found
Run Task 0 first:
```bash
./apiAutomation-0x00
```

### API Rate Limiting
Scripts include delays between requests. If you encounter rate limiting:
- Increase delay in scripts
- Wait a few minutes between runs

---

## Author

**Billy Mwangi**
- GitHub: [@BillyMwangiDev](https://github.com/BillyMwangiDev)
- Repository: [ALXprodev-Devops](https://github.com/BillyMwangiDev/ALXprodev-Devops)

---

## License

This project is part of ALX DevOps training program.

---

## Acknowledgments

- [Pokemon API](https://pokeapi.co/) for providing free Pokemon data
- ALX Africa for the project requirements
