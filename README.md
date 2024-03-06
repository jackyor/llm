# llm
I use groq to access Mixtral-8x7B llm model. Reason of choosing groq is the api is easy to create in Hong Kong and free of charge. Also, groq has a huge competitive advantage in inferencing speed. For model, Mixtral-8x7B is one of the best open source llm model with small weight. The temperature of the model is 0 to ensure the result is reproducible. 

Demo video: https://youtu.be/Q3V-Cvy4oZ8

The request content is in the content.txt which contain the text article and a prompt. The article is copy from the source https://techcrunch.com/2023/10/27/x-is-launching-new-premium-and-basic-subscription-tiers/. 

- The prompt is the following:

"Given an article, your task is to extract information about mentioned companies and the topic of the article. The information about each company should include the company’s name and domain. The topic is the exactly the same with the first sentence of the article. Please parse this information into the following JSON format: 

```
{
  "related_companies": [
    {
      "company_name": "<Company Name>",
      "company_domain": "<Company Domain>"
    },
    // More companies as needed
  ],
  "topic": "<First Sentence of the Article>"
}
```
Please ensure the accuracy of the extracted information and the correctness of the JSON format."

- The result is:

```
{
  "related_companies": [
    {
      "company_name": "X",
      "company_domain": "X.com"
    },
    {
      "company_name": "Twitter",
      "company_domain": "Twitter.com"
    },
    {
      "company_name": "Bloomberg",
      "company_domain": "Bloomberg.com"
    },
    {
      "company_name": "Reuters",
      "company_domain": "Reuters.com"
    }
  ],
  "topic": "X is launching two new subscription tiers, including a ‘Premium+’ ad-free plan."
}
```

Note: I am not sure if I need to elimate Twitter. Although X and Twitter is the same company, Twitter is more regonized than X as the company name thus it may be more valuable to include Twitter.
