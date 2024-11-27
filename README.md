# **Financial Insights Scoring Model API**

## **Overview**
This project implements a Flask-based API for evaluating the financial health of families using a scoring model. The API calculates a financial score (0–100) and provides actionable insights based on family-level financial data.

---

## **Features**
- **Scoring Model**: Evaluates financial health based on:
  - Savings-to-Income Ratio
  - Monthly Expenses as a percentage of Income
  - Loan Payments as a percentage of Income
  - Spending trends in discretionary categories (e.g., Travel, Entertainment)
  - Percentage of Financial Goals Met
- **Insights**: Provides key financial metrics and recommendations.
- **Extensibility**: Can be integrated into dashboards or other financial tools.

---

## **Technologies Used**
- Python
- Flask
- Pandas (for data manipulation)

---

## **Installation**

### **1. Clone the Repository**
```bash
git clone <repository-url>
cd <repository-directory>
```

### **2. Set Up a Virtual Environment**
```bash
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
```

### **3. Install Dependencies**
```bash
pip install -r requirements.txt
```

---

## **Usage**

### **1. Start the Flask App**
Run the following command in the project directory:
```bash
python app.py
```

### **2. Test the API**
- Use a tool like **Postman**, **curl**, or any HTTP client to test the API.
- API Endpoint: `http://127.0.0.1:5000/score`
- Method: `POST`
- **Sample Request Body** (JSON):
  ```json
  {
    "Family ID": "FAM001",
    "Savings": 20000,
    "Income": 100000,
    "Monthly Expenses": 5000,
    "Loan Payments": 2000,
    "Travel": 8000,
    "Entertainment": 3000,
    "Financial Goals Met (%)": 70
  }
  ```

### **3. Response Example**
```json
{
  "Financial Score": 75,
  "Insights": "Savings-to-Income Ratio: 0.20, Expenses Percentage: 0.05, Loan Payments Percentage: 0.02"
}
```

---

## **Project Structure**
```
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

---

## **Dependencies**
Ensure the following Python libraries are installed:
- Flask
- Pandas

You can install them using:
```bash
pip install -r requirements.txt
```

---

## **Scoring Model Details**
The financial score is calculated based on:
1. **Savings-to-Income Ratio**:
   - Below 20%: Penalized heavily
   - 20–50%: Moderate penalty
2. **Monthly Expenses as a Percentage of Income**:
   - Above 80%: Heavily penalized
   - 50–80%: Moderate penalty
3. **Loan Payments as a Percentage of Income**:
   - Above 40%: Heavily penalized
   - 20–40%: Moderate penalty
4. **Spending Trends in Discretionary Categories**:
   - High spending on Travel/Entertainment reduces the score.
5. **Financial Goals Met**:
   - Rewards are given for higher achievement rates.

---

## **Future Improvements**
- Deploy to a cloud service (e.g., AWS, Heroku).
- Add a frontend using **Streamlit** or **Dash** for visualization.
- Extend the scoring model to include more financial metrics.

---

## **License**
This project is licensed under the MIT License. See the LICENSE file for more details.

---

Let me know if you’d like to adjust this or include additional sections!
