# Coffee-Tasting-Survey-and-Predictive-Analysis
A predictive analytics project utilizing ML models that explores coffee preferences and survey demographics among an enthusiast audience.

## Project Goals and Summary
The specialty coffee industry has seen remarkable growth over the past decade. [The National Coffee Association](https://www.ncausa.org/Newsroom/Specialty-coffee-consumption-hits-14-year-high) reports that specialty coffee consumptions among Americans was up by nearly 84% between 2011 and 2025.

With such an explosive expansion underway, understanding consumer coffee preferences and building customer profiles are critical steps for up-and-coming specialty cafes or roasters looking to break into a competitive market.

The analysis I’ve outlined in this project aims to support such goals by diving into an in-depth survey detailing demographics, coffee habits and personal rankings among enthusiast coffee drinkers. In a real-world application, I could see this data being used to inform which coffees to stock, as well as which groups to directly market towards.

With my own personal background as an avid coffee hobbyist, I aim to shed some additional insight on the results based on my own knowledge of what elements of coffee tend to standout the most.

## Data and Background Information
In this project, I analyzed the results of a survey conducted by James Hoffmann, a leading coffee influencer and the winner of the 2007 Barista Championship. Hoffman and his team began his project in late 2023, surveying around 4,000 people in the U.S. Participants were asked about their various coffee preferences, habits and demographics.

The crux of the survey focused on a sample of four different coffees that participants were provided to taste test:

 - Coffee A: Light Roast, Washed
 - Coffee B: Medium Roast
 - Coffee C: Dark Roast
 - Coffee D: Light Roast, Natural

The difference between Coffee A and D comes down to the processing method. Coffee D's natural process results in fermentation, leading to a more distinct, fruity taste profile. Washed, light roast coffees tend to have more pronounced acidity and citric flavors.

It’s important to note that participation was voluntary, and the survey was announced on Hoffmann's social channels. As a result, the data likely skews towards an audience already familiar or experienced with coffee.



## Central Questions

 - Which coffees have the most widespread appeal? 
 - Can we confirm whether this dataset skews towards a coffee enthusiast audience?
 - Can we predict a coffee preference based on demographic data?
 - Are there customer profiles we can build using this dataset?

## Methods Used

 - Inferential Statistics
 - Data Visualization
 - Machine Learning 
     - Classification 
         - Logistic Regression
         - SVC
         - Random Forest
 - Clustering: KModes
 - Dimensionality Reduction: PCA

## Workflow

 1)	Data Cleaning
 2)	Exploratory Data Analysis
 3)	Preprocessing for ML Techniques
 4)	Classification
 5)	Clustering
 6)	Final Results & Key Insights

## Predictive Analytics & Clustering

### a) Data Preprocessing
Preparations for machine learning required heavy cleaning. Many incomplete rows were dropped and multi-select answers called for custom workflows to decouple them. To ensure clustering could be performed, I filled in missing values using the mode value of each column. 

### a)	Classification
The first portion of the ML process was to build a classification model that could predict sample coffee preferences across A, B, C and D based on survey answers. 

Algorithms used included logistic regression, SVC and Random Forest. These were implemented via the sci-kit learn package.

Ultimately, the results were weak. Accuracy scores landed around 50% across models, no better than random chance. Class imbalance likely played a role in these results, as the model skewed towards a male, coffee-expert audience. It's possible a more expansive survey reaching beyond Hoffmann's core audience would result in better performing models.

### b)	Clustering
Because the survey analysis was entirely based on categorical data, I opted to use K-Modes for the clustering process. Compared to K-Means' distance-based algorithm, K-Modes aims to build clusters based on a dissimilarity measure on each categorical variable. Documentation for the K-Modes package can be found [here.](https://pypi.org/project/kmodes/)

Using the elbow method, the optimal cluster value likely fell around three to five clusters. Dimensionality reduction using PCA was used to visualize the cluster options on a 2D plane. 

After checking the mode values of each cluster’s columns and making use of my own coffee knowledge, I determined that three clusters was a reasonable splitting point for building customer profiles. Those findings are detailed in the key insights section.

## Key Insights
**Enthusiast coffee drinkers prioritize experience first.** Those surveyed reported drinking only one to two cups per day and favored more complicated drinks like pourovers and lattes. Specialty roasters and cafes should focus on premium, high-quality coffees to attract customers seeking a one-of-a-kind expereience.

**Acidic coffees outrank the rest.** Light roast Coffees A and D won out when pitted against the medium and dark roast samples. In taste tests, they ranked the highest on acidity and lowest in bitterness.

**Fruity, light roast coffees are a clear favorite.** The fermented, fruit-forward light roast Coffee D led by a wide margin. That held true even against Coffee A, the other light roast. A pure popularity vote shows similar coffees are set to outperform in a product lineup. 

**Younger, male audiences favor lighter roasts.** In contrast, women are more ambivalent across the board based on sample coffee rankings. Gendered preferences indicate the need for a split marketing and outreach strategy.

**Customer profiles can be split into three key groups.** Using a clustering analysis, the following groups came into focus:

1)	**Specialty Pourover Purist:**
 - Light roast enjoyer
 - Pure pourover expert
 - High spender at home and in the cafe

2)	**Flexible Espresso Aficionado:** 
 - Light to medium roast preference
 - Latte drinker, with milk only
 - Heavily invested in espresso equipment

3)	**Casual Coffee Enjoyer:**
 - Favors medium roast
 - Seeks out lattes with a sweet kick
 - Drinks for the caffeine boost
