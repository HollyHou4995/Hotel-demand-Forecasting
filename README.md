# README: Time Series Forecasting for Hotel Booking Demand

## Dataset Overview
This dataset contains hotel booking demand data for:
- **Resort Hotel (H1)**: 40,060 observations.
- **City Hotel (H2)**: 79,330 observations.
This dataset contains hotel demand data for two types of hotels: a resort hotel (H1) with 40,060 observations and a city hotel (H2) with 79,330 observations, totaling 119,390 bookings. Each record represents a hotel booking with 31 variables capturing booking details, customer characteristics, and stay information. The data spans arrivals between July 1, 2015, and August 31, 2017, including both completed and canceled bookings. All sensitive information related to hotel and customer identification has been anonymized. These datasets are valuable resources for research and education in areas such as revenue management, machine learning, and data mining.

https://www.sciencedirect.com/science/article/pii/S2352340918315191
https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand?resource=download

### Key Features:
- **Dataset Size**: 119,390 rows and 19 columns.
- **Column Names**:
  - `hotel`: Type of hotel (e.g., Resort Hotel, City Hotel).
  - `is_canceled`: Whether the booking was canceled (1 for yes, 0 for no).
  - `lead_time`: Days between booking date and arrival date.
  - `arrival_date`: Full date of arrival.
  - `arrival_date_year`: Year of the arrival date.
  - `arrival_date_month`: Month of the arrival date.
  - `arrival_date_week_number`: Week number of the arrival date.
  - `arrival_date_day_of_month`: Day of the month of arrival.
  - `stays_in_weekend_nights`: Number of weekend nights in the stay.
  - `stays_in_week_nights`: Number of weekday nights in the stay.
  - `adults`: Number of adults in the booking.
  - `children`: Number of children in the booking.
  - `babies`: Number of babies in the booking.
  - `market_segment`: Source of booking (e.g., Direct, Online Travel Agent).
  - `distribution_channel`: Booking distribution channel (e.g., Direct, TA/TO).
  - `customer_type`: Type of customer (e.g., Transient, Contract).
  - `adr`: Average Daily Rate, indicating the price paid for the stay.
  - `reservation_status`: Current status of the booking (e.g., Check-Out, No-Show).
  - `reservation_status_date`: Date of the reservation status update.

### Missing Data:
- `children`: Contains 4 missing values.

The dataset provides a foundation for exploring booking patterns, pricing strategies, and customer behaviors.

---

## Time Series Analysis

### 1. Average Price (ADR)
- Weekly movements in ADR reveal seasonal and trend patterns.
- **Decomposition**:
  1. **Trend**: Long-term movements in ADR.
  2. **Seasonality**: Recurring patterns due to demand shifts.
  3. **Residuals**: Random variations.

### 2. Variables Influencing ADR:
1. **Lead Time**:
   - Short lead times → Higher ADR (last-minute demand).
   - Long lead times → Discounted rates.
2. **Arrival Month**:
   - ADR peaks during holidays and tourist seasons.
3. **Adults**:
   - Group size affects room pricing.

These variables refine forecasting by linking ADR with guest behavior and seasonality.

---

## SARIMA Model Results

1. **SARIMA without Covariates**:
   - **MAE**: 5.41
   - Captures trends and seasonality effectively.
   - Simpler and more robust for forecasting ADR.

2. **SARIMA with Covariates**:
   - **MAE**: 6.38
   - Adding `lead_time`, `adults`, and `arrival_date_month_numeric` increased error slightly.
   - Covariates were not statistically significant, introducing complexity without improving accuracy.

---

## Key Insights and Recommendations
1. **Model Comparison**:
   - **SARIMA without covariates** is preferred for this dataset due to better accuracy and simplicity.
   - Covariates do not significantly improve ADR forecasting here.

2. **Application**:
   - Use SARIMA without covariates for pricing and demand forecasting.
   - For richer datasets, consider advanced models like SARIMAX or LSTM for incorporating external factors.

3. **Impact of Covariates**:
   - ADR is driven primarily by intrinsic trends and seasonality in this dataset.

---

## Summary
The SARIMA model without covariates provides the best balance of accuracy, simplicity, and robustness. It effectively captures ADR trends and seasonality, making it a reliable tool for real-world applications in hotel revenue management and demand forecasting.
