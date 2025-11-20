# Azure API Management Policy for AIDR

This Azure API Management policy integrates with AIDR to protect LLM inputs and
outputs by validating and optionally transforming content before it reaches the
LLM or is returned to the client.

## Prerequisites

1. **AIDR**: You need an active AIDR account with a valid API token.
2. **Named Values**: Configure the following named values in the Azure API Management instance:
   - `ai-guard-url`: AI Guard URL (e.g. `https://ai-guard.aws.us-west-2.pangea.cloud`).
   - `ai-guard-token`: AI Guard token.

   To configure named values:
   1. Go to your API Management instance in Azure Portal.
   2. Navigate to **APIs** > **Named values**.
   3. Create new named values with the names above.
3. **Request/Response Format**: The policy expects requests and responses to
  follow the [OpenAI Responses API](https://platform.openai.com/docs/api-reference/responses/create)
  format.

## Installation

1. Copy the contents of `ai-guard-policy.xml`
2. In the Azure API Management instance:
   1. Navigate to your API operation
   2. Go to the **Policies** section
   3. Select the **Policy code editor** icon next to the **Policies** heading and
     replace the contents with the contents of `ai-guard-policy.xml`, or merge
     them with any existing policies.
   4. Save the policy.
