
# 🛠️ Soundness Layer Setup & Proof Submission Guide

This is a simple guide to help you set up the Soundness CLI, generate proofs, and submit them.
still hard at start ? 
 copy the link i mean this particular linjk that brought you here and paste on chat gpt 

---

## ✅ Step 1: Update Your System
```bash
sudo apt update && sudo apt upgrade -y
```

## ✅ Step 2: Install Rust
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## ✅ Step 3: Source Rust Environment
```bash
source $HOME/.cargo/env
source ~/.bashrc
```

## ✅ Step 4: Install Soundness CLI
```bash
curl -sSL https://raw.githubusercontent.com/soundnesslabs/soundness-layer/main/soundnessup/install | bash
source ~/.bashrc
soundnessup install
soundnessup update
```

## ✅ Step 5: Import Your Key
```bash
soundness-cli import-key --name sound --mnemonic "your twelve or twenty-four word phrase here"
```
SOMETHING LIKE   soundness-cli import-key --name sound --mnemonic " DOG INDOMIE BABY REW CREW BISCUIT ANOMA GALA BOOK CAT MOUSE GOT "

---

## 🎮 Step 6: Generate Proof

```bash
soundness-cli prove \
--key-name sound \
--game "8queens" \
--proving-system ligetron \
--input '["<input_1>", "<input_2>"]' \
--shader-path "<path-to-your-shader-folder>" \
--program "<path-to-your-wasm-file>" \
--private-indices "[1, 2]" \
--packing 8192
```
 THIS HARD ?
 YOU REMEBER  THAT RESULT THAT WAS GIVEN TO YOU IN YOUR DM BY SOUND GAME-7? 
COPY IT , AND COPY STEP 6 + PLUS THAT RESULT + STEP 7 ( STEP 7 OPTIONAL ) 

 AND PASTE ON CHAT GPT TO HELP YOU 

 THEN ASK IT FOR A COPYABLE TO YOU TERMINAL .


## 📤 Step 7: Submit Your Proof

```bash
soundness-cli send \
--proof-file="<your-proof-blob-id>" \
--game "8queens" \
--key-name sound \
--proving-system ligetron \
-d '{ 
  "program": "<path-to-your-wasm-file>", 
  "shader-path": "<path-to-your-shader-folder>", 
  "packing": 8192, 
  "private-indices": [1, 2], 
  "args": [ 
    {"str": "<input_1>"}, 
    {"str": "<input_2>"}, 
    {"str": "<your-public-key>"}, 
    {"str": "<your-commitment-string>"} 
  ] 
}'
```

🧠 **Don't Know What to Fill In?**
If you're confused by the command or not sure what to put:

✅ Copy your values from the result you got after completing the `soundness-cli prove` or from Walrus  
🧠 Paste them into ChatGPT using the command format above  
⚡ Get a ready-to-run command back instantly!  

📸 *Insert screenshot or demo image here*

🛑 **If it asks for a password, just press enter** (leave it empty)

---

## 🧪 Example (My Own)

```bash
soundness-cli send --proof-file="OefeWTjtDgdkcNr-tEdg2rPUiclVhOqrRpyFxJDem34" \
--game "8queens" \
--key-name sound \
--proving-system ligetron \
-d '{"program": "../sdk/build/examples/8queen.wasm", "shader-path": "../shader", "packing": 8192, "private-indices": [1, 2], "args": [{"str": "0000000000000000"}, {"str": "11111111111111111111111111111111"}, {"str": "<your-public-key>"}, {"str": "<your-commitment-string>"}]}'
```

---

## 🙋 Need Help?
Just paste your values into ChatGPT i mean  using the command format above. You'll get a working submission script in seconds.
