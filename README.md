
The Pooled OLS method was selected due to its suitability for analyzing time series data with a single entity, in this case, the city of Toronto. The model assumes no time-invariant characteristics that could bias the results, allowing all variations in the dependent variable to be attributed to the explanatory variables included in the model.

![Insert Image](https://github.com/Emma-the-Analyst/ECONOMIC-IMPACT-OF-FOODTRUCK--TORONTO/blob/main/IMAGES/POOLED%20OLS%20ESTIMATE.png?raw=true)

**Estimation Results**

| Variable | Coefficient | P-Value | Significance |
|----------|-------------|---------|--------------|
| Food Trucks | 3.51 | < 0.05 | Significant |
| Unemployment Rate | 40.37 | < 0.05 | Significant |
| Population | 0.0019 | < 0.05 | Significant |
| Lagged Restaurants | 0.35 | 0.1711 | Not Significant |

The estimation yielded a statistically significant positive relationship between food trucks and restaurants (p < 0.05), with each additional food truck associated with a 3.51-unit increase in active restaurants. The unemployment rate showed a strong positive coefficient of 40.37, indicating that a 1% increase in unemployment is associated with an increase of 40.37 active restaurants. Population also showed a positive but smaller effect. The lagged number of restaurants was not statistically significant (p = 0.1711).

**Post Estimation Tests**

The Durbin-Watson test was conducted to assess the presence of autocorrelation in the residuals. The calculated statistic was 1.3648, indicating the presence of positive autocorrelation, which could affect the efficiency of the parameter estimates.

**Alternative Models**

Alternative models including ARIMA, Arellano-Bond, Two-Stage Least Squares (2SLS), and First Difference methods were evaluated. The ARIMA model failed to establish a direct relationship between variables. The Arellano-Bond model produced lower than expected coefficients and failed autocorrelation tests. The 2SLS approach encountered challenges in selecting the best instrumental variable. The First Difference Test produced invalid R-squared values. The Pooled OLS method emerged as the most appropriate choice for this study.

---

## 3. Recommendations

Based on the findings of this study, the following policy recommendations are proposed to support a balanced and thriving food service industry in Toronto:

**1. Support Collaborative Food Ecosystems**

Policies should encourage partnerships between food trucks and restaurants to maximize their collective impact. Culinary Hubs should be established in high-traffic areas such as Nathan Phillips Square and Harbourfront, where food trucks and restaurants share spaces to create vibrant dining destinations. Integrating food trucks into existing restaurant districts, such as the King Street West area, can enhance the area's appeal to both locals and tourists.

**2. Foster Entrepreneurship in the Food Industry**

Initiatives should be introduced to make entry into the food truck business more accessible. Programs like the City of Toronto's BusinessTO Support Centre could expand to offer specific training modules and funding options for food truck operators. Aspiring entrepreneurs could be offered micro-loans or grants to cover startup costs such as vehicle retrofitting and licensing fees. By targeting underrepresented communities, these programs could diversify Toronto's culinary offerings while driving inclusive economic growth.

**3. Invest in Infrastructure for Food Services**

Designated Food Truck Zones, such as those near Union Station or Harbourfront, should be developed to provide essential utilities like electricity and water while reducing congestion in high-demand areas. Drawing inspiration from successful models like Portland's food truck pods, semi-permanent food truck clusters could be introduced in emerging neighborhoods like Liberty Village or the Distillery District.

**4. Encourage Innovation in Food Services**

Supporting the adoption of technology can ensure the resilience of Toronto's food trucks and restaurants. Incentives should be offered for adopting delivery platforms and emerging trends like cloud kitchens. The city could partner with tech hubs in Toronto, such as MaRS Discovery District, to explore cutting-edge solutions tailored for the food service sector.

**5. Simplify and Modernize Licensing Processes**

Addressing barriers to entry for food trucks in Toronto is crucial. The current annual mobile vending permit fee of $6,377 should be reviewed to make the industry more accessible to small-scale entrepreneurs. An online "Fast-Track Licensing Portal" could be introduced to streamline approvals, reduce wait times, and improve transparency.

---

## 4. Conclusion

This study investigated the economic relationship between food trucks and traditional restaurants in Toronto using 55 years of business licensing data, unemployment statistics, and population estimates. The Pooled OLS regression analysis revealed a statistically significant positive relationship between food trucks and restaurants, with each additional food truck associated with a 3.51-unit increase in active restaurants. This finding challenges the common perception that food trucks pose a threat to traditional restaurants and instead points to a complementary relationship where both sectors thrive alongside each other.

The unemployment rate also showed a strong positive correlation with restaurant activity, suggesting that economic downturns may drive entrepreneurship and demand for affordable dining options. Population growth contributed positively to restaurant counts, reinforcing the role of market size in supporting the food service industry.

The analysis confirms that food trucks and restaurants are complements, not competitors. These findings provide a strong evidence base for policy reforms that support both sectors. By implementing collaborative strategies, reducing regulatory barriers, and investing in infrastructure, Toronto can position itself as a global leader in culinary diversity and innovation.

