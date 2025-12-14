# Advanced Shell Scripting

## 0. API Request Automation

### Description
Automates the process of making API requests to the Pokémon API and saving the results to a file.

### File: `apiAutomation-0x00`

**Features:**
- Fetches Pikachu data from Pokemon API
- Saves response to `data.json`
- Logs errors to `errors.txt` if request fails

### Usage
```bash
chmod +x apiAutomation-0x00
./apiAutomation-0x00
```

### Output

**Success:**
```bash
Success! Data saved to data.json
```

**View data:**
```bash
jq . < data.json | head -n 50
```

### Requirements
- `curl` - for API requests
- `jq` - for JSON formatting (optional)

### Install dependencies
```bash
sudo apt update
sudo apt install curl jq -y
```

## Author
Billy Mwangi
