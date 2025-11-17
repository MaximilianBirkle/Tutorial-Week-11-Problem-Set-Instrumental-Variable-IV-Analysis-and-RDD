# Data Download Instructions

This directory should contain the replication datasets needed for the tutorial analysis.

## Required Data Files

### 1. AJR (2001) Data: `maketable5.dta`

**Paper**: Acemoglu, D., Johnson, S., & Robinson, J. A. (2001). The Colonial Origins of Comparative Development: An Empirical Investigation. *American Economic Review*, 91(5), 1369–1401.

**Download Sources**:

1. **Primary Source - Daron Acemoglu's MIT Data Archive**:
   - Visit: https://economics.mit.edu/people/faculty/daron-acemoglu/data-archive
   - Look for "The Colonial Origins of Comparative Development: An Empirical Investigation"
   - Download the ZIP file containing replication data
   - Extract `maketable5.dta` to this directory

2. **Alternative Source - AEA Website**:
   - Visit: https://www.aeaweb.org/articles?id=10.1257/aer.91.5.1369
   - Look for "Data and Programs" or "Supplementary Materials"
   - Download and extract to this directory

3. **OpenICPSR**:
   - Visit: https://www.openicpsr.org/openicpsr/project/112564/
   - Download the replication package

4. **Course Google Drive** (if available):
   - Check your course materials for a shared Google Drive folder
   - The instructor may have already prepared `maketable5.dta`

### 2. RDD Data (Optional): `KlasnjaTitiunik-Brazil-data.dta`

**Paper**: Klašnja, M. & Titiunik, R. (2017). "The Incumbency Curse: Weak Parties, Term Limits, and Unfulfilled Accountability." *American Political Science Review*.

**Download Sources**:
- Search for the paper's replication materials on the APSR website or the authors' websites
- Check Harvard Dataverse for political science replication data

## File Structure

After downloading, your data directory should contain:
```
data/
├── DATA_INSTRUCTIONS.md (this file)
├── maketable5.dta
└── KlasnjaTitiunik-Brazil-data.dta (optional)
```

## Verification

Once you've downloaded the files, you can verify they're in the correct location by running:

```r
# In R:
file.exists("data/maketable5.dta")
```

Or in terminal:
```bash
ls -lh data/
```
