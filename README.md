## 🧠 Article-to-Meme Generator (MakeAI + HTTP API)

This project automatically converts any article, blog post, or text content into a funny, shareable meme using MakeAI’s LLM capabilities.
It extracts the core idea from long content, compresses it into humor, and returns structured meme text in JSON format—perfect for automation, social media bots, or meme-based content creation.

---


## 🚀 Features

Turns long articles into memes within seconds

Uses MakeAI’s prompt engine + HTTP request module

Outputs memes in a guaranteed JSON format (top_text, bottom_text)

Can be extended to auto-generate meme images, tweets, or Instagram posts

Fully automation-ready — plug into Notion, Airtable, Google Sheets, or APIs

---


## 🔧 How It Works

User inputs (or Make fetches) an article URL or raw text.

The Make scenario sends the article to MakeAI using a custom HTTP module.

The model transforms the article into a humorous meme concept.

Output returns clean JSON for easy downstream usage.

---


## 🧩 JSON Request Body (Used in MakeAI → HTTP Module)
{
  "prompt": "Convert the following article into a funny meme. Extract the key idea, exaggerate it humorously, and output ONLY meme text in two parts: 'top_text' and 'bottom_text'.\n\nArticle:\n{{article}}\n\nMake it short, relatable, and viral.",
  
  "temperature": 0.7,
  
  "max_tokens": 200,
  
  "response_format": {
  
    "type": "json_schema",
    
    "json_schema": {
    
      "name": "meme_output",
      
      "schema": {
      
        "type": "object",
        
        "properties": {
        
          "top_text": { "type": "string" },
          
          "bottom_text": { "type": "string" }
          
        },
        
        "required": ["top_text", "bottom_text"]
      }
    }
  }
}

---




## 🏗️ Use Cases

Automated meme generation for newsletters

Adding humor to blogs or marketing pipelines

Social media meme bots

Meme-based content repurposing

AI-powered knowledge distillation

---


## 📦 Future Enhancements

Auto-generate meme images with templates

Add image captions on top of generated backgrounds

Multi-language meme support

Article summarization + meme combo mode
