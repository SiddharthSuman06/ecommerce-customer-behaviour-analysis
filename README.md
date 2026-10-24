# Berlin Restaurant Market Analysis

Berlin has around 6,600 rated restaurants on TripAdvisor, and two thirds of them have never claimed their page. I wanted to see what separates the well-rated ones from the rest, and what that might mean for delivery platforms like Wolt, Lieferando or Delivery Hero that work with these restaurants every day.

I spent years in kitchens and advising restaurant owners before moving into data, so this one is close to home.

![Ratings overview](images/1_ratings_overview.png)

## What I found

**1. Claimed restaurants get far more reviews, and slightly better ratings.**
Restaurants that have claimed their TripAdvisor page get about 3.4x more reviews (around 162 vs 48). Their average rating is 0.14 stars higher (4.25 vs 4.10). That gap is statistically clear but small: Cohen's d is around 0.2, and the two distributions overlap almost completely.

This is a comparison, not an experiment. Popular restaurants may simply be more likely to claim their page, so I can't say claiming causes the difference.

![Claimed vs unclaimed](images/2_claimed_vs_unclaimed.png)

**2. Service, food and value all go together with higher ratings. Atmosphere much less so.**
The three are about equally linked to the overall rating. Atmosphere has a much weaker link. A simple place with good service and fair prices does just as well as a beautiful one.

![Correlation matrix](images/5_correlation_matrix.png)

**3. Mid-range is the most crowded segment and rates lowest.**
Half of all Berlin restaurants sit in the €€-€€€ band. Both budget (€) and fine dining (€€€€) rate higher on average.

![Price vs performance](images/3_price_vs_performance.png)

**4. The most common cuisines aren't the best rated.**
European, café and German places dominate by count. Cafés, Mediterranean and Asian restaurants rate a bit higher on average. The differences are small, so I treat this as a pointer rather than a ranking.

![Cuisines](images/4_cuisines.png)

**5. Berlin doesn't need white tablecloths.**
Mustafa's Gemuese Kebab, a cheap street food stand, is the fourth most-reviewed restaurant in the city, with over 4,300 reviews and a 4.5 rating.

## What I'd recommend to a delivery platform

- The review gap is the bigger story. Helping restaurant partners claim and manage their profiles looks worthwhile, but the honest way to find out is a small pilot: offer onboarding support to a random half of unclaimed partners and compare after a few months.
- When coaching partners, start with service and value for money rather than decor or longer opening hours.

## What I changed in October 2026

I went back through the notebook and fixed a few things. The notebook has a note at each fix:

- I originally wrote that claimed restaurants rate "14% higher". The gap is 0.14 stars, which is about 3.5%.
- The Berlin filter was also picking up a town called Berlingen.
- I had filled missing food, service, value and atmosphere scores with the median before running correlations. About half were missing, so that flattened the results. Now the correlations only use real scores.
- Cuisine matching used partial text matches, so "European" also counted "Central European". It now matches exactly.
- I stopped calling the claimed vs unclaimed comparison an A/B test, switched to Welch's t-test and added an effect size.

## How to run it

1. Download `tripadvisor_european_restaurants.csv` from [Kaggle (TripAdvisor European Restaurants)](https://www.kaggle.com/datasets/stefanoleone992/tripadvisor-european-restaurants).
2. Put it in a folder called `data/` next to the notebook (or in your Google Drive if you use Colab).
3. Install the packages and open the notebook:

```bash
pip install -r requirements.txt
jupyter notebook Berlin_Restaurant_Market_Analysis.ipynb
```

## Tools

Python, pandas, NumPy, Matplotlib, Seaborn, SciPy (Welch's t-test, Cohen's d, confidence intervals).

## Limitations

- Everything here is correlation. Nothing was randomised.
- TripAdvisor leans towards tourists, so local favourites may be under-represented.
- Ratings are rounded to half stars, which hides a lot of variation.

## Author

Siddharth Suman, Data Analyst, Berlin
[LinkedIn](https://www.linkedin.com/in/siddharthsuman06)
