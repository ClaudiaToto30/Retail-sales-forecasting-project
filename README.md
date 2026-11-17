# Forecasting U.S. Retail Sales - Final Project

Final project - Business Forecasting, Fall 2026 | Claudia Toto

## The Problem
Forecast monthly U.S. retail sales for the next 12 months (Aug 2026 - Jul 2027) to support inventory, staffing and budget decisions, especially for the holiday season.

## Deliverables
| File | Audience | Description |
|---|---|---|
| `Retail_Sales_Forecast_Presentation.pptx` | Class / team | Problem, data, methodology, exploration, model judgement, recommendation, forecast and ideas to improve |
| `Retail_Sales_Forecast_Management_Summary.docx` | Management | 1-page summary: forecast and conclusion, methodology, data insights, limitations and recommendations |
| `Project_Forecast_MRTSSM44000USN.Rmd` | Technical | R Markdown code for the full analysis |
| `Project_Forecast_MRTSSM44000USN.html` | Technical | Knitted report with all outputs and plots |
| `MRTSSM44000USN.xlsx` | Data | Monthly retail sales downloaded from FRED |

## Data
- **Source:** FRED, Federal Reserve Bank of St. Louis / U.S. Census Bureau
- **Series:** MRTSSM44000USN - Retail Sales: Retail Trade (millions of dollars, not seasonally adjusted)
- **Period:** January 1992 - July 2026 (415 monthly observations)

## Methodology
- **Models compared:** Mean, Naive, Seasonal Naive, ETS, Holt-Winters, STL + ETS, ARIMA
- **Test:** models trained on Jan 1992 - Jul 2025 and evaluated on the last 12 months (Aug 2025 - Jul 2026)
- **Selection measure:** MAPE on the test set, supported by RMSE, MASE and residual analysis (Ljung-Box)

## Results
| Model | Test MAPE |
|---|---|
| **ARIMA(4,1,0)(0,1,1)[12]** | **1.51%** |
| Holt-Winters | 1.78% |
| ETS | 2.35% |
| STL + ETS | 2.83% |
| Seasonal Naive | 4.24% |
| Naive | 5.02% |
| Mean | 47.80% |

## Forecast (ARIMA)
- **Next 12 months:** about $8.17 trillion (+5.4% vs. the previous 12 months)
- **December 2026 peak:** $745.8 billion (95% interval: $718B - $774B), about +4% vs. December 2025
- **January 2027:** about $626 billion (about 16% below December)
