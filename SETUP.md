# Setup Instructions

This guide will help you set up your environment and get started with the Tutorial Week 11 analysis.

## Prerequisites

### Required Software

1. **R** (version 4.0 or higher)
   - Download from: https://cran.r-project.org/

2. **RStudio** (recommended but optional)
   - Download from: https://posit.co/download/rstudio-desktop/

### Required R Packages

The following packages will be automatically installed when you run the R Markdown file:

- `AER` - For instrumental variable regression (ivreg)
- `haven` - For reading Stata .dta files
- `dplyr` - For data manipulation
- `ggplot2` - For visualization
- `stargazer` - For regression tables
- `boot` - For bootstrap methods
- `lmtest` - For diagnostic tests
- `sandwich` - For robust standard errors
- `knitr` - For R Markdown rendering
- `kableExtra` - For enhanced tables

You can also install them manually:

```r
install.packages(c("AER", "haven", "dplyr", "ggplot2", "stargazer",
                   "boot", "lmtest", "sandwich", "knitr", "kableExtra"))
```

## Getting Started

### Step 1: Download the Data

Before running the analysis, you need to download the replication data:

1. Navigate to the `data/` directory
2. Read `data/DATA_INSTRUCTIONS.md` for download links
3. Download `maketable5.dta` from one of the sources listed
4. Place it in the `data/` directory

**Quick links:**
- **MIT Data Archive**: https://economics.mit.edu/people/faculty/daron-acemoglu/data-archive
- **OpenICPSR**: https://www.openicpsr.org/openicpsr/project/112564/

### Step 2: Verify Data Location

Make sure your directory structure looks like this:

```
Tutorial-Week-11-Problem-Set-Instrumental-Variable-IV-Analysis-and-RDD/
├── data/
│   ├── DATA_INSTRUCTIONS.md
│   └── maketable5.dta          <- Your downloaded data file
├── Tutorial-Week-11-IV-RDD-Analysis.Rmd
├── README.md
├── SETUP.md (this file)
└── .gitignore
```

### Step 3: Open the R Markdown File

1. Open RStudio
2. Open `Tutorial-Week-11-IV-RDD-Analysis.Rmd`
3. You should see the full analysis template with all questions

### Step 4: Run the Analysis

**Option A: Knit the entire document**
- Click the "Knit" button in RStudio
- This will run all code chunks and create an HTML report

**Option B: Run chunks interactively**
- Use Cmd+Shift+Enter (Mac) or Ctrl+Shift+Enter (Windows) to run each chunk
- This is recommended for development and debugging

## File Descriptions

### Analysis Files

- **`Tutorial-Week-11-IV-RDD-Analysis.Rmd`**: Main R Markdown analysis file
  - Contains all questions from the assignment
  - Includes code for IV estimation, permutation tests, bootstrap, and RDD (optional)
  - Produces HTML output with results

### Data Files

- **`data/maketable5.dta`**: AJR (2001) replication data
  - You need to download this yourself (see data/DATA_INSTRUCTIONS.md)
  - Contains variables for IV analysis of institutions and growth

- **`data/KlasnjaTitiunik-Brazil-data.dta`** (optional): RDD data
  - Only needed if completing the optional RDD section

### Documentation

- **`README.md`**: Assignment instructions and questions
- **`SETUP.md`**: This setup guide
- **`data/DATA_INSTRUCTIONS.md`**: Detailed data download instructions

## Workflow

### Typical Analysis Workflow

1. **Load data** (first code chunk)
2. **Explore data** to understand variable names
3. **Update variable names** in the code if needed
   - The template uses common names (logpgp95, avexpr, logem4)
   - Check your data and adjust if necessary
4. **Run IV analysis** (Q1)
5. **Conduct permutation tests** (Q2a)
6. **Generate bootstrap CIs** (Q2b)
7. **Write conceptual answers** (Q2c, Q3, Q4)
8. **Optional: RDD analysis** (Problem 2)

### Important Variables

Based on the AJR (2001) paper, look for these variables in the data:

- **Outcome (Y)**: `logpgp95` - Log GDP per capita 1995
- **Endogenous (T)**: `avexpr` - Average protection against expropriation risk
- **Instrument (Z)**: `logem4` - Log settler mortality
- **Controls (X)**: `f_french`, `f_brit`, `sjlofr`, `catho80`, `muslim80`, `no_cpm80`, `lat_abst`

**Note:** Variable names may differ slightly. Check with `names(ajr_data)` after loading.

## Troubleshooting

### Problem: Data file not found

**Error message:** `Error: Data file not found`

**Solution:**
1. Make sure you've downloaded `maketable5.dta`
2. Check it's in the `data/` directory
3. Verify the filename is exactly `maketable5.dta` (case-sensitive)

### Problem: Package installation fails

**Solution:**
```r
# Try installing packages one by one
install.packages("AER")
install.packages("haven")
# etc.

# Or try a different CRAN mirror
install.packages("AER", repos = "https://cloud.r-project.org")
```

### Problem: Variable names don't match

**Error message:** Variable names in the code don't exist in the data

**Solution:**
1. After loading data, run: `names(ajr_data)`
2. Update variable names in the "Data Preparation" section
3. Look for the README or documentation in the data download

### Problem: Knitting fails but chunks run fine

**Solution:**
- Try: Session → Restart R
- Clear cache: Delete `*_cache/` folders
- Check that all packages are installed

## Tips for Success

1. **Read the questions carefully** - Each section has specific requirements
2. **Check your data** - Verify variable names before running analysis
3. **Interpret results** - Don't just report numbers, explain what they mean
4. **Comment your code** - Future you will thank present you
5. **Save frequently** - Use Cmd+S / Ctrl+S regularly
6. **Version control** - Commit your work as you progress

## Getting Help

- **R documentation**: `?ivreg` or `help(boot)`
- **AER package vignette**: `vignette("AER")`
- **AJR paper**: Read the original paper for context
- **Albouy paper**: Read the critique for Q4

## Next Steps

Once your setup is complete:

1. ✅ Data downloaded and in `data/` directory
2. ✅ R and RStudio installed
3. ✅ Packages installed
4. ✅ .Rmd file opens without errors

You're ready to start the analysis! Open `Tutorial-Week-11-IV-RDD-Analysis.Rmd` and begin with Q1.

Good luck! 🎓
