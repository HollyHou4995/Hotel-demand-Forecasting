## Pick a Time Series Variable of Interest

This dataset contains hotel demand data for two types of hotels: a resort hotel (H1) with 40,060 observations and a city hotel (H2) with 79,330 observations, totaling 119,390 bookings. Each record represents a hotel booking with 31 variables capturing booking details, customer characteristics, and stay information. The data spans arrivals between July 1, 2015, and August 31, 2017, including both completed and canceled bookings. All sensitive information related to hotel and customer identification has been anonymized. These datasets are valuable resources for research and education in areas such as revenue management, machine learning, and data mining.

https://www.sciencedirect.com/science/article/pii/S2352340918315191
https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand?resource=download

### Dataset Overview:
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
- The dataset contains missing values for:
  - `children`: 4 missing values.

This dataset provides a comprehensive foundation for analyzing booking patterns, customer behaviors, and revenue metrics for hotel management, providing a rich foundation for exploring trends, seasonality, and forecasting models to analyze and predict hotel demand.
