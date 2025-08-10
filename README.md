# Handsman Threads – Salesforce CRM Solution

**Elevating the Art of Sophistication in Men's Fashion**

## 🧠 Overview

**Handsman Threads** is a bespoke Salesforce CRM platform crafted to streamline men’s tailoring services. The application significantly enhances customer engagement, optimizes order fulfillment, and fosters personalized styling experiences through custom automations and robust CRM workflows.


## 🎯 Business Goals

- **Streamline Order Management** for seamless customer operations  
- **Elevate Customer Experience** using personalized styling and loyalty programs  
- **Ensure Inventory Accuracy** with real‑time stock updates  
- **Optimize Salesforce Tooling** via Flows, Apex, Email Alerts, and Custom Objects  


## ⚙️ Project Architecture

### 📦 Custom Objects
| Object               | Purpose                                   |
|----------------------|--------------------------------------------|
| `Handsman_Customer__c` | Capture customer info, loyalty status, total purchases |
| `Handsman_Product__c`  | Manage product catalog: SKU, price, quantity |
| `Inventory__c`         | Track stock levels and warehousing         |
| `Handsman_Order__c`    | Process customer orders and manage status  |
| `Marketing_Campaign__c`| Handle promotions and campaign tracking    |

Standard Salesforce objects like **Accounts**, **Contacts**, **Reports**, and **Dashboards** are integrated for broader analytics and business context.


## 🧑‍💻 Key Features & Automations

### 1. Order Confirmation Workflow
- Uses a **record-triggered Flow**: on status change from *Pending → Confirmed*
- Sends confirmation email to customer
- Updates inventory stock automatically (e.g. reduced from 400 → 380 units)

### 2. Low-Stock Alert Automation
- Triggered when **Inventory.Quantity < 5**
- Sends alert to inventory manager to restock

### 3. Loyalty Program (Scheduled Flow)
- Runs daily at midnight (12:00 AM)
- Classifies customers as:
  - **Gold**: total purchases > 1,000
  - **Silver**: 500 < total purchases ≤ 1,000
  - **Bronze**: total purchases ≤ 500
- Automatically updates `Loyalty_Status__c` and notifies customer via email

### 4. Apex Order Total Calculation
- Custom **Apex trigger** calculates `Total_Amount__c` = `Product.Price__c × Quantity__c`
- Ensures real-time accuracy on Handsman_Order__c record submission


## 📝 Usage & Record Flow

1. **Create Customer** – New record in `Handsman_Customer__c` including email validation (only Gmail addresses accepted)
2. **Add Product** – Record into `Handsman_Product__c` (name, SKU, price, stock quantity)
3. **Inventory Entry** – Link product to warehouse, record stock level
4. **Place Order** – Create `Handsman_Order__c`, choose customer & product, enter quantity; total auto-calculated
5. **Confirm Order** – Change order status to “Confirmed” triggers email & stock update
6. **Automations in Action** – Low-stock alerts and loyalty upgrades executed by relevant Flows

---

## 📁 Project Structure

HandsmanThreadsProject/
├── README.md
├── flows/ <-- Metadata for Flows
├── triggers/ <-- Apex Trigger files
├── validationRules/ <-- Email and input validations
└── reports/ dashboards/ <-- Salesforce reports and dashboards for analytics



## 🎓 Conclusion

The **Handsman Threads** Salesforce CRM project exemplifies how to leverage Salesforce’s capabilities to create a tailored business solution. Its clean and modular design aligns technology with business needs, delivering a scalable CRM platform optimized for both customer experience and operational efficiency.


## ✉️ Acknowledgments

Thanks to the SmartBridge Virtual Internship team, mentors, and trainers for guiding the development and deployment of this project. Every feature was thoroughly tested and documented to meet the project scope and quality standards.


## 🔗 Repository
  
- **GitHub Repository**: [Ch‑harini11/HandsmenThreadsProject](https://github.com/Ch-harini11/HandsmenThreadsProject/)

🙏 Huge thanks to @SmartBridge, @Amarender Katkam, @Sridevi Sira, and @Yudhisther Yadav for providing this incredible learning opportunity to students across India!
To everyone still exploring opportunities – keep going, keep growing! 🚀
#SkilledonSalesforce hashtag#SmartBridge hashtag#Salesforce hashtag#VirtualInternship hashtag#Trailblazers
#CareerGrowth hashtag#CertificationsMatter hashtag#LearningNeverStops hashtag#StudentJourney hashtag#Gratitude hashtag#HardWorkPaysOff
