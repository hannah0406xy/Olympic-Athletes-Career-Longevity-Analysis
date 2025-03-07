## 📋 Overview

This project analyzes the key determinants of Olympic career longevity using data from Athens 1896 to Rio 2016. By examining various factors that influence how long Olympic athletes remain competitive at the highest level, this analysis provides valuable insights for athletic development programs, sports organizations, and talent identification systems.

## 🎯 Project Objectives

- Identify and quantify key factors influencing Olympic athlete career longevity
- Develop predictive models to forecast athlete career trajectories
- Uncover patterns and trends to inform strategic decisions in athlete development
- Provide evidence-based recommendations for sports organizations and national Olympic committees

## 📊 Dataset

The analysis utilizes a comprehensive dataset containing 271,116 unique athlete-event entries across Olympic Games from 1896 to 2016. The data includes:

- Demographic information (age, gender, country)
- Sport-specific details (sport, event)
- Performance metrics (medals won)
- Physical characteristics (height, weight, BMI)
- Career information (participations, career span)

## 🔍 Methodology

### Data Preprocessing

- Filtered to include 44 well-established sports with at least 20 years of Olympic presence
- Applied sport and gender-specific median imputation for missing values in modern era (post-1960)
- Used broader category medians for historical era (pre-1960) with less reliable record-keeping
- Transformed variables to address skewness and improve model performance

### Feature Engineering & Selection

Selected key features based on statistical significance and practical relevance:

| Variable | Test Statistic | df | p-value | Effect Size |
|----------|---------------|-----|---------|------------|
| Total Medals | F = 7429.0 | 2, 130359 | <0.001 | η² = 0.102 |
| First Age | F = 1233.0 | 2, 130359 | <0.001 | η² = 0.019 |
| BMI | F = 204.4 | 2, 130359 | <0.001 | η² = 0.003 |
| Country Strength | F = 318.1 | 2, 130359 | <0.001 | η² = 0.005 |
| Sport | χ² = 4317.5 | 86 | <0.001 | - |
| Gender | χ² = 287.27 | 2 | <0.001 | - |
| Season | χ² = 611.67 | 2 | <0.001 | - |

### Model Development

**Supervised Learning:**
- Random Forest (500 trees) for capturing non-linear relationships
- Gradient Boosting (300 trees, interaction depth 4, learning rate 0.05) for iterative learning

**Unsupervised Learning:**
- K-means clustering to identify natural athlete groupings
- Principal Component Analysis (PCA) for dimension reduction and visualization
- Silhouette analysis to determine optimal number of clusters

## 🔑 Key Findings

### Predictive Model Performance

| Model | Overall Accuracy | Single Class | Short Class | Long Class |
|-------|-----------------|-------------|------------|------------|
| Random Forest | 78.96% | 98.7% (27,966/28,257) | 21.5% (1,429/6,653) | 35.4% (1,485/4,197) |
| Gradient Boosting | 74.19% | 89.8% (25,377/28,257) | 39.7% (2,639/6,653) | 23.7% (996/4,197) |

### Feature Importance

1. **Country strength**: Athletes from nations with stronger Olympic programs have careers 2.3 years longer on average
2. **Total medals**: Performance success strongly correlates with extended careers
3. **Sport type**: Significant variation in career length across different sports
4. **BMI and First age**: Moderate influence on career longevity
5. **Gender and Season**: Minimal impact on career length prediction

### Career Patterns (Clusters)

| Cluster | Size | Key Characteristics |
|---------|------|---------------------|
| One-Time Participants | 46.4% | Single appearance, younger athletes (avg. age 22.76) |
| Older Low Achievers | 16.5% | Few participations, low medal rate, older athletes (avg. age 30.76) |
| Consistent Mid-Level Competitors | 15.5% | Multiple Games (avg. 2.02), moderate success rate |
| Short-Lived High Achievers | 12.3% | Brief careers (0.51 years) but high medal rates (1.20) |
| Dedicated Participants | 6.8% | Long careers (10.44 years), moderate success |
| Elite Veterans | 2.6% | Multiple Games (avg. 3.00), highest medal rate (3.27), extended careers |

## 💡 Implications & Recommendations

### For National Olympic Committees

1. **Strengthen support infrastructure**: The strong correlation between country strength and career longevity highlights the need for comprehensive athlete support systems
2. **Focus on first Olympic cycle**: With 46.4% of athletes making only one Olympic appearance, enhanced support during the first Olympic cycle is critical
3. **Develop sport-specific career planning**: Significant variation in career spans across sports requires tailored career development approaches

### For Athlete Development Programs

1. **Create targeted retention strategies**: Focus on the transition from Short-Lived High Achievers to Elite Veterans
2. **Address mid-career transitions**: Support systems for Older Low Achievers could improve long-term career prospects
3. **Implement sport-specific benchmarks**: Use identified patterns to set realistic career progression targets by sport

## 📈 Future Directions

- Investigate temporal stability of career patterns across Olympic eras
- Explore sport-specific variations in career determinants
- Analyze transition mechanisms between identified athlete clusters
- Develop more sophisticated early-career prediction models

## 👥 Contributors
- Xinyi Wang
