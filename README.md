Strategic Revenue Analysis: AtliQ Grands Hospitality 🏨📊

An End-to-End Business Intelligence Solution for the Luxury Hotel Sector
📖 Project Background

AtliQ Grands is a prestigious hotel chain in India that was losing market share and revenue to aggressive competitors. Management lacked a centralized system to monitor performance, making it impossible to respond to market changes.

I developed this project following a Lead Analyst Briefing with Abhishek Anand, a Revenue Manager at OYO Rooms. The objective was to move away from "gut-feeling" decisions and implement a professional Business Intelligence Hub using Power BI.
🔗 Quick Links

    Live Portfolio: subhobasak.netlify.app

    Project Walkthrough: YouTube Demonstration

🏗️ The Technical Architecture

To ensure the dashboard was scalable and fast, I implemented a Star Schema data model. This involved connecting five separate datasets and engineering a custom calendar to reflect the hospitality industry's unique "Weekend" (Friday/Saturday) demand patterns.
📐 The Analytical Engine (26 Custom DAX Measures)

I engineered 26 specialized DAX measures to "peel the onion" of AtliQ Grands' data. These measures allow management to look at the business through three distinct lenses: Financials, Operations, and Growth Trends.
1. Financial Performance (Level 1)
Measure	DAX Formula	Business Purpose
Revenue	SUM(fact_bookings[revenue_realized])	Total realized revenue after deductions.
ADR	DIVIDE([Revenue], [Total Bookings], 0)	Average Daily Rate: Measures the average price paid per room sold.
RevPAR	DIVIDE([Revenue], [Total Capacity])	Revenue Per Available Room: The ultimate measure of hotel success.
Total Capacity	SUM(fact_aggregated_bookings[capacity])	Total available inventory across all properties.

2. Operational Health (Level 2)
Measure	DAX Formula	Business Purpose
Occupancy %	DIVIDE([Total Succesful Bookings],[Total Capacity],0)	Percentage of total rooms occupied by guests.
Realisation %	1- ([Cancellation %]+[No Show rate %])	The percentage of bookings that actually turned into a stay.
Cancellation %	DIVIDE([Total cancelled bookings],[Total Bookings])	Tracking the rate of lost customers.
No Show rate %	DIVIDE([Total no show bookings],[Total Bookings])	Guests who booked but never checked in.
Average Rating	AVERAGE(fact_bookings[ratings_given])	Quality control metric based on customer feedback.

3. Efficiency Metrics (Averages)
Measure	DAX Formula	Business Purpose
DBRN	DIVIDE([Total Bookings], [No of days])	Daily Booked Room Nights: Average rooms booked per day.
DSRN	DIVIDE([Total Capacity], [No of days])	Daily Sellable Room Nights: Average inventory ready to sell per day.
DURN	DIVIDE([Total Checked Out],[No of days])	Daily Utilized Room Nights: Average rooms actually occupied per day.

4. Market Contribution
Measure	DAX Formula	Business Purpose
Booking % by Platform	DIVIDE([Total Bookings], CALCULATE([Total Bookings], ALL(fact_bookings[booking_platform]))) * 100	Shows which channel (MMT, Direct, etc.) is most effective.
Booking % by Room Class	DIVIDE([Total Bookings], CALCULATE([Total Bookings], ALL(dim_rooms[room_class]))) * 100	Shows demand distribution across room categories.

5. Time Intelligence (Week-on-Week Trends)

These measures use complex DAX variables (VAR) to calculate growth compared to the previous week.
Measure	Logic
Revenue WoW %	Identifies if weekly revenue is trending up or down.
Occupancy WoW %	Tracks sudden shifts in guest demand.
ADR WoW %	Monitors if pricing changes are helping or hurting margins.
Revpar WoW %	The holistic "health check" of the property weekly growth.
Realisation WoW %	Tracks check-in efficiency trends.
DSRN WoW %	Monitors changes in sellable inventory (maintenance issues).

💡 Strategic Business Insights

By analyzing the data through the measures above, I identified three critical opportunities for AtliQ Grands:

    The Dynamic Pricing Opportunity: My ADR analysis showed a flat line over 3 months. This revealed that AtliQ was not raising prices during peak demand (Weekends/Holidays), leaving millions in potential revenue on the table.

    The "Rating-Revenue" Correlation: Properties with an average rating below 3.0 saw a massive 15% spike in cancellations. Improving service in these properties is a direct lever for revenue growth.

    Platform Strategy: Direct Offline bookings had the highest ADR. I recommended a strategy of "Loyalty Discounts" on their own website to move customers away from high-commission third-party platforms.

🖥️ Final Dashboard Design

    Key Visuals: Donut charts for Platform contribution, Line charts for Weekly Trends, and Table visuals with Conditional Formatting.

    Interactivity: Slicers for City, Month, and Room Class; Dynamic Tooltips for "hover-over" trend analysis.

🛠️ Tools Used

    Power BI Desktop (Data Modeling, DAX, Visualization)

    Power Query (ETL & Data Transformation)

    Excel (Initial Data Profiling)

👤 About the Developer

I am Subho Basak, a Data Analyst in Siliguri, currently specializing in Business Intelligence and Strategic Analytics.
