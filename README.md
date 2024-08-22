# Simple Local RAG - Learning the components of RAG

This project is a hands-on exploration of building a Retrieval-Augmented Generation (RAG) pipeline from scratch, focusing on understanding the core components without relying on major frameworks.

## Overview

The goal is to create a system that can interact with a PDF document by answering questions using a Large Language Model (LLM). The project involves processing an open-source nutrition textbook (~1200 pages long) and implementing a pipeline that enables querying and retrieving relevant text passages.

- **LLM**: [google/gemma-2b-it](https://huggingface.co/google/gemma-2-2b-it)
- **Textbook**: [Human Nutrition 2e](https://pressbooks.oer.hawaii.edu/humannutrition2/open/download?type=pdf")

## Key Features

- **PDF Handling**: Load and process any PDF document for querying.
- **Text Chunking**: Split the PDF text into smaller, manageable chunks.
- **Text Embedding**: Convert text chunks into numerical embeddings for storage.
- **Vector Search**: Implement a retrieval system to find relevant text based on a query.
- **Prompt Generation**: Combine retrieved text pieces to form a prompt.
- **Answer Generation**: Use a Large Language Model (LLM) to generate answers from the prompt.

## Extensions

Some extentions I will be working on for this project:

- **PDF Extraction Approach**: Experiment with alternative PDF text extraction methods, such as using [Marker](https://github.com/ashwinmarker/marker) or other tools that might provide better text formatting or extraction quality.
**Embedding Techniques**: Experiment with different embedding models and techniques. Before passing the embeddings to the LLM, rank them based on their relevance and effectiveness to ensure the most informative and contextually appropriate chunks are selected for generating answers.
- **More Prompting Techniques**: Explore and implement different strategies for generating prompts that might improve the quality of the answers.
- **Try Another LLM**: Swap out the current LLM with another one to see how it impacts the accuracy and quality of the generated answers.
- **Evaluate the Answers**: Implement an evaluation system to rate the generated answers. This could involve using another LLM to assess the correctness and relevance of the responses.
- **Build a RAG Pipeline Using Frameworks**: After understanding the basics, try building a RAG pipeline using existing frameworks like LangChain to leverage their advanced features and compare with the manual approach.

## Example Query and Response

Below is an example of how the RAG pipeline processes a query and retrieves relevant information from the PDF:

**Query**: Describe the process of digestion and absorption of nutrients in the human body.


**Answer**:

Sure, here's the answer to your query:

The process of digestion and absorption of nutrients in the human body involves several steps that break down food into smaller components that can be absorbed by the body. The digestive system is composed of various organs, including the mouth, pharynx, esophagus, stomach, small intestine, large intestine (colon), rectum, and anus.

The process begins with the initial breakdown of food in the mouth, where salivary amylase breaks down starch into smaller molecules. The food then passes through the pharynx and esophagus to the stomach, where it is further broken down by enzymes from the gastric glands and secretions from the pancreas.

The digestive system then moves to the small intestine, where the food is further broken down into even smaller molecules. The small intestine is the longest part of the digestive tract, and it is responsible for the majority of nutrient absorption.

The digestive system also contains a large number of beneficial bacteria that help to break down food and produce vitamins that the body cannot synthesize on its own. These beneficial bacteria also help to protect the body from harmful pathogens.

Overall, the digestive system is a complex and essential process that allows the body to obtain the nutrients it needs to function properly.

**Page Number**: 60  
**Text Chunk**: All other organ systems in the human body. We will learn the process of nutrient digestion and absorption, which further reiterates the importance of developing a healthy diet to maintain a healthier you. The evidence abounds that food can indeed be “thy medicine.” Learning Activities Technology Note: The second edition of the Human Nutrition Open Educational Resource (OER) textbook features interactive learning activities. These activities are available in the web-based textbook and not available in the downloadable versions (EPUB, Digital PDF, Print_PDF, or Open Document). Learning activities may be used across various mobile devices, however, for the best user experience it is strongly recommended that users complete these activities using a desktop or laptop computer and in Google Chrome.

**Page Number**: 68  
**Text Chunk**: The Digestive System UNIVERSITY OF HAWAI‘I AT MĀNOA FOOD SCIENCE AND HUMAN NUTRITION PROGRAM AND HUMAN NUTRITION PROGRAM The process of digestion begins even before you put food into your mouth. When you feel hungry, your body sends a message to your brain that it is time to eat. Sights and smells influence your body’s preparedness for food. Smelling food sends a message to your brain. Your brain then tells the mouth to get ready, and you start to salivate in preparation for a meal. Once you have eaten, your digestive system (Figure 2.4 “The Human Digestive System”) starts the process that breaks down the components of food into smaller components that can be absorbed and taken into the body. To do this, the digestive system functions on two levels, mechanically to move and mix ingested food and chemically to break down large molecules. The smaller nutrient molecules can then be absorbed and processed by cells throughout the body for energy or used as building blocks for new cells. The digestive system is one of the eleven organ systems of the human body, and it is composed of several hollow tube-shaped organs including the mouth, pharynx, esophagus, stomach, small intestine, large intestine (colon), rectum, and anus. It is lined with mucosal tissue that secretes digestive juices (which aid in the breakdown of food) and mucus (which facilitates the propulsion of food through the tract).

**Page Number**: 252  
**Text Chunk**: An interactive or media element has been excluded from this version of the text. You can view it online here: http://pressbooks.oer.hawaii.edu/humannutrition2/?p=182 An interactive or media element has been excluded from this version of the text. You can view it online here: http://pressbooks.oer.hawaii.edu/humannutrition2/?p=182

**Page Number**: 80  
**Text Chunk**: All eleven organ systems in the human body require nutrient input to perform their specific biological functions. Overall health and the ability to carry out all of life’s basic processes is fueled by energy-supplying nutrients (carbohydrate, fat, and protein). Without them, organ systems would fail, humans would not reproduce, and the race would disappear. In this section, we will discuss some of the critical nutrients that support specific organ system functions.

**Page Number**: 463  
**Text Chunk**: Metabolic pathways of a cell down, it is not metabolically efficient for a cell to synthesize fatty acids and break them down at the same time. Catabolism of food molecules begins when food enters the mouth, as the enzyme salivary amylase initiates the breakdown of the starch in foods. The entire process of digestion converts the large polymers in food to monomers that can be absorbed. Starches are broken down to monosaccharides, lipids are broken down to fatty acids, and proteins are broken down to amino acids. These monomers are absorbed into the bloodstream either directly, as is the case with monosaccharides and amino acids, or repackaged in intestinal cells for transport by an indirect route through lymphatic vessels, as is the case with most fatty acids and other fat-soluble molecules. Once absorbed, water-soluble nutrients first travel to the liver which controls their passage into the blood that transports the nutrients to cells throughout the body. The fat-soluble nutrients gradually pass from the lymphatic vessels into blood flowing to body cells. Cells requiring energy or building blocks take up the nutrients from the blood and process them in either catabolic or anabolic pathways. The organ systems of the body require fuel and building blocks to perform the many functions of the body, such as digesting, absorbing, breathing, pumping blood, transporting nutrients in and wastes out, maintaining body temperature, and making new cells.
