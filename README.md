# The Breakdown of the Classic Portfolio Hedge: A Comprehensive Markov-Switching Analysis

This repository contains the complete code and analysis for investigating the breakdown of the traditional stock-bond hedge during the high-inflation period of 2022-2023.

## Abstract

Using advanced econometric techniques, we provide quantitative evidence that the fundamental relationship between stocks and Treasury bonds underwent a structural regime change during this period. The stock-bond correlation switched from negative (-0.3) to strongly positive (+0.6), representing a fundamental breakdown of traditional portfolio diversification.

## Key Findings

- Stock-bond correlation regime change from negative to strongly positive during 2022-2023
- Regime change persisted for nearly two years (different from previous crisis periods)
- Traditional 60/40 portfolios experienced unprecedented simultaneous losses
- Markov-switching model successfully identifies two distinct regimes

## Reproducibility

### System Requirements
- R version 4.0 or higher
- RStudio (recommended)
- Internet connection for data downloads

### Setup Instructions

1. **Clone the repository:**
```bash
git clone https://github.com/lusiki/stock-bond-regime-analysis.git
cd stock-bond-regime-analysis
```

2. **Install R dependencies:**
```r
# Install renv if not already installed
if (!require("renv")) install.packages("renv")

# Restore the project environment
renv::restore()
```

3. **Get FRED API Key (free):**
- Visit: https://fred.stlouisfed.org/docs/api/api_key.html
- Add your key to `.Renviron`: `FRED_API_KEY=your_key_here`

4. **Run the analysis:**
```r
# Open and knit the main analysis file
rmarkdown::render("analysis/main_analysis.Rmd")
```

### Expected Runtime
- Data download: ~2 minutes
- Full analysis: ~5-10 minutes
- Markov-switching estimation: ~3-5 minutes

## Data Sources

All data is downloaded programmatically:

- **Stock/Bond Data:** Yahoo Finance via `quantmod` package
  - SPY (SPDR S&P 500 ETF)
  - TLT (iShares 20+ Year Treasury Bond ETF)
- **Macroeconomic Data:** Federal Reserve Economic Data (FRED)
  - Consumer Price Index (CPIAUCSL)
  - Federal Funds Rate (DFF)
  - Unemployment Rate (UNRATE)

**Data Period:** January 1, 2007 - December 29, 2023

## File Structure

```
├── analysis/main_analysis.Rmd     # Main analysis file
├── data/                          # Data storage (populated on first run)
├── output/figures/               # Generated plots
├── output/tables/                # Generated tables
├── renv.lock                     # Package versions
└── functions/                    # Helper functions
```

## Key Results

### Regime Characteristics
- **Hedge Regime:** Negative correlation (-0.3), normal volatility
- **Breakdown Regime:** Positive correlation (+0.6), elevated volatility
- **2022-2023:** 80%+ probability of breakdown regime

### Economic Interpretation
The regime change coincides with the transition from deflationary/liquidity crises to inflation-driven monetary tightening, representing a fundamental shift in market dynamics.

## Methodology

- **Econometric Model:** Bivariate Markov-Switching Model
- **Software:** R with MSwM package
- **Statistical Tests:** ARCH-LM, Jarque-Bera for model justification
- **Robustness:** Multiple rolling correlation windows

## Citation

If you use this analysis, please cite:

```bibtex
@misc{regime_analysis_2024,
  author = {Financial Risk Analyst},
  title = {The Breakdown of the Classic Portfolio Hedge: A Comprehensive Markov-Switching Analysis},
  year = {2024},
  url = {https://github.com/lusiki/stock-bond-regime-analysis}
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For questions or suggestions:
- GitHub Issues: [Create an issue](https://github.com/yourusername/stock-bond-regime-analysis/issues)
- Email: your.email@domain.com

## Acknowledgments

- Federal Reserve Economic Data (FRED) for macroeconomic time series
- Yahoo Finance for financial market data
- R Core Team and package maintainers

---

*Last updated: [Current Date]*
