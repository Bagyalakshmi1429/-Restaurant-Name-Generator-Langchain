# Restaurant-Name-Generator-Langchain
This project is a Restaurant Name Generator that uses LangChain to integrate a large language model (LLM) for creative content generation. It takes a user-selected cuisine type and generates a restaurant name along with menu items for that cuisine. 

**Tools Used**

Streamlit: Creates an interactive web app for user input and output display.

LangChain: Structures sequential prompt workflows for smooth integration with the LLM.

ChatGroq LLM: Generates creative restaurant names and menu items based on prompts.

Environment Variables: Secures the GROQ_API_KEY for API authentication.

**Work Flow**

**User Interaction (main.py):**

The Streamlit app displays a sidebar where users select a cuisine type (e.g., Indian, Italian).

The selection triggers a function call to generate the restaurant name and menu items using the backend logic.

**Backend Processing (langchain_helper.py):**

**Step 1: Restaurant Name Generation**

A PromptTemplate is defined to instruct the LLM:

"I want to open a restaurant for {cuisine} food. Suggest a fancy name for this."

The LangChain LLMChain executes the prompt using the LLM, producing a creative restaurant name.

**Step 2: Menu Items Generation**

Another PromptTemplate is defined for menu suggestions:

"Suggest some menu items for {restaurant_name}. Return it as a comma-separated string."

The LLMChain takes the restaurant name generated in Step 1 as input and produces a list of menu items.

**Step 3: Sequential Workflow**

**A SequentialChain combines both tasks:**

The output of Step 1 (restaurant name) becomes the input for Step 2.

This ensures a cohesive and contextually accurate menu generation process.

**Final output is a dictionary containing:**

**restaurant_name:** The generated restaurant name.

**menu_items:** A comma-separated string of menu items.

**Result Display (main.py):**

The app receives the output dictionary from the backend.

The restaurant name is displayed as a header.

The menu items are split into a list and displayed as individual entries.


**Sequential Chaining:** Ensures logical flow where the generated restaurant name informs menu creation, maintaining thematic consistency.

**LLM Temperature Setting:** A creative temperature of 0.9 generates varied, imaginative outputs while staying relevant.

**Reusable Prompts:** Clear, modular prompts allow for easy updates or adaptations.

**Secure Credentials:** Environment variables ensure the API key remains confidential.
