# llm
I use groq to access Mixtral 8x7b llm model. Reason of choosing groq is the api is easy to create in Hong Kong and free of charge. The temperature of the model is 0 for ensuret the reproducibility.

Demo video: https://github.com/jackyor/llm/assets/87265896/9871f6d6-8b78-4997-bccb-df5889878e23

The request content is in the content.txt which contain the text article and a prompt. The article is copy from the source https://techcrunch.com/2023/10/27/x-is-launching-new-premium-and-basic-subscription-tiers/. 

The prompt is the following:

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

