# Detekcia toxického obsahu na webe

Autor: Michal Jusko  
Rok: 2025  
Fakulta elektrotechniky a informatiky, TUKE

Tento repozitár obsahuje Jupyter notebooky a experimenty vytvorené v rámci bakalárskej práce „Detekcia toxického obsahu na webe“. Cieľom práce bolo otestovať viaceré prístupy ku klasifikácii komentárov ako toxických alebo netoxických – naprieč rôznymi jazykmi (slovenčina, angličtina) a pomocou rôznych typov modelov (monojazyčné, multilingválne, aj LLM modely ako ChatGPT).

## Prehľad notebookov

### Slovenský model
- `final-slovak-bert.ipynb`  
  Tréning a vyhodnotenie modelu SlovakBERT na slovenskom datasete (`hate_speech_slovak`).  
  Úloha: binárna klasifikácia

### Anglické modely
- `final-toxic-bert-binar.ipynb`  
  ToxicBERT trénovaný na anglických dátach (`civil_comments`).  
  Úloha: binárna klasifikácia

- `final-toxic-bert-miltilabel.ipynb`  
  Multilabel klasifikácia anglických komentárov (okrem `severe_toxicity`).  
  Triedy: `toxicity`, `obscene`, `threat`, `insult`, `identity_attack`, `sexual_explicit`

### Multilingválny model
- `final-xml-roberta.ipynb`  
  Tréning XLM-RoBERTa modelu na kombinovaných EN+SK dátach (`civil_comments`, `hate_speech_slovak`, `toxi-text-3M`)  
  Úloha: binárna klasifikácia

### Modely ChatGPT
- `chatgpt-zero-shot.ipynb`  
  Zero-shot klasifikácia komentárov pomocou OpenAI ChatGPT (bez finetuningu)

- `chatgpt-few-shot.ipynb`  
  Few-shot klasifikácia s niekoľkými príkladmi v promptoch

## Spustenie

1. Klonovanie repozitára:
   ```
   git clone https://github.com/Michal-Jusko/Detekcia_toxickeho-_obsahu_na_webe.git
   ```

2. Inštalácia závislostí (ak používaš lokálne prostredie):
   ```
   pip install -r requirements.txt
   ```

3. Otvor a spusti notebook podľa potreby (Google Colab, Kaggle, Jupyter Lab).

Odporúčaná verzia Pythonu: 3.10+

## Použité knižnice

- transformers, datasets, scikit-learn
- pandas, matplotlib, seaborn
- openai (pre ChatGPT časť)

Niektoré notebooky vyžadujú Hugging Face token alebo OpenAI API kľúč.

## Dáta

Použité datasety je potrebné stiahnuť manuálne (nie sú súčasťou repozitára):

- https://huggingface.co/datasets/civil_comments
- https://huggingface.co/datasets/TUKE-KEMT/hate_speech_slovak
- https://huggingface.co/datasets/FredZhang7/toxi-text-3M

Po stiahnutí ich uložte do priečinka `data/`.

## Výstupy

Väčšina notebookov obsahuje:

- klasifikačné metriky (F1, precision, recall, accuracy)
- vizualizácie priebehu trénovania (grafy lossov a presnosti)
- CSV a PNG výstupy v priečinku `results/`
- zakomentované poznámky a alternatívne experimenty

## Kontakt

V prípade otázok: michal.jusko.2@student.tuke.sk
