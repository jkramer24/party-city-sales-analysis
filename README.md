Party City Sales Forecast & Store Analysis

Overview

This project uses a 1% sample of US consumer transaction data to forecast Party City's Q4 2022 Brand Comparable Sales and identify underperforming store locations as candidates for closure. The analysis was completed in Python using Pandas, NumPy, SciPy, Matplotlib, and GeoPandas.

Same Store Sales Forecast

Monthly transaction data was aggregated to the quarterly level and filtered to same store pairs, meaning stores with sales data in both the current quarter and the same quarter one year prior. Rather than averaging store level year over year changes, which can be skewed by small stores with volatile sales, total sales across all qualifying stores were summed before calculating the percent change. This approach weights larger stores more heavily and produces a more stable aggregate estimate.
The transaction based estimates were validated against Party City's officially reported Brand Comparable Sales figures using OLS regression. The model produced an R² of 0.83 and a p-value of 0.0007, confirming a statistically significant relationship between the transaction estimates and the reported figures. The regression equation was then used to adjust the raw estimate for any systematic bias in the sample. The final Q4 2022 forecast is -11.84%, compared to the last reported quarter of -3.20% in Q3 2022.

Store Closure Analysis

A four factor scoring model was built to rank each store as a closure candidate. The four factors are average quarterly sales, sales trend from H1 to H2 2022, proximity to the nearest Party City location calculated using the Haversine formula, and state level market strength. Each factor was converted to a percentile rank between 0 and 1 and averaged into a single closure score. Stores with the lowest scores are the strongest closure candidates.
Of the 100 lowest scoring stores, California, Illinois, Indiana, Pennsylvania, and Florida accounted for 58 locations. Texas was the strongest market with 29 stores in the top 100. The results are visualized on a map showing store health scores across the continental US.

Tools & Libraries

Python, Pandas, NumPy, SciPy, Matplotlib, GeoPandas

 
