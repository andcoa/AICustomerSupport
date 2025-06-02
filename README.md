# AI-Powered Customer Support Workflow

## Objective  
Automate customer support triage using AI to classify incoming emails and generate intelligent responses, reducing manual workload and improving resolution speed with a retrieval-augmented approach.

## Skills Learned  
- **Email Integration**: Built an automated Gmail trigger to ingest new support emails in real time.  
- **AI Classification**: Implemented text classification with OpenRouter to route customer support vs. non-support queries.  
- **RAG Implementation**: Leveraged Pinecone and OpenAI embeddings for retrieval-augmented generation (RAG), enhancing response accuracy.  
- **AI Agent Orchestration**: Deployed an AI agent using OpenRouter with memory and tool integration to generate contextual responses.  
- **Workflow Optimization**: Designed a conditional logic system to route only relevant inquiries to the AI agent, minimizing false positives.

## Tools Used  
- **Email Integration**: Automated Gmail triggers to capture support emails in real time.
- **AI Classification**: Implemented AI to accurately distinguish support from non-support queries.
- **RAG Implementation**: Applied Pinecone and OpenAI embeddings to improve response accuracy.
- **AI Agent Orchestration**: Deployed an AI agent with memory and tool integration for contextual replies.
- **Workflow Optimization**: Designed conditional logic to route relevant inquiries and minimize false positives.

## Steps  

![image](https://github.com/user-attachments/assets/f334b8c0-4278-4363-b2bc-aa62e1870a92)

1. **Trigger Setup**  
   - Configured Gmail trigger in n8n to listen for new incoming support emails.

2. **Text Classification**  
   - Connected the email content to an OpenRouter-powered text classifier.
   - Classifier outputs either “Customer Support” or “Other”.

3. **Conditional Routing**  
   - If "Other": routed to a "No Operation" node to stop processing.  
   - If "Customer Support": sent to the AI agent workflow.

4. **Embedding & Vector Search**  
   - Customer support documents pre-embedded using **OpenAI Embeddings**
   - On each query, Pinecone returns relevant context via semantic search.

5. **AI Agent Response**  
   - Agent powered by **OpenRouter Chat** uses query, Pinecone results, memory, and tools to craft a high-quality response.

6. **Scalable Output**  
   - Response can be integrated with downstream steps like auto-reply, Slack notification, or CRM ticketing systems.
  
Example: Sent myself an email inquiring about the pool policy and the workflow replied back:

![image](https://github.com/user-attachments/assets/3917447a-73b1-4568-8634-c5ad9044d16b)

