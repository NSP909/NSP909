# Priyadarshan Narayanasamy

CS + Neuroscience (double degree) and Computational Finance at the University of Maryland. I build ML systems and ship full-stack products. 20x hackathon winner, MLH Top 50 (2025), published at ICML 2025 and 2026.

[![Website](https://img.shields.io/badge/nsp.sh-1f6feb?style=flat-square&logo=google-chrome&logoColor=white)](https://nsp.sh)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nspd)
[![Devpost](https://img.shields.io/badge/Devpost-003e54?style=flat-square&logo=devpost&logoColor=white)](https://devpost.com/nspriyadarshan)
[![Email](https://img.shields.io/badge/Email-ea4335?style=flat-square&logo=gmail&logoColor=white)](mailto:nspd@terpmail.umd.edu)

## About

I care about building technology that actually changes outcomes for people, not just Agentic Slop. The work I'm proudest of sits where real problems meet hard engineering: helping visually impaired people sense their surroundings, reading focus straight off brain signals, cutting medical errors out of healthcare data. That mix of neuroscience and machine learning is what I keep coming back to, and I want to spend my career turning that kind of research into things people can hold and use.

I work across ML research and production engineering. On the research side that means spatially-aware LLMs, EEG-based neural interfaces, and AI text detection. On the product side it means document-processing and agent pipelines that run at scale. GPA 3.982/4.000, Michael Antonov Scholar, Dean's List every semester.

I've won 20 of 24 hackathons over two years, which put me on [MLH's 2025 Top 50](https://www.cs.umd.edu/article/2025/10/umd-student-recognized-mlh-top-50-list), selected from a pool of 500,000+ developers.

## Publications

**Beyond Perplexity: Character Distribution Signatures and the MDTA Benchmark for AI Text Detection** ([arXiv:2605.01647](https://arxiv.org/abs/2605.01647)), accepted at the ICML 2026 Hypothesis Testing Workshop. A way to detect AI-generated text from character distribution patterns instead of model probabilities, with a Letter Distribution Score and the 642,000-sample MDTA benchmark. Layered on existing detectors it lifts AUROC and F1, especially in narrow domains where vocabulary is more constrained.

**SING: Spatial Context in Large Language Models for Next-Gen Wearables** ([arXiv:2504.08907](https://arxiv.org/abs/2504.08907)), accepted at ICML 2025. A CNN spatial encoder and intermodal projection layer that cut median Direction-of-Arrival error from 88.5 degrees to 13.0 degrees using a single microphone, plus a LoRA-tuned Llama 3.2 3B reaching 25.7-degree mean DoA error for spatially-aware ASR with up to 5 simultaneous speakers.

## Experience

**Software Engineering Intern, Google** (May 2026 to Present)

**Full-Stack ML Engineering Intern, Gencise AI** (Dec 2024 to Present)
- Built a document parsing pipeline pairing a fine-tuned Google Document AI (trained on 400+ synthetically generated forms) with Gemini and HTML template-based data augmentation, raising F1 from 0.75 to 0.91 across 20,000+ documents in production.
- Engineered an async Microsoft Graph API email processor with batch optimization and document caching that cut processing from 15 minutes to 2 minutes per application while handling 1,000+ daily emails, storing files in AWS S3 via boto3 with metadata in PostgreSQL.
- Architected 7 microservices across 4 verticals on LangGraph workflows, exposed through Flask blueprint REST APIs (15 endpoints) backed by SQLAlchemy, handling entity extraction, validation, conflict resolution, and database population with source-backtracking and 35 automated tests; shipped on Docker/Kubernetes with GitHub Actions CI/CD.
- Built a FastAPI premium quote generator computing exposure-based premiums across coverage types, enriched with custom web scrapers and the Google Places, Yelp, and TripAdvisor APIs.

**Machine Learning Research Intern, Kaliber Labs** (May 2024 to Dec 2024)
- Led a cross-functional team building a data querying pipeline on a modified RAG2SQL architecture with semantic agents, reaching 94% accuracy across 2,000+ test queries.
- Deployed LLaVA for surgical monitoring by fine-tuning Llama 3.2 3B and training a custom image-to-text projection layer on 48,000 manually labeled frames from 200 surgical videos.
- Engineered custom vector databases indexing 120,000+ embeddings across 40,000 pages, tuning chunking and retrieval latency for training and inference.
- Designed APIs for remote ML model serving across multiple production integrations.

**Research Assistant, iCosMos Lab at UMD** (Aug 2024 to Present)
- Co-authored SING (see Publications), building the CNN spatial encoder and intermodal projection layer and LoRA-tuning Llama 3.2 3B for spatially-aware ASR.
- Developing an LLM-generated text detector from letter distribution signals, reaching 0.99 AUROC on a custom 350,000+ sample benchmark across models, domains, and temperatures.
- Developing an SNN that uses bi-hemispherical attention to map EEG signal patterns to spatial audio locations for neural sound localization.

**Co-Founder and Vice President, AI/ML Club at UMD** (Mar 2024 to Present)
- Co-founded the club and grew it from 8 to 600+ members across disciplines in two semesters.
- Led a 4-person research project on oryx movement patterns using DBSCAN clustering, Shapley filtering, and PCA to relate movement groups to time and season.
- Ran workshops on RAG, fine-tuning, transformers, and more.

## Selected Projects

**[FocusFlow](https://devpost.com/software/focus-flow-y63tzm)** (1st Overall, HackUMBC 2025)
A brain-computer interface that reads concentration directly off your brain instead of guessing from timers and self-reports. A Muse headband streams 5 EEG channels at 256Hz over Bluetooth; the pipeline filters the signal and pulls band-power features across Alpha, Beta, Theta, Delta, and Gamma using 6-second sliding windows. The model is a HemiAttentionLSTM, a bidirectional network with cross-hemispherical attention that captures how the two hemispheres interact during focus, trained with focal loss and weighted sampling to handle class imbalance. It hits 87% accuracy across 5 attention states. FastAPI serves predictions over async WebSockets at sub-100ms latency, and a Next.js dashboard shows live focus state plus historical trends.

**[SixthSense](https://devpost.com/software/sixthsense-xuw41r)** (1st Overall, HackPrinceton Spring 2025)
A wearable that lets visually impaired users feel their surroundings through touch. Meta glasses capture the scene, YOLOv8 detects objects, and object names are turned into embedding vectors. An inverse Fourier transform converts each embedding into a distinct vibration pattern, so a glove signals what an object is while a servo-driven gauntlet points toward where it is, splitting the "what" and "where" pathways the way the brain does. Multiple objects blend into one comfortable signal, and testing showed the encoding is mathematically consistent: similar objects correlate at 71.7% versus 10.2% for different ones. Built with Python, Next.js, Arduino, and vibration and servo motors.

**[TaxDaddy](https://devpost.com/software/taxdaddy)** (3rd Overall, Hacklytics 2025 at Georgia Tech)
A callable AI accountant. It bridges Twilio and OpenAI's Realtime API over WebSockets so you can phone in, ask questions about your documents, and get walked through filing by voice. Behind it, 5 specialized agents coordinate through a multi-agent graph doing live RAG and tool calling. OCR extracts data from uploaded forms into MongoDB in under 7 seconds, PyPDF Filler populates the actual fields, and a Benford's-Law layer flags fraud and anomalies in the numbers.

**[SolSpeak](https://devpost.com/software/n-kp7oqy)** (Solana and Blockchain Track Winner, HackNYU 2025)
Hands-free DeFi by voice. Say "swap 2 SOL to USDC" and it executes, plus price checks, transfers, portfolio balances, tax estimates, and cross-border payments, all in plain language. The voice agent runs on Twilio WebSockets and the Realtime API, with a Pinecone vector DB indexing Solana docs for accuracy and Helius and CoinGecko feeding live data. Rust smart contracts were deployed to Solana mainnet-beta, not just devnet, inside the 24-hour window.

**Pulsify** (Honorable Mention, BioHack 2024)
A healthcare query system that routes one natural-language question through 3 parallel channels (patient records, clinical trials, medical imaging). NLP-to-SQL translation hits 87% accuracy in under 3 seconds across 20,000+ records, a per-document schema generator unifies incompatible EHR formats, and source-verified retrieval backtracks every answer to its origin to cut hallucinations and preventable medical errors. Image queries run through a custom Llama 3.2 3B with a LLaVA-style projection layer.

**L-LMS** (Fetch.ai "Beyond Boundaries" Track Winner, HackMIT 2024)
A multi-agent tutor built on LangGraph, with separate agents for query refinement, context analysis, and response generation. A 15,000+ embedding vector DB with semantically partitioned segments and Redis caching keeps responses under 2 seconds, and a hybrid setup pairs Llama 3.1 for fast generation with GPT-4o for precision, wired into the Canvas API with OCR for coursework.

Full list including HireFlow, Vector Mentor, AnchorVision, OpenSwarm, and Pitcher lives on [Devpost](https://devpost.com/nspriyadarshan).

## Stack

**Languages:** Python, Java, JavaScript, C, SQL

**ML/AI:** PyTorch, TensorFlow, HuggingFace, Transformers, CNNs, LSTMs, SNNs, LoRA fine-tuning, LangChain, LangGraph, RAG, RAG2SQL, vector DBs, OpenAI, Claude, Gemini, OCR, OpenCV, signal processing

**Web/Backend:** React, Next.js, Flask, FastAPI, WebSockets, Twilio, REST, async

**Data:** PostgreSQL, MongoDB, SQLAlchemy, NumPy, SciPy, Pandas, Matplotlib

**Cloud/DevOps:** AWS (S3, EC2, Lambda), Google Cloud (Document AI, Vertex AI, BigQuery, Places API), Azure, Docker, Kubernetes, GitHub Actions, Git

## Awards

**2025**
- MLH Top 50, chosen from 500,000+ developers
- 1st Overall, HackUMBC 2025
- 1st Overall, HackPrinceton Spring 2025
- 3rd Overall, Hacklytics 2025 at Georgia Tech
- Solana and Blockchain Track Winner, HackNYU 2025
- Best Use of Terraform/Cloud, HoyaHacks 2025 at Georgetown
- Judge and Mentor, ML Track (400+ participants), Bitcamp at UMD

**2024**
- 2nd Overall, Demo Day, Harvard Hacker House
- 2nd Overall, HackPrinceton Fall 2024
- Warm-Up Challenge Winner, MIT Energy and Climate Hackathon
- Honorable Mention, BioHack 2024 (Nucleate PGH)
- 3rd Overall, Demo Day, Harvard Hacker House
- 1st Overall, HackUMBC 2024
- Fetch.ai "Beyond Boundaries" Track Winner, HackMIT 2024
- 2nd Overall, KatyYouthHacks 2024
- Best Use of AI/ML Innovation (FSK Bridge Recovery), Bitcamp at UMD
- Best Finance Hack (Capital One), HackPrinceton Spring 2024
- Spark of Genius Award, Hack CEWIT 2024 at Stony Brook
- Elevance Healthcare Track Winner (MediCompile), Hacklytics 2024
- Best Digital Forensics Hack (CtrlF MyVideo), HoyaHacks 2024
- Dean's List, University of Maryland

**2023 and earlier**
- Best Hack, CodeDay Amritsar 2023
- Most Entertaining Hack ("Never Gonna Let You Sleep"), Epoch 2023 (Hack Club)

## Stats

<p align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=NSP909&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=NSP909&layout=compact&theme=tokyonight&hide_border=true" />
</p>

Open to research collaborations and good teams. Reach me at nspd@terpmail.umd.edu or [nsp.sh](https://nsp.sh).
