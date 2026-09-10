---
title: "Use Your LM Studio Models in Ollama (No Re-Download!)"
description: "Already have models in LM Studio? Import them into Ollama in 5 easy steps. No re-downloading, no coding needed."
tags: [ollama, lm-studio, local-llm, gguf, windows]
---

Downloaded a bunch of models in LM Studio? 📦

Now you want to try Ollama... and it wants you to download them **all over again**? 😩

Nope. Let's just move them over. It takes about 5 minutes. ⏱️

> 🖥️ **Example:** Qwen3 8B on Windows. Works with any `.gguf` model.

---

## Step 1: Copy the Model Path 📋

In LM Studio, go to **My Models** → click **⋯** next to your model → **Copy absolute path**.

![Copy absolute path in LM Studio](images/01-lm-studio-copy-path.png)

It looks something like this:

```text
C:/Users/YOU/.cache/lm-studio/models/lmstudio-community/Qwen3-8B-GGUF/Qwen3-8B-Q4_K_M.gguf
```

---

## Step 2: Make a Modelfile 📝

1. Create a folder, like `C:\ollama-models`
2. Inside it, create a file called `Modelfile.txt`
3. Type `FROM`, a space, then paste **your** path:

```text
FROM C:/Users/YOU/.cache/lm-studio/models/lmstudio-community/Qwen3-8B-GGUF/Qwen3-8B-Q4_K_M.gguf
```

Save it. That's the whole file. Really! 😄

![Modelfile with the FROM line](images/02-modelfile.png)

---

## Step 3: Install Ollama ⬇️

Grab it from [ollama.com](https://ollama.com/download/windows) and install.

Then open **PowerShell** and type:

```bash
ollama list
```

![Empty ollama list](images/04-ollama-list-empty.png)

Empty? Perfect. Let's fill it up. 👇

---

## Step 4: Import the Model ✨

```bash
cd C:\ollama-models
ollama create qwen3 -f .\Modelfile.txt
```

💡 `qwen3` is just a nickname. Call it anything you like!

![ollama create success](images/05-ollama-create.png)

See **success**? You did it! 🎉

> ⚠️ **Heads up:** Ollama makes its own copy of the model, so you'll need some free disk space.

---

## Step 5: Say Hi! 👋

```bash
ollama run qwen3
```

Type a message, hit **Enter**, and chat away. 💬

![Chatting with Qwen3 in the terminal](images/07-chat-in-terminal.png)

Not a terminal fan? Open the **Ollama app** and pick `qwen3` from the list. 🖱️

![Qwen3 in the Ollama app](images/08-ollama-app.png)

---

## Want to Remove It? 🗑️

```bash
ollama stop qwen3
ollama rm qwen3
```

Relax, your LM Studio copy stays safe. 😌

---

## Stuck? 🤔

- **File not found?** Make sure your path ends with `.gguf` and you ran `cd` to the right folder first.
- **`ollama` not recognized?** Close PowerShell and open it again.

---

That's it! **One model, two apps, zero re-downloads.** Happy chatting! 🤖
