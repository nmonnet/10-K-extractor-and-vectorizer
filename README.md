# 10-K-extractor-and-vectorizer



## Extracting URL and matching with WRDS database

The URL_wrds_matched_extractor.ipynb notebook is designed to retrieve the 10-K reports links of all available stocks on WRDS. To run the code, you must have access to a WRDS account. Additionally, it requires a supplementary file that maps ticker symbols to CIK codes. This file can be downloaded from [SEC's Ticker Symbol File ](https://www.sec.gov/include/ticker.txt) and should be placed in a folder named "data." A version acquired on 24/09/2024 is available in the repository.

## Extracting the 10-K

The 10_Ks_extractor.ipynb notebook enables users to extract 10-K reports from EDGAR using the previously acquired list of URLs. The resulting 10-K reports are transformed into semantically meaningful paragraphs that are long enough to maintain contextual precision, yet short enough to be effectively processed by the BERT model we will be using.



## Converting paragraphs to tokens

The convert_to_tokens.ipynb notebook converts the previously obtained 10-K paragraphs into lists of tokens suitable for interpretation by the BERT model we will be using.


## Converting tokens to vectors

The final section of the code, 10_K_to_vector.ipynb, is the most flexible, as it requires repurposing to suit your specific needs and may be computationally intensive. We provide an example here using the BERT model available at [Hugging Face](https://huggingface.co/yiyanghkust/finbert-tone), which is specialized in analyzing corporate reports, including 10-K and 10-Q filings, earnings call transcripts, and analyst reports. Our example took three weeks to compute on a single computer without splitting the process. The splitter enables the simultaneous processing of multiple parts of the dataset, which can significantly reduce computation time.
