
# CVE Vulnerability Checker

## Overview

The **CVE Vulnerability Checker** is a PowerShell script designed to automate the process of checking Common Vulnerabilities and Exposures (CVEs) associated with specified libraries. By leveraging the NVD (National Vulnerability Database) API, this script retrieves detailed information about vulnerabilities, including severity ratings, descriptions, and suggested mitigation strategies.

## Features

- **Input Flexibility:** Users can specify a text file containing a list of CVE IDs and associated libraries in `.jar` format.
- **Detailed Reporting:** The script generates a comprehensive TXT report that includes CVE details, descriptions, CVSS scores, and recommended actions.
- **Logging Mechanism:** A robust logging system tracks the script's operations, providing insights into both regular and debug-level logs.
- **Error Handling:** The script includes error handling to manage API request failures gracefully, ensuring the user receives meaningful feedback.

## Installation

To use this script, ensure you have PowerShell installed on your machine. You can run the script on any Windows system that supports PowerShell 5.0 or later.

1. Clone this repository to your local machine:
   ```bash
   git clone [https://github.com/TFourie30/CheckCVE.git]
   cd CheckCVE
   ```

2. Open PowerShell and navigate to the script's directory.

## Usage

To execute the script, use the following command in PowerShell:

```powershell
.\CVE-Check.ps1 -cveFilePath "C:\Path\To\Your\CVE-List.txt" [-apiKey "YourApiKey"]
```

- **`-cveFilePath`** (Mandatory): The path to the text file containing CVE IDs and libraries.
- **`-apiKey`** (Optional): Your API key for NVD API access (if required).

### Input File Format

The input file should contain a list of libraries followed by their corresponding CVE IDs. Each entry should be on a new line, with libraries ending in `.jar` and CVE IDs starting with `CVE-`. For example:

```
library1.jar
CVE-2024-1234
library2.jar
CVE-2024-5678
```

### Output

The script generates a TXT report in the same directory as the script, named `CVE-Report-YYYY-MM-DD.txt`, where `YYYY-MM-DD` is the current date. This report contains:

- Library name
- Associated CVE IDs
- Descriptions of each CVE
- Severity ratings and CVSS scores
- Recommended actions for remediation
- General recommended actions for vulnerability management

## Logging

The script features a logging mechanism that records various levels of information (Info, Debug, Error) in a log file named `CVE-Report-YYYY-MM-DD.log`. Debug logs are only shown when the log level is set to "Debug," ensuring that users can focus on essential information during normal execution.

## Rationale Behind Implementation

1. **Ease of Use:** By allowing users to specify a text file, the script accommodates batch processing of multiple CVEs, making it efficient for security teams and developers.
2. **Detailed Reporting:** The focus on providing rich detail in reports helps users understand the vulnerabilities affecting their libraries and take informed actions.
3. **Error Management:** By implementing robust error handling, the script minimizes disruptions and informs users of issues without halting the entire process.
4. **Modular Logging:** The logging structure allows users to monitor script activity, which is crucial for debugging and auditing.


## Contact

For any inquiries or support, feel free to reach out via GitHub or your preferred contact method.

---

Happy scanning!
