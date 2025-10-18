PharmaSafe

Database-Centric Medicine Expiry and Stock Prioritization


Project Overview :

PharmaSafe is a comprehensive pharmacy inventory management system developed to reduce medicine wastage, enhance compliance and optimise stock-utilisation by leveraging relational database storage, machine-learning expiry prediction and intelligent stock prioritization.
Pharmacies often struggle with expired or soon-to-expire medicines, leading to financial loss and regulatory risk. PharmaSafe addresses this with:

1. A centralised relational database for medicines, batches, sales history and storage conditions.

2. An AI expiry prediction module that assesses early-expiry risk, predicts expiry dates, and assigns risk levels.

3. A smart alert engine that triggers email/SMS alerts for expired or imminently expiring stock.

4. A stock prioritization engine (based on FEFO + demand forecasting) and a dashboard that visualises “safe vs expiring vs expired” stock.


Key Features :

1.Medicine & Batch Management – record medicine details (name, type, category), batch details (manufacture date, expiry date, storage conditions, quantity).

2.Expiry Prediction – ML model analyses batch + storage data to predict early expiry risk and writes results back into the database.

3.Smart Alerts – scheduled scans (CRON/Task Scheduler) run daily/weekly, identify expired/expiring stock, send email/SMS notifications.

4.Stock Prioritization – uses FEFO logic and demand history to generate priority list; updates database + dashboard accordingly.

5.Dashboard & Reports – visual analytics, monthly wastage prediction (“₹3,200 worth of stock may expire next month”), safe vs expiring stock breakdown.

6.Responsive UI – modern green-themed UI, dark mode support, user authentication (signup/login/profile), interactive forms and data tables.


Architecture & Workflow :

1.Data Storage – relational database (e.g., MySQL/PostgreSQL) stores all medicine, batch, purchase/sales and storage condition data.

2.AI Expiry Prediction Module – reads batch + storage data, predicts expiry risk and predicted expiry date, then writes predictions back to DB.

3.Smart Alert Engine – scheduled job that runs SQL queries to identify expired / expiring stock (≤ 30 days) and triggers notifications.

4.Stock Prioritization Engine – executes FEFO (First Expire, First Out) + demand forecasting logic, generates priority list and updates DB + dashboard.

5.Dashboard / UI Layer – shows visual charts & insights: safe stock vs expiring vs expired, monthly wastage forecasts, priority stock list, batch tables, alert logs.


User Interface Overview :

1.Branding & Layout – “PharmaSafe” displayed top-left in sidebar header; sidebar menu remains (Dashboard Overview, Medicines & Batches, Expiry Predictions, Alerts, Stock Prioritization, Reports).

2.Authentication – Login / Sign-Up button top-right; upon successful authentication, replaced by Profile button showing user name; sign-up form captures name, email, password.

3.Colour Theme – soothing green palette:

4.Light mode: background #E8F5E9, accent #43A047, text #1B5E20

5.Dark mode: background #1B1F1D, accent #66BB6A, text #C8E6C9


Page-Specific Details:

1.Dashboard Overview: summary cards + charts

2.Medicines & Batches: table + “+ Add Medicine/Batch” form (fields: Medicine Name, Batch ID, Purchase Date, Expiry Date, Quantity, Storage Type)

3.Expiry Predictions: table with predicted expiry, risk level, confidence score; colour-coded rows

4.Alerts: table of triggered alerts with filters

5.Stock Prioritization: title updated to “Stock Prioritization” (removed “(FEFO)”), stocks listed numerically (Stock 1, Stock 2…) grouping same-purchase-date, medicines within sorted by expiry. Download CSV option included

6.Reports: summary cards + export options + date-range selector

7.Chart Enhancement in Dark Mode – bar graphs use lighter mint-green tones (#81C784, #A5D6A7) for readability, axis labels in soft grey; rest of UI unchanged.


Getting Started :

1.Clone this repository:

git clone https://github.com/harshitapokhariya/Pharmasafe.git  

2.Install dependencies and set up environment variables (database URI, ML model path, email/SMS credentials).

3.Configure your relational database and apply schema + migrations.

4.Train or load the machine-learning model for expiry prediction and ensure the module reads/writes to the database.

5.Ensure CRON/task scheduler is enabled to run the Smart Alert Engine at regular intervals.

6.Start the frontend server and verify pages: Dashboard, Medicines & Batches, Expiry Predictions, Alerts, Stock Prioritization, Reports.

7.Deploy to a hosting service (e.g., Vercel) and switch to the proper production database.



Thank you for exploring PharmaSafe — your partner in proactive, intelligent medicine inventory management.
