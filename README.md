# Domain Analysis Project

This project focuses on analyzing domain names to identify potentially malicious or suspicious ones. It involves various steps such as data preprocessing, feature extraction, and domain expertise analysis.

## Data
The project uses a dataset containing DNS records captured by the Suricata IDS. The dataset includes information about different types of network traffic, including DNS queries. 

## Analysis Steps
1. **Data Preprocessing**: The DNS records are loaded into a DataFrame and filtered to include only DNS queries.
2. **Feature Extraction**: Relevant features such as domain names and DNS types are extracted from the data.
3. **Domain Filtering**: The domain names are filtered to include only those with DNS type A (indicating an address record associated with a domain).
4. **Domain Expertise Analysis**: Each domain is checked against a list of one million TLDs to identify whether it is present in the list.
5. **Creation Date Retrieval**: For domains not found in the list, an attempt is made to retrieve their creation date using WHOIS queries.

## Dependencies
- pandas
- python-whois

## Usage
1. Clone the repository.
2. Install the required dependencies using pip: `pip install -r requirements.txt`.
3. Run the main script: `python main.py`.

## Results
The project generates insights into potentially malicious or suspicious domains based on their presence in the list of one million TLDs and their creation dates. These insights can be used for further investigation or threat detection purposes.

## Results

The analysis produced the following results:

| domain_tld            | isOnList | fecha_creacion           |
|-----------------------|----------|--------------------------|
| aoltw.net             | 1        | 2000-01-10 04:09:19      |
| 22.110phpmyadmin     | 1        | None                     |
| 110phpmyadmin.localdomain | 1   | None                     |
| ntkrnlpa.info         | 1        | 2023-06-27 08:18:55      |
| sql-ledger.org        | 1        | 2000-09-08 16:25:09      |
| backtrack-linux.org   | 1        | 2009-04-29 00:26:42      |
| hackerlabs.vpn        | 1        | None                     |
| bigflickrfeed.com     | 1        | None                     |
| malwarecity.com       | 1        | [2008-02-06 15:42:35, 2008-02-06 00:00:00] |
| cakephp.org           | 1        | 2005-06-13 23:07:32      |
| ecvps.com             | 1        | 2009-05-21 14:24:02      |
| vtlfccmfxlkgifuf.com  | 1        | None                     |
| macromates.com        | 1        | [2003-02-05 00:25:14, 2003-02-04 19:25:14] |
| ejfodfmfxlkgifuf.xyz  | 1        | None                     |

<br>

> **Note:**  
> This is a sample result. Actual results may include false positives and false negatives, so we cannot rely entirely on this classification and must continue further investigation. However, this presents a good technique for achieving the intended analysis.*


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
