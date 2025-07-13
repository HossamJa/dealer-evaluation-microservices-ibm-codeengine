# 🛒 Product Price Comparison App – Microservices with IBM Code Engine

This project is the final assignment for the Coursera course:  
**"Application Development using Microservices and Serverless with Kubernetes and OpenShift"** by IBM.

It demonstrates how to deploy multiple microservices (Python, Node.js, and a frontend) on **IBM Cloud Code Engine** to build a price comparison tool.

---

## 📦 Technologies Used

- IBM Cloud Code Engine (Serverless Container Deployment)
- Python (Flask)
- Node.js (Express)
- HTML, JS (Frontend)
- REST APIs
- GitHub for version control

---

## 🧱 Project Architecture

The application is divided into **3 microservices**:

1. **Product Details** (Python): Provides product list via REST API  
2. **Dealer Pricing** (Node.js): Provides pricing via REST API  
3. **Frontend App**: Uses both APIs to display product and dealer pricing


---

## 🚀 Microservices Deployment

### ✅ 1. Product Details Microservice (Python)

```bash
ibmcloud ce application create \
--name prodlist \
--image us.icr.io/<your_namespace>/prodlist \
--registry-secret icr-secret \
--port 5000 \
--build-context-dir products_list \
--build-source https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
```

🖼️ Screenshot:

![product_details_deploy](https://github.com/user-attachments/assets/23f26c7e-026a-4509-ab60-10be67b42cb7)


---

### ✅ 2. Dealer Pricing Microservice (Node.js)

```bash
ibmcloud ce application create \
--name dealerdetails \
--image us.icr.io/<your_namespace>/dealerdetails \
--registry-secret icr-secret \
--port 8080 \
--build-context-dir dealer_details \
--build-source https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
```

🖼️ Screenshot:

![dealer_details_deploy](https://github.com/user-attachments/assets/9e3dfacc-9cdc-4ce6-946b-051fbf9809b6)


---

## 🌐 Frontend Deployment

### ✅ 3. Clone and Modify Frontend

Clone: https://github.com/ibm-developer-skills-network/dealer_evaluation_frontend.git  
Update `index.html` with API URLs.

🖼️ Screenshots:

![git_clone](https://github.com/user-attachments/assets/ca8dc1e8-aa43-4d75-998f-be059fdcfafe)

<img width="885" height="484" alt="index_urlchanges" src="https://github.com/user-attachments/assets/640ffea2-0621-4125-9278-3a939a2c69ff" />


---

### ✅ 4. Deploy the Frontend App

```bash
ibmcloud ce application create \
--name frontend \
--image us.icr.io/<your_namespace>/frontend \
--registry-secret icr-secret \
--port 5001 \
--build-source .
```

🖼️ Screenshot: 

<img width="853" height="433" alt="frontend_deploy" src="https://github.com/user-attachments/assets/b4116144-7f33-4948-be92-c828f4492935" />


---

## 🧪 App Functionality Test

🖼️ Screenshots:
- Homepage loaded:

<img width="603" height="335" alt="homepage" src="https://github.com/user-attachments/assets/702e61e6-27a6-4a0c-a621-1a3fc765161c" />

- Dealer list:

<img width="617" height="407" alt="product_dealer" src="https://github.com/user-attachments/assets/7611c75d-8ff1-4f69-b7f0-e2c0da28fe2e" />

- Selected dealer price:

<img width="634" height="305" alt="product_dealer_price" src="https://github.com/user-attachments/assets/68857456-6380-4647-824e-256a3602c482" />

- All dealer prices:

<img width="619" height="341" alt="product_all_dealers_prices" src="https://github.com/user-attachments/assets/61b23ac2-c3d4-488b-a2d7-9359d891bcd6" />


---

## 🎓 Course Info

> **Course**: Application Development using Microservices and Serverless  
> **Platform**: Coursera  
> **Provider**: IBM  
> **Completion Date**: July 2025

---

## 👨‍💻 Author

**Hossam Jamjama**  

