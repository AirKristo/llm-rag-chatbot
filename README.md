Retrieval-Augmented Chatbot

This project implements a chatbot using retrieval-augmented generation (RAG). The idea is to combine a large language model (LLM) with a document retrieval layer so that the model can answer questions based on actual context rather than hallucinating.

Overview

The chatbot works in two modes:

* Naive prompting – simply passing the user question to the LLM.

* RAG prompting – retrieving relevant text chunks from a knowledge base and including them in the prompt.

I compared the two approaches on a set of research documents to see how retrieval changes the quality of answers.

Key points

* I experimented with chunk size and settled on around 200 words. This was a good balance between too little context and too much noise

* The prompt template adds the query and the retrieved text before asking the model for an answer

In practice:

* When asked “Who is the founder of NYU?”, the naive model hallucinated a name, while the RAG version said “I don’t know.”

* On “difference between hot and cold fusion”, the naive model produced a vague and partly wrong statement, while the RAG version again admitted it didn’t have enough context

This shows RAG reduces hallucinations and makes the model more honest about what it doesn’t know.
