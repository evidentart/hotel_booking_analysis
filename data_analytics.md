# Data Analytics


## 1. Approach for Analysis

### 1.1. Descriptive Analytics
- Analyzed past and current data to identify:
  - Patterns and seasonality in booking behaviors.
  - Insights into guest demographics, cancellation reasons, and peak booking times.
- **Supervised Learning** was applied with `adr` (price) as the target variable to reveal actionable insights.

### 1.2. Predictive Analytics
- **K-Means Clustering** was employed for guest segmentation:
  - Segments were based on booking behaviors and traits.
  - Predicted trends in occupancy rates and pricing strategies for decision-making.  

This combination of descriptive and predictive approaches ensured actionable insights for improving hotel operations.

---

## 2. Algorithms Used for Analysis

### 2.1. J48 Algorithm
- Predicted:
  - Cancellation likelihood. The J48 algorithm predicted the likelihood of cancellations based on historical data. It achieved 76.68% accuracy, showing strong performance in predicting non-cancellations but struggling with actual cancellations due to class imbalance.
  - Correctly classified 76.68% of instances.
  - Struggled with class imbalance:
  - True Positive Rate for cancellations: 45.6%.
  - True Positive Rate for non-cancellations: 95%.

     ![Picture1](https://github.com/user-attachments/assets/d931115e-7e50-453f-bc4f-befeee111f27)
  
    
  - Optimal room type allocation. This decision tree allocated optimal room types to guests based on booking details. It performed well for common room types, achieving 90.2% accuracy, but struggled with underrepresented room types due to class imbalance.  
  - Correctly classified 90.2% of instances.
  - High accuracy for common room types (e.g., A and G).
  - Lower accuracy for rare room types due to class imbalance.
    
    ![Picture2](https://github.com/user-attachments/assets/047de789-5423-43c2-ae09-c668ce12b276)

    
  - Monthly occupancy rates. The algorithm analyzed monthly booking patterns to predict occupancy rates. It achieved 96.62% accuracy, with particularly strong predictions for peak months such as July, August, and December.  
  - Correctly classified 96.62% of instances.
  - High performance across all months, particularly July, August, and December.
 
    ![Picture3](https://github.com/user-attachments/assets/42fdac70-82ae-4100-973e-33b847beaf07)

---

### 2.2. K-Means Clustering
##### **Why K-Means Clustering?**

- **Efficiency for Large Datasets:**  
  - K-Means scales effectively and works well with datasets containing over 100,000 records.  
  - It handled multiple attributes such as `lead_time`, `average daily rate (adr)`, and `booking changes`.  

- **Ease of Interpretation:**  
  - The algorithm generated clear, interpretable clusters that allowed us to uncover patterns like **ADR**, **stay duration**, and **booking frequency**.  

- **Actionable Insights:**  
  - K-Means clustering identified key customer segments based on behavior, enabling us to design pricing strategies and promotions that align with each cluster's needs.  

### **Clustering of Hotel Bookings Based on Lead Time (7 Clusters)**

On the left side, we analyzed customer behavior based on how far in advance they make their bookings. The data was divided into 7 clusters:  
- **Cluster 3: "Ultra-Advanced Planners"**  
  - Customers in this cluster stand out with the **highest average lead time (~400 days)**.  
  - These customers are likely planning stays for large events such as weddings, conferences, or other occasions that require extensive preparation.  
- **Cluster 2: "Last-Minute Bookers"**  
  - Customers here have a **low average lead time (~30 days)**, representing last-minute bookings.  
  - They are likely business travelers or tourists who need accommodations quickly.  

By understanding behaviors across clusters, such as **Cluster 3's advanced planners** and **Cluster 2's last-minute bookers**, hotels can better target customers with specific pricing and promotional strategies.

   ![Picture4](https://github.com/user-attachments/assets/e1c6872d-4f6d-4d04-8867-e62f2cee9b3b)



### **Clustering of Hotel Bookings Based on Booking Changes (5 Clusters)**

On the right side, customers were grouped into 5 clusters based on the **frequency of their booking changes**:  
- **Cluster 2: "Flexible Frequent Changers"**  
  - This is the **largest segment**, representing **30% of the dataset**.  
  - These customers frequently modify their bookings and are likely premium travelers who value flexibility.  
  - Ideal strategies include offering flexible booking policies or premium upgrade promotions to attract and retain these customers.  
- **Cluster 0: "Budget-Conscious Stable Bookers"**  
  - Customers in this cluster rarely make booking changes and tend to choose **lower-priced rooms**.  
  - These travelers respond well to promotions like **last-minute deals** or **budget-friendly packages**.  

By identifying these segments, we can develop tailored marketing strategies, such as offering premium upgrades to **Cluster 2** or budget promotions to **Cluster 0**.

This method allowed us to segment customers efficiently and uncover patterns that can drive business decisions. For example:
- **Cluster 3:** Targeted with advanced booking promotions for event organizers.  
- **Cluster 2:** Tailored flexible booking policies and premium upgrade offers.  
- **Cluster 0:** Focused on budget-conscious promotions for last-minute deals.
  
#### The Python script for K-means clustering was developed with partial assistance from AI. This experimental approach yielded promising results, demonstrating its potential for effective data analysis
[Sample Script](https://github.com/evidentart/sample-scripts)
---

### **2.3. Linear Regression Algorithm**
Linear regression was used to predict the **Average Daily Rate (ADR)** and analyze the factors influencing it.  

**Key Results:**
- The model showed a **moderate positive relationship** between predicted and actual ADR values, with a correlation of **0.7391**.  
- **Errors:**
  - Relative Absolute Error: High.  
  - Square Error: High.  
  - Average prediction error: **0.0043 units**, indicating the need for more advanced techniques to improve accuracy.  

**Key Trends Identified:**
1. **City Hotels Charge Higher ADR**  
   - Urban areas demand premium pricing.  
2. **Longer Lead Times Lower ADR**  
   - Early booking discounts are common.  
3. **Seasonality Impacts ADR**  
   - Higher ADR during peak months like November and December.  
4. **Larger Bookings Increase ADR**  
   - Group bookings or suites often result in higher pricing.  

These findings underline the potential for ADR forecasting to guide revenue management strategies. However, the results suggest that additional features or advanced models could enhance predictive accuracy.
    
![Picture2](https://github.com/user-attachments/assets/f32d3820-7591-425e-817c-168c5d3c0814)



---


