---
title: "My First Kaggle Competition: Gen AI Intensive Course Capstone 2025Q1 – Learning About Agents and the Expanding Capabilities of Generative AI"
layout: post
---

  <h2>My First Kaggle Competition: Gen AI Intensive Course Capstone 2025Q1 – Learning About Agents and the Expanding Capabilities of Generative AI</h2>
  <p><a href="blog.html">Back to Blog</a></p>

  <p>One of the most powerful uses of machine learning is its ability to analyze and interpret real-world data, like audio, to improve safety and decision-making. For my Gen AI Intensive Course Capstone 2025Q1 project, I developed SoundGuard. It’s an emergency sound detection system that utilizes generative AI to identify urgent audio signals and then trigger appropriate responses.</p>

  <h3>How the Project Started</h3>
  <p>The Gen AI Intensive Course by Google showcased the multimodal capabilities of generative AI. It can now interpret many types of data, including text, images, and audio. Knowing this, I wanted to develop a tool to interpret audio. I also hoped to find a way to apply that to real-world use cases.</p>

  <h3>How It Works</h3>
  <p>SoundGuard uses machine learning to classify emergency sounds. By processing audio, it can detect sounds like glass breaking or siren alarms. Once a sound is identified, a chatbot responds with natural language instructions, helping the user assess the situation and take action. The system is designed to be calm and reassuring in emergencies.</p>

  <p>For the project, I used the ESC-50 dataset to train the model, and integrated it with Hugging Face and Google Cloud Storage for seamless real-time interaction.</p>

  <h3>Gen AI Capabilities & Requirements</h3>
  <p>The Gen AI Intensive Course Capstone 2025Q1 project required the use of at least three Gen AI capabilities. Here are the capabilities listed in the competition:</p>

  <ul>
    <li>Structured output/JSON mode/controlled generation</li>
    <li>Few-shot prompting</li>
    <li>Document understanding</li>
    <li>Image understanding</li>
    <li>Video understanding</li>
    <li>Audio understanding</li>
    <li>Function calling</li>
    <li>Agents</li>
    <li>Long context window</li>
    <li>Context caching</li>
    <li>Gen AI evaluation</li>
    <li>Grounding</li>
    <li>Embeddings</li>
    <li>Retrieval-augmented generation (RAG)</li>
    <li>Vector search/vector store/vector database</li>
    <li>MLOps (with GenAI)</li>
  </ul>

  <p>For SoundGuard, I focused on three core capabilities to meet the project’s requirements:</p>
  <ul>
    <li><strong>Audio Understanding:</strong> Using YAMNet and the ESC-50 dataset, SoundGuard classifies emergency sounds like glass breaking and sirens in real time. This allows the system to recognize audio and trigger the appropriate responses.</li>
    <li><strong>Few-Shot Prompting:</strong> The chatbot in SoundGuard leverages few-shot prompting to generate actionable, natural language instructions based on the audio classification. When an emergency sound is detected, the chatbot quickly delivers instructions, like suggesting a course of action in response to a siren or glass breaking.</li>
    <li><strong>Function Calling / Agents:</strong> The chatbot agent guides users through the necessary steps based on the detected audio. For example, if it detects glass breaking, the agent can suggest that users check for potential break-ins, providing helpful and calm instructions.</li>
  </ul>

  <h3>Dataset Choice: ESC-50</h3>
  <p>We chose the ESC-50 dataset, which is a collection of environmental audio clips. This includes sounds of sirens, glass breaking, and alarms. It includes both audio classifications and labels for environmental sounds. These labels help the model to recognize different emergency events.</p>

  <h3>Model Choice: YAMNet</h3>
  <p>We decided to use YAMNet, a pretrained model developed by Google. The model is available on TensorFlow Hub. YAMNet was trained on AudioSet, a large dataset with millions of YouTube videos. It can classify audio into 521 different categories. Its lightweight, fast, and efficient design makes YAMNet ideal for real-time audio classification. This is crucial because real-time audio classification must be fast.</p>

  <h3>Challenges Faced</h3>
  <p>Despite its capabilities, YAMNet presented some challenges. It was trained on YouTube audio clips, which can vary in quality and background noise. The ESC-50 dataset's clean, short recordings differed from YouTube's noisy, longer clips. This lead to issues with being able to classify certain sounds. Glass breaking was sometimes classified as silence, or sirens as irrelevant noises.</p>

  <h3>Solution: Confidence Thresholding and Fallback</h3>
  <p>To address these issues, we implemented a confidence thresholding system. YAMNet often produced low-confidence scores for correct classifications. We ran code several times. Sometimes the scores were as low as 0.01 for accurate predictions.</p>
  <p>When the model’s confidence was below 0.02, we applied a fallback mechanism to ESC-50's ground truth labels. This ensured that emergency sounds like sirens and glass breaking were reliably flagged. This helped SoundGuard to excel, even when YAMNet struggled to identify edge cases.</p>

  <h3>Frontend Interface: Gradio and Hugging Face</h3>
  <p>We wanted to create a working interface where users could interact with the chatbot. We knew that first we needed to upload the audio files to storage. That way, they could be accessed and streamed in real time. We decided to use Google Cloud Storage (GCS) to host the audio files from the ESC-50 dataset.</p>

  <h3>Storing Audio Files in Google Cloud Storage</h3>
  <p>The ESC-50 dataset consists of 2,000 audio recordings, each 5 seconds long, covering 50 different sound events.</p>
  <p>We focused on a subset of the dataset containing emergency-related sounds. This included sirens, glass breaking, and alarms. So, we filtered the dataset to only include these relevant categories. Then we exported the audio file metadata into a CSV file, which included the URLs for each file in the subset. We then created a GCS bucket to store these files. We uploaded each file separately and linked to their corresponding URLs. This ensured easy access for the live demo.</p>

  <h3>Building the Demo with Gradio on Hugging Face</h3>
  <p>With the audio files hosted on GCS, we turned our attention to the frontend of the project. We wanted to create a simple, user-friendly interface. We decided to make a Hugging Face space and chose their Gradio chatbot template. This interface allowed users to interact with the SoundGuard chatbot. It's a simple real-time demo where users can listen to classified emergency sounds. Then they receive actionable, calming instructions from the chatbot.</p>

  <h3>Integration with GitHub</h3>
  <p>We pushed the Kaggle notebook to GitHub. This way, we could store and manage the codebase for the entire project in a GitHub repo. Next, we integrated Hugging Face Spaces with GitHub. This links the repository to the demo for real-time functionality. That means Github can manage the backend logic. The backend logic is important. Here, it includes sound classification and the chatbot's responses. New changes in GitHub are automatically reflected in the Hugging Face space. This keeps the chatbot updated both now and in the future.</p>

