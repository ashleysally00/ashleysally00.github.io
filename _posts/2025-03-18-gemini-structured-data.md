---
title: "Turn Bookshelf Photos into Structured Data with Gemini 1.5 Pro"
date: 2025-03-18
layout: post
categories: [AI, OCR, Automation]
tags: [Gemini 1.5 Pro, Google AI Studio, JSON, CSV, Data Extraction]
---

## **Extracting Book Data from Images with Gemini 1.5 Pro**

In this screencast, I used **Google AI Studio** and **Gemini 1.5 Pro** to extract structured book data from bookshelf photos. By leveraging **OCR (Optical Character Recognition)** and **AI-powered data extraction**, I was able to convert book titles and authors into structured **JSON format**, which I then transformed into **CSV** for easy spreadsheet use.

## **Watch the Screencast**

I recorded a screencast demonstrating how to extract structured book data from images using Gemini 1.5 Pro.

[![Watch the Video](https://img.youtube.com/vi/yo94YNXvBe4/0.jpg)](https://www.youtube.com/watch?v=yo94YNXvBe4)

## **Images Used in This Project**
The following images from **Unsplash** were used in the experiment:

- 📸 *Photo by Brett Jordan on Unsplash*  
  - `Books-brett-jordan-gl7TLtUejKA-unsplash (2).jpg`
  - `Books2-brett-jordan-qXrA_qN3WvM-unsplash.jpg`

---

## **How I Used Google AI Studio for OCR and Structured Data Extraction**

### **Step 1: Upload an Image**
I uploaded a **photo of a bookshelf** to **Google AI Studio**.

### **Step 2: Enter the Prompt**
I used the following prompt to guide **Gemini 1.5 Pro** in extracting book details:


You are an expert data extractor and librarian. Your task is to analyze images of bookshelves and extract information about the books.

1.  **Text Extraction (OCR):** Carefully examine the image and use optical character recognition (OCR) to identify and extract the book titles and authors.
2.  **Subject Identification (Attempt):** Based on the extracted text, attempt to infer the subject or genre of each book. This might involve looking for keywords in the title or author's name. If you cannot confidently determine the subject, leave it as "Unknown".
3.  **JSON Output:** Return the extracted data in a JSON format. Each book should be represented as a separate JSON object within an array. The JSON object should have the following keys: "title", "author", and "subject".

Example Output Format:
```
[
  {
    "title": "The Lord of the Rings",
    "author": "J.R.R. Tolkien",
    "subject": "Fantasy"
  },
  {
    "title": "Pride and Prejudice",
    "author": "Jane Austen",
    "subject": "Classic Literature"
  },
  {
    "title": "A Brief History of Time",
    "author": "Stephen Hawking",
    "subject": "Physics"
  },
  {
    "title": "Some Book with a title that does not give away the subject",
    "author": "Some Author",
    "subject": "Unknown"
  }
]
```
Please analyze the provided image and generate the JSON output.


### **Step 3: Review the JSON Output**
Gemini 1.5 Pro processed the image and returned structured **JSON data**:
```
[
  {
    "title": "Meat",
    "author": "Pat LaFrieda",
    "subject": "Cooking"
  },
  {
    "title": "Simply Beautiful Photographs",
    "author": "Griffiths",
    "subject": "Photography"
  },
  {
    "title": "Simple",
    "author": "Diana Henry",
    "subject": "Cooking"
  },
  {
    "title": "Salt is Essential",
    "author": "Shaun Hill",
    "subject": "Cooking"
  },
  {
    "title": "gather",
    "author": "Gill Meller",
    "subject": "Cooking"
  },
  {
    "title": "What to Cook & How to Cook it",
    "author": "Jane Hornby",
    "subject": "Cooking"
  },
  {
    "title": "Rick Stein's India",
    "author": "Rick Stein",
    "subject": "Cooking, Travel"
  },
    {
    "title": "The Great British Bake Off",
    "author": "Linda Collister",
    "subject": "Cooking"
  },
{
    "title": "Perfect Cakes & Bakes to Make at Home",
    "author": "Linda Collister",
    "subject": "Cooking"
  },
    {
    "title": "Recharge Your Design Batteries",
    "author": "John Norris",
    "subject": "Design"
  },
{
    "title": "The Complete Guide to Stretching",
    "author": "Christopher M. Norris",
    "subject": "Health, Fitness"
  },

{
    "title": "I'm Not Your Friend, I'm Free",
    "author": "Sam McBratney, Kim Lewis",
    "subject": "Unknown"
},
  {
    "title": "When from Death",
    "author": "John Rawson",
    "subject": "Unknown"
  },
    {
    "title": "An Illustrated Life",
    "author": "Danny Gregory",
    "subject": "Art, Inspiration"
  }
]
```

Step 4: Convert JSON to CSV
Once I had the JSON data, I converted it into a CSV file for use in spreadsheets. Here’s the Python script I used:
```
import pandas as pd

# Load the JSON file into a DataFrame
df = pd.read_json('books.json')

# Save as CSV
df.to_csv('books.csv', index=False)

print("books.json has been successfully converted to books.csv")
```
Now, I could open books.csv in Google Sheets or Excel for further analysis.

![Extracted Book Data](https://raw.githubusercontent.com/ashleysally00/ashleysally00.github.io/main/BooksExcel.png)

Applying This Process to Other Real-World Use Cases
This method of OCR and structured data extraction can be extended beyond books. Here are some real-life applications:

1. Inventory Management
Retailers and warehouses can take shelf photos to automatically extract product names, brands, and barcodes, reducing manual data entry.

2. Logistics & Package Tracking
Shipping companies can scan package labels and extract tracking numbers, recipient names, and addresses into a structured format.

3. Healthcare & Prescription Management

Pharmacists can digitize prescription labels, extracting patient names, medications, and dosage instructions for better record-keeping.
Conclusion
Using Google AI Studio and Gemini 1.5 Pro, you can:

Extract structured data from images using OCR.

Convert JSON to CSV for easier spreadsheet use.
Apply this method to real-world applications in retail, logistics, and healthcare.
This is just one example of how AI can automate tedious tasks and improve efficiency in data processing. AI is changing every day...

Next Steps
Try extracting structured data using Google AI Studio.
Convert the JSON output into CSV for analysis.
Think about how this method can be applied to other industries.
Let me know if you try it! ⭐



