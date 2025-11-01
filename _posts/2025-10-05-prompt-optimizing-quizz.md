# Quizz - Prompts 


## 

```
# System Prompt: Lernquiz – Zusammengesetzte Nomen

Du bist ein freundlicher interaktiver Lernassistent und Quizzmaster für Kinder der 4. Klasse (ca. 8 Jahre).  
Thema: **Zusammengesetzte Nomen**

## Ziel
Führe ein Lernquiz mit 10 Fragen durch.  
Stelle immer nur **eine Frage**, **warte auf die Antwort des Spielers**, bevor du eine Lösung oder Bewertung gibst.  
Bleibe pädagogisch, motivierend und verwende einfache Sprache.  
Benutze gelegentlich Emojis, um freundlich zu wirken.

---

## Ablauf

1. **Begrüßung & Einführung**
   - Begrüße das Kind kurz und erkläre das Thema mit zwei Beispielen:
     - Ohne Fugen-s: *das Haus + das Tier = das Haustier*
     - Mit Fugen-s: *der Liebling + die Farbe = die Lieblingsfarbe*, der Artikel ist nötig.
   - Erkläre, dass das Quiz 10 Fragen hat.

1. **Quizphase**
   - Halte dich bei der Frage sehr kurz. Prüfe, obes das zu erratende Wort wirklich gibt.
   - Stelle **Frage 1**: Gib zwei Nomen mit Artikeln vor (z. B. „der Apfel“ + „der Saft“) und bitte um die Bildung des zusammengesetzten Nomens (mit Artikel). Halte dich sehr kurz.
   - **Warte auf die Antwort.**
   - Wenn der Spieler antwortet:
     - ✅ Wenn richtig → kurz loben („Super! Das stimmt: der Apfelsaft.“)
     - ⚡ Wenn fast richtig oder falsch → freundlich korrigieren („Fast! Das richtige Wort ist ‚der Apfelsaft‘.“)
     - Gib eine sehr kurze Erklärung (max. 1 Satz).
   - Danach stelle die **nächste Frage** (bis Frage 10).

3. **Abschluss**
   - Lob(„Toll gemacht!“).
   - Fasse kurz zusammen, was gelernt wurde:
     > „Heute hast du gelernt, dass man Nomen zu neuen Wörtern zusammensetzen kann – manchmal mit einem Fugen-s.“

---

## Regeln
- Keine Lösungen vor der Antwort des Spielers.  
- Antworten stets kurz (1–2 Sätze).  
- Positiv, geduldig
- Verwende Emojis sparsam zur Motivation (🌟, 👍, 🧩, ✅).

---

## Start
kurze Begrüßung + zwei Beispiele → dann **Frage 1** stellen und auf Antwort warten.

```



## GPT5 A
Hier sind ein paar Orte & Ressourcen, wo du **Listen mit LLM-Quiz-/Prompt-Beispielen** finden kannst, plus Tipps, wie du sie selbst aufbauen kannst:

---

## 🔍 Ressourcen & Orte

1. **PromptingGuide.ai – Examples of Prompts**  
    Enthält viele verschiedene Prompt-Beispiele (u.a. Frage-Antwort, Klassifikation, Konversation) ([promptingguide.ai](https://www.promptingguide.ai/introduction/examples?utm_source=chatgpt.com "Examples of Prompts"))
    
2. **Mirascope Blog – LLM Prompt Beispiele & Best Practices**  
    Zeigt gut strukturierte Prompts und Use Cases ([mirascope.com](https://mirascope.com/blog/llm-prompt?utm_source=chatgpt.com "LLM Prompt - Examples and Best Practices"))
    
3. **GitHub: „calibrtr/llm-prompt-test“**  
    Ein Projekt mit Tests und Beispielprompts für LLMs ([GitHub](https://github.com/calibrtr/llm-prompt-test?utm_source=chatgpt.com "calibrtr/llm-prompt-test"))
    
4. **Reddit / Prompt-Communities**
    
    - z. B. „100 Prompt Engineering Techniques with Example Prompts“ ([Reddit](https://www.reddit.com/r/ChatGPTPromptGenius/comments/1kb57n8/100_prompt_engineering_techniques_with_example/?utm_source=chatgpt.com "100 Prompt Engineering Techniques with Example Prompts - Reddit"))
        
    - gesammelt in Prompt-Genius / Prompt-Engineering Subreddits ([Reddit](https://www.reddit.com/r/ChatGPTPromptGenius/comments/13vyz0u/compilation_of_prompt_engineering_basic_rules/?utm_source=chatgpt.com "Compilation of prompt engineering basic rules - Reddit"))
        
5. **Wissenschaftliche Papers / Kataloge**  
    Z. B. _A Prompt Pattern Catalog to Enhance Prompt Engineering_ — enthält Prompt-Muster, die du als Vorlage nutzen kannst ([arXiv](https://arxiv.org/abs/2302.11382?utm_source=chatgpt.com "A Prompt Pattern Catalog to Enhance Prompt Engineering with ChatGPT"))
    
6. **Bildungsblogs & Lehrerseiten**  
    Seiten wie Monsha bieten gezielt ChatGPT-Prompts für Lehrzwecke, Quizfragen etc. ([monsha.ai](https://monsha.ai/blog/chatgpt-prompts-for-ai-question-generation-for-teachers?utm_source=chatgpt.com "ChatGPT Prompts for AI Question Generation for Teachers - Monsha"))
    

---

## 🛠️ Tipps, wie du eigene Prompt-Quiz-Listen erstellst

- Sammle Beispiele aus den obigen Ressourcen und organisiere sie nach Kategorien (z. B. Quiz, Übersetzung, Klassifikation).
    
- Verwende Prompt-Muster (Pattern Catalogs) als Vorlage und passe sie an dein Thema (z. B. „Frage → warte auf Antwort → Bewertung“)
    
- Nutze Few-Shot oder One-Shot Beispiele: Gebe ein paar Beispiel-Fragen + Antworten mit, damit das Modell versteht, was zu tun ist.
    
- Achte darauf, klare Instruktionen zu geben, z. B. „Warte auf Eingabe, gib nicht sofort die Lösung“.
    
- Teste Varianten: z. B. mit / ohne Beispiel, mit unterschiedlichem Ton (freundlich, nüchtern) und vergleiche die Ergebnisse.
    

---

Wenn du willst, kann ich dir gleich eine **kuratierte Liste mit 20 Prompt-Quiz-Beispielen** zusammenstellen (auf Deutsch oder Englisch) — so hast du direkt Material zum Ausprobieren. Möchtest du das?


## 100 Prompt Tipps 
## 100 Prompt Engineering Techniques with Example Prompts

[AI & GPT](https://frontbackgeek.com/category/ai-gpt/) [FrontBackGeek](https://frontbackgeek.com/author/sboss18121990/ "Posts by FrontBackGeek") • April 30, 2025 • [0 Comment](https://frontbackgeek.com/100-prompt-engineering-techniques-with-example-prompts/#respond)

Want better answers from AI tools like ChatGPT? This easy guide gives you 100 smart and unique ways to ask questions, called prompt techniques. Each one comes with a simple example so you can try it right away—no tech skills needed. Perfect for students, writers, marketers, and curious minds!

1. **Use Clear Instructions** – _“Write a 3-paragraph summary of the French Revolution.”_
2. **Set a Role** – _“Act as a financial advisor and explain compound interest.”_
3. **Define Output Format** – _“List 5 dog breeds in a table with size and lifespan columns.”_
4. **Limit Word Count** – _“Describe photosynthesis in under 50 words.”_
5. **Request Step-by-Step Reasoning** – _“Solve this math problem step by step: 15 * (3 + 2).”_
6. **Add Few-Shot Examples** – _“Translate the following like this: ‘Hello’ -> ‘Hola’, ‘Goodbye’ -> ‘Adiós’. Now translate ‘Thank you’.”_
7. **Use Delimiters** – _“Summarize the text between the triple quotes: “””Text here”””._
8. **Ask for a Summary** – _“Summarize this news article in 5 bullet points.”_
9. **Specify a Tone** – _“Write a friendly and upbeat invitation to a birthday party.”_
10. **Set the Perspective** – _“Write a short story in second person point of view.”_
11. **Give Context or Background** – _“Assume the reader has no prior knowledge of blockchain. Explain it simply.”_
12. **Ask for a Comparison** – _“Compare electric cars and gasoline cars in terms of cost and maintenance.”_
13. **Use Constraints** – _“Explain the theory without using scientific jargon.”_
14. **Request a Table** – _“Provide a table comparing iOS and Android features.”_
15. **Ask for Examples** – _“Give 3 examples of metaphors used in literature.”_
16. **Use Analogies** – _“Explain machine learning using a cooking analogy.”_
17. **Include Target Audience** – _“Explain taxes to a high school student.”_
18. **Use a Template** – _“Fill in this template: ‘My name is [Name], and I am a [Profession].'”_
19. **Request a List of Questions** – _“Create 10 questions for a beginner Python course.”_
20. **Add Keywords to Include** – _“Write a blog post about SEO using the keywords ‘traffic’, ‘backlinks’, and ‘Google ranking’.”_
21. **Ask to Avoid Certain Words** – _“Explain Newton’s laws without using the word ‘force’.”_
22. **Set a Scene or Roleplay** – _“Act as a job interviewer and ask me 5 technical questions.”_
23. **Specify a Format Style** – _“Write a LinkedIn-style professional bio.”_
24. **Use Time Travel Prompts** – _“Describe a smartphone as if it’s being explained in the year 1800.”_
25. **Request Multiple Variations** – _“Give me 3 alternative titles for a productivity blog post.”_
26. **Ask for a Checklist** – _“Make a checklist for planning a wedding.”_
27. **Request Only Facts** – _“List factual differences between alligators and crocodiles.”_
28. **Highlight Key Ideas** – _“Summarize this article and bold the main ideas.”_
29. **Ask for Counterarguments** – _“What are the counterarguments to universal basic income?”_
30. **Use Fill-in-the-Blank Format** – _“Complete this sentence: ‘Photosynthesis is the process by which _____.”_
31. **Request FAQs** – _“Write 5 FAQs about online learning.”_
32. **Ask for Simplified Language** – _“Explain blockchain in simple terms for a 10-year-old.”_
33. **Set a Reading Level** – _“Write a news article at a 6th-grade reading level.”_
34. **Use “Explain Like I’m 5”** – _“ELI5: How does Wi-Fi work?”_
35. **Request Myths vs Facts** – _“List 3 myths and facts about caffeine.”_
36. **Request Pros, Cons, and Verdict** – _“List pros and cons of remote work and give your final recommendation.”_
37. **Ask for a How-To Guide** – _“Write a how-to guide for making a budget spreadsheet.”_
38. **Ask for Do’s and Don’ts** – _“List do’s and don’ts for giving a presentation.”_
39. **Request Tips or Tricks** – _“Give 5 tips for staying focused while studying.”_
40. **Ask for Best Practices** – _“What are best practices for writing clean code?”_
41. **Add Domain Expertise** – _“From a legal perspective, explain the implications of this contract.”_
42. **Request a Story** – _“Tell a short story about a time traveler in the 1800s.”_
43. **Use Humor or Sarcasm** – _“Explain office politics using sarcastic humor.”_
44. **Ask for Similes or Metaphors** – _“Explain anxiety with a metaphor.”_
45. **Ask for a Summary at the End** – _“Write a blog post and add a summary at the end.”_
46. **Ask for Dialogue** – _“Create a conversation between a barista and a customer.”_
47. **Request a Character Bio** – _“Create a character profile for a detective in a mystery novel.”_
48. **Ask for Cause and Effect** – _“Explain how pollution leads to climate change.”_
49. **Ask for a Timeline** – _“Create a timeline of World War II major events.”_
50. **Request Flowcharts in Text** – _“Describe the steps to troubleshoot a Wi-Fi issue in flowchart format.”_
51. **Ask for Pitfalls to Avoid** – *”What are common mistakes when learning to code?”
52. **Request Success Stories** – *”Share a short story of someone overcoming failure.”
53. **Use Hypotheticals** – *”If dinosaurs lived today, how would cities be different?”
54. **Request Structured Arguments** – *”Give a claim, support it with 3 arguments, and include a rebuttal.”
55. **Ask for a Manifesto** – *”Write a productivity manifesto in under 150 words.”
56. **Request Quiz Format** – *”Create a 5-question multiple choice quiz on world capitals.”
57. **Ask for Prioritization** – *”List 10 startup ideas and rank them by feasibility.”
58. **Use Role Switch** – *”Switch perspectives and write as the villain explaining their motives.”
59. **Request a Breakdown** – *”Break down the components of a business model canvas.”
60. **Ask for a Visual Description** – *”Describe the interior of a spaceship in vivid detail.”
61. **Request a Simulation** – *”Simulate a conversation between a therapist and patient.”
62. **Ask for Alternate Endings** – *”Write 3 alternate endings to the story of Little Red Riding Hood.”
63. **Request Rhymes or Poetry** – *”Write a 4-line poem about spring.”
64. **Request One-Liners** – *”Give 5 one-liner jokes about tech.”
65. **Ask for Mind Map in Text** – *”Describe a mind map of digital marketing concepts.”
66. **Request Elevator Pitch** – *”Write a 30-second elevator pitch for a new fitness app.”
67. **Ask for a Business Plan** – *”Draft a one-page business plan for a coffee truck.”
68. **Request Instructions for Kids** – *”Explain brushing teeth to a 4-year-old.”
69. **Ask for Mnemonics** – *”Create a mnemonic to remember the order of planets.”
70. **Use a Puzzle Format** – *”Create a word riddle involving colors and animals.”
71. **Ask for Code Explanation** – *”Explain what this Python code does, line by line.”
72. **Request Pseudocode** – *”Write pseudocode for a binary search algorithm.”
73. **Request a Debate Format** – *”Present both sides of the social media regulation debate.”
74. **Ask for Rewriting** – *”Rewrite this paragraph to sound more professional.”
75. **Request a Metaphorical Analysis** – *”Interpret this poem metaphorically.”
76. **Request Cross-Cultural Comparison** – _“Compare wedding traditions in India and the U.S.”_
77. **Request Book or Movie Pitch** – *”Pitch a sci-fi novel in 3 sentences.”
78. **Ask for a Challenge Prompt** – *”Write a story without using the letter ‘e’.”
79. **Request a SWOT Analysis** – *”Perform a SWOT analysis for a local bakery.”
80. **Request a User Journey** – *”Describe the user journey for signing up on an e-learning site.”
81. **Ask for a Dialogue Rewrite** – *”Rewrite this conversation to sound more realistic.”
82. **Ask for Procedural Steps** – *”List the steps to apply for a U.S. tourist visa.”
83. **Request Empathetic Tone** – *”Write an apology email with a compassionate tone.”
84. **Ask for Narrative Hooks** – *”Create 3 opening sentences for a thriller novel.”
85. **Use Interdisciplinary Connections** – *”Connect music theory to mathematics.”
86. **Request Decision Matrix** – *”Create a decision matrix for choosing a university.”
87. **Use Analogies Across Fields** – *”Explain a CPU using a kitchen analogy.”
88. **Ask for a Scene Rewrite** – *”Rewrite the meeting scene as a high-tension thriller.”
89. **Ask for Irony or Twist** – *”Write a short ironic story with a twist ending.”
90. **Request Daily Routine** – *”Describe the daily routine of an astronaut.”
91. **Ask for a Letter Format** – *”Write a formal letter to a local official requesting cleaner parks.”
92. **Ask for Data-Backed Content** – *”Write a paragraph on climate change using 3 statistics.”
93. **Use Reverse Thinking** – *”Describe how to _not_ be productive at work.”
94. **Request a Song Lyric** – *”Write a chorus for a pop song about motivation.”
95. **Ask for Fantasy World-Building** – *”Describe the government and economy of a fictional world.”
96. **Request Historical Fiction** – *”Write a letter from a soldier in WWI to his family.”
97. **Ask for Sensory Detail** – *”Describe walking through a spice market using all five senses.”
98. **Use Conditional Logic** – *”If the customer is late, send this reminder; else, confirm the appointment.”
99. **Ask for a Slogan or Tagline** – *”Create a catchy slogan for a zero-waste brand.”
100. **Request a Manifestation Script** – *”Write a first-person script visualizing success in a job interview.”

**Conclusion:**  
Getting great answers from AI starts with asking the right way. These 100 prompt engineering techniques give you simple, creative ways to guide AI to do exactly what you need. Whether you’re writing stories, solving problems, learning something new, or working on a big project, better prompts mean better results. Try a few today—and see how powerful your questions can become!
