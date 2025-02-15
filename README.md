# Address PIN Code Validator

## Overview
This Python program validates whether a given free-flowing address has the correct PIN code corresponding to the mentioned locality. It uses the free API provided by [Postal PIN Code](http://www.postalpincode.in/Api-Details) to verify the locality details associated with the PIN code.

## Features
- Extracts the PIN code from a given address.
- Fetches the correct locality details using the API.
- Validates if the PIN code matches the locality in the address.
- Returns appropriate messages based on validation results.

## Prerequisites
- Python 3.x
- `requests` module (install using `pip install requests`)

## Installation
1. Clone the repository or download the script.
2. Install dependencies using:
   ```sh
   pip install requests
   ```
3. Run the script and input addresses for validation.

## Usage
```python
from validate_pincode import validate_address

address = "2nd Phase, 374/B, 80 Feet Rd, Mysore Bank Colony, Banashankari 3rd Stage, Srinivasa Nagar, Bengaluru, Karnataka 560050"
print(validate_address(address))
```

## Test Cases & Expected Output

| # | Input Address | Expected Output |
|---|--------------|----------------|
| 1 | `"2nd Phase, 374/B, 80 Feet Rd, Mysore Bank Colony, Banashankari 3rd Stage, Srinivasa Nagar, Bengaluru, Karnataka 560050"` | `Valid address.` |
| 2 | `"2nd Phase, 374/B, 80 Feet Rd, Mysore Bank Colony, Banashankari 3rd Stage, Srinivasa Nagar, Bengaluru, Karnataka 560095"` | `Invalid address: PIN code does not match locality.` |
| 3 | `"374/B, 80 Feet Rd, State Bank Colony, Banashankari 3rd Stage, Srinivasa Nagar, Bangalore. 560050"` | `Valid address.` |
| 4 | `"Colony, Bengaluru, Karnataka 560050"` | `Invalid address: PIN code does not match locality.` |
| 5 | `"Unknown Place, XYZ District, ABC State 123456"` | `Invalid PIN code: 123456` |




