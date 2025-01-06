
## Overview
This project demonstrates how to extend Salesforce's **Agentforce** capabilities by integrating **custom actions** and leveraging **Einstein AI** to enhance user experiences. With these configurations, your virtual assistant can handle conversations seamlessly, retrieve records, and execute custom flows, such as processing order returns.

---

## Key Features
1. **Out-of-the-Box Agentforce Actions**  
   - Retrieve and summarize account details.  
   - Handle follow-up queries using conversational context.  
   - Automatically fetch related records such as orders and products.

2. **Custom Agent Actions**  
   - Extend Agentforce capabilities by integrating existing flows into the assistant's catalog of actions.  
   - Example: Use the "Initiate Return" flow to process order returns and update status fields dynamically.

3. **Einstein Copilot Integration**  
   - Enable contextual and dynamic conversations using **Large Language Models (LLMs)** powered by **Einstein AI**.  
   - Maintain a seamless flow of communication by understanding context and chaining actions.

---

## Setup Instructions

### **1. Enable Einstein AI**
1. Open **Setup** in your Salesforce org.
2. Search for **Einstein Setup** and toggle the **Enable Einstein** switch.  
3. Refresh your browser to activate additional admin settings.

### **2. Verify Existing Orders**
1. From the **App Launcher**, search for **Orders** and select **All Orders**.  
2. Ensure the sample orders for **Edge Communications** exist in the system.

### **3. Enable Einstein Copilot**
1. Go to **Setup** → Search for **Agents**.
2. Enable **Einstein Copilot** by toggling it on.  
3. Open **Agent Builder** from the Einstein Copilot settings.

---

## Testing Standard Agentforce Actions
1. Open the **Agent Builder**.  
2. In the **Conversation Preview**, type:  
   - `Tell me about the account Edge Communications.`  
   - Review the response for account details.  
3. Follow up with:  
   - `Do they have any active orders?`  
   - Confirm the assistant retrieves and displays the active orders for **Edge Communications**.

---

## Adding Custom Actions to Agentforce

### **1. Create a Custom Agent Action**
1. Go to **Setup** → Search for **Agent Actions** → Click **New Agent Action**.
2. Configure the custom action:
   - **Reference Action Type**: Flow  
   - **Reference Action**: Initiate Return  
   - **Instructions**:  
     - **Action Instructions**: Use "Initiate Return" for requests to return or refund orders or products.  
     - **Inputs**: Populate this input variable with an Order recordId.  
     - **Outputs**: Status of the return request (initiated, processed, completed).  
   - Enable **Require Input** and **Collect data from user**.
   - Enable **Show in conversation** for Outputs.

3. Save the action.

### **2. Add Custom Action to the Agent**
1. Go to **Agent Builder**.  
2. Deactivate the assistant if it’s active.  
3. Under **Topics**, select **MigrationDefaultTopic** → Click **This Topic’s Actions** → Add **Initiate Return** from the Asset Library.  
4. Activate the assistant.

---

## Testing the Custom Action
1. Start a conversation from the **Home tab**:  
   - `What is the order with the most recent order start date?`  
   - Click the displayed order link (e.g., Order 101).
2. Request order details:  
   - `Tell me about order 101.`  
3. Initiate a return:  
   - `Start a return for order 101.`  
4. Verify that the **Return Status** field on the order is updated to **Initiated** under the **Details tab**.

---

## Technologies Used
- **Salesforce Agentforce**: For building and customizing virtual agents.  
- **Einstein AI**: For conversational intelligence and LLM integration.  
- **Salesforce Flows**: To automate unique business processes like order returns.  

---

## Benefits
1. **Enhanced User Experience**: Provide dynamic and contextual responses.  
2. **Seamless Integration**: Use existing flows and data models to handle custom business processes.  
3. **Time-Saving Automation**: Automate manual tasks, such as initiating returns, improving operational efficiency.

---

