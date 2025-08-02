🤖 n8n Daily Newsletter Workflows 📰
This repository contains two n8n workflows designed to automate the process of creating and sending a daily newsletter from news articles. These workflows demonstrate different approaches to fetching and processing news content.

✨ Workflows

📧 Workflow 1: Send Daily Newsletter (Send_Daily_Newsletter.json)

This workflow fetches the latest BBC technology news, extracts the top three articles, and sends them directly via email.

Webhook Trigger: Starts the workflow on a specified path.

RSS Read: Fetches the latest BBC technology news from https://feeds.bbci.co.uk/news/technology/rss.xml.

Code: This node uses JavaScript to slice the items, keeping only the top three.

Send a message: The final node sends an email containing the article titles, links, and summaries to a predefined recipient using a Gmail account.

🧠 Workflow 2: Summarize News and Trigger (Workflow_1_Summarize_And_Trigger.json)

This workflow also reads the same BBC technology news feed, but instead of sending the raw articles, it leverages an OpenAI model to summarize the content before sending it to another webhook.

Webhook Trigger: Initiates the workflow upon receiving a POST request.

Format News Content: A function node that formats the top three news articles for summarization.

Summarize with GPT: Uses the GPT-4 model from OpenAI to summarize the formatted news items into a short newsletter.

Send to Workflow 2: A final HTTP Request node sends the generated summary to another webhook URL.

🛠️ Prerequisites

n8n Instance: You need a running n8n instance to import and run these workflows.

API Keys/Credentials:

Gmail OAuth2 Credentials: Required for the Send_Daily_Newsletter workflow to send emails.

OpenAI API Key: Required for the Summarize with GPT node in the second workflow.

🚀 Usage

Import Workflows: In your n8n instance, navigate to the workflows section and import the .json files.

Configure Credentials: Update the credentials for Gmail and OpenAI in the respective nodes.

Activate Workflows: Set the workflows to "Active" to enable them.

Trigger: The workflows are triggered by webhooks. For Workflow_1_Summarize_And_Trigger, you would need to manually or programmatically trigger its webhook.
