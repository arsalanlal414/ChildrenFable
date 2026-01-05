# Image → Children’s Fable (Vision‑LLM via Ollama)

A minimal web app (single `index.html`) that sends an image and a prompt to a local Ollama vision‑language model, and renders the generated story.

## 1) Install & Run Ollama

- Install Ollama: https://ollama.com/download
- Pull a **vision‑capable** model (choose one that works on your machine):
  ```bash
  ollama pull llama3.2-vision
  # or: ollama pull llava:latest
  # or: ollama pull bakllava
  # or: ollama pull minicpm-v
  ```
- Allow cross‑origin browser requests (if needed) and start the server:
  ```bash
  # On macOS/Linux
  export OLLAMA_ORIGINS=*
  ollama serve

  # On Windows PowerShell
  setx OLLAMA_ORIGINS "*"
  ollama serve
  ```

> The app calls `http://localhost:11434/api/chat`. If your browser still blocks requests, consider running a small local reverse proxy or using a different browser.

## 2) Run the App

Just open `index.html` in a browser (Chrome/Edge/Firefox). No backend required.

1. Upload an image.
2. Choose the model that you have pulled in Ollama.
3. Use the default prompt (or customize it), then click **Generate Story**.

## 3) Real‑World Scenario

**Children’s Fable Generator:** A parent or teacher can turn a child’s drawing or a photo of everyday objects into a short fable that promotes reading, imagination, and values. The model writes a brief story with a moral, easy to read aloud in class.

Alternative scenarios you can implement by changing the prompt:
- **Vehicle brand identification:** “Identify the vehicle make and model and justify your guess.”
- **Food nutrition guidance:** “Describe ingredients in the dish and give allergy warnings.”
- **Retail shelf QA:** “List mislabeled products, price tags, and stock‑outs.”

## 4) Troubleshooting

- _The output mentions the ‘image’ rather than objects_: tighten your prompt (“Do not mention the camera or the word ‘image’. Focus on the scene.”).
- _Empty/odd output_: ensure your chosen model actually supports vision inputs.
- _Slow responses_: try a smaller model or reduce image size before uploading.
- _CORS error_: set `OLLAMA_ORIGINS=*` before `ollama serve`.
- _Model not found_: run `ollama pull <model>` first.

## 5) Report Hints (PDF)

Include:
- **Scenario description** (what problem it solves and who benefits).
- **Screenshots** (input image + generated text from the app).
- **Problems & solutions** (e.g., CORS, model selection, prompt tuning, hardware limits).

---

Generated on 2025-11-08 02:25:06.
