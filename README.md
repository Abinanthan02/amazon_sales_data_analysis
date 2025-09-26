Amazon Product Sales Analysis & Recommendation System
This project performs Exploratory Data Analysis (EDA) and builds a value-based product recommendation system using Amazon product data. Since actual sales figures are not available, we use proxy metrics like rating count, discount percentage, and customer ratings to infer product popularity and value.

📁 Dataset Overview
File: amazon.csv
Source: Amazon India (scraped public data)
Rows: ~500+ products
Key Columns:
product_name, category, brand (extracted)
discounted_price, actual_price, discount_percentage
rating, rating_count
review_title, review_content (for future sentiment analysis)
⚠️ Note: This dataset does NOT contain actual sales volume or revenue. 

🎯 Project Goals
Clean and preprocess Amazon product data.
Analyze price, discount, and rating trends by category.
Identify best-value products using a custom value_score.
Generate actionable insights for consumers and sellers.
Output visualizations and ranked product lists.
🛠️ Tech Stack
Python 3.8+
Libraries:
pandas, numpy → Data manipulation
matplotlib, seaborn → Visualization
re → Text cleaning
📂 Project Structure


1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
amazon-sales-analysis/
│
├── amazon.csv                 # Input dataset
├── amazon_analysis.py         # Main analysis script
├── README.md                  # This file
│
├── outputs/
│   ├── top_value_products.csv
│   ├── category_summary.csv
│   ├── high_value_deals.csv
│   ├── rating_dist.png
│   ├── discount_vs_rating.png
│   └── price_dist.png
│
└── requirements.txt           # Dependencies
▶️ How to Run
1. Clone or download the project
bash


1
2
git clone https://github.com/your-username/amazon-sales-analysis.git
cd amazon-sales-analysis
2. Install dependencies
bash


1
pip install -r requirements.txt
3. Run the analysis
bash


1
python amazon_analysis.py
✅ Make sure amazon.csv is in the same directory as the script. 

4. View results
Check the outputs/ folder for:

CSV reports (top_value_products.csv, etc.)
PNG visualizations
📈 Key Features
Robust data cleaning for prices, ratings, and discounts
Custom value score:
value_score = rating × log(rating_count) × (1 + discount/100)
Category-wise insights (e.g., Cables, TVs, Smartwatches)
Brand extraction (boAt, Ambrane, Samsung, etc.)
High-value deal finder: High rating + high discount + high reviews
📊 Sample Insights
Most reviewed product: TP-Link WiFi Adapter (179K+ reviews)
Highest discount: Sounce iPhone Cable (90% off)
Top category: Cables & Accessories (high volume, deep discounts)
Best value brand: boAt (strong presence in top-value lists)
📝 Future Improvements
Add review sentiment analysis (NLP)
Build a Flask/Dash web dashboard
Include price trend forecasting
Compare brand performance statistically
📜 License
MIT License — feel free to use, modify, and distribute.
