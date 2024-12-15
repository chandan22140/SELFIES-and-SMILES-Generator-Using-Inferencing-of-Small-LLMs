# SELFIES and SMILES Generator Using Inferencing of Small LLMs  

This project leverages OpenAI's API to generate **SELFIES** and **SMILES** strings for chemical molecules based on their molecular properties. It automates the generation process for a large dataset, using a timeout mechanism to handle API responses efficiently.  

## Features  

- Reads molecular data from a JSON file.  
- Generates **SELFIES** and **SMILES** strings for each molecular entry.  
- Implements a timeout mechanism to handle delayed API responses.  
- Saves the generated results in a structured JSON file.  

## Prerequisites  

1. **Python 3.8 or later**  
2. Required Python libraries:  
   - `openai`  
   - `threading` (standard library)  
   - `json` (standard library)  
   - `time` (standard library)  

To install the `openai` library, use:  
```bash  
pip install openai  
```  

## Project Structure  

- **`cleaned_data.json`**: Input file containing molecular data.  
- **`generated_results.json`**: Output file storing generated SELFIES and SMILES strings.  
- **Main script**: Contains the core logic for API calls and data processing.  

## Usage  

### 1. Prepare the Input Data  

Ensure that your input file, `cleaned_data.json`, exists in the working directory and follows this format:  
```json  
[
    {
        "index": 0,
        "logP": -0.23,
        "qed": 0.76,
        "SAS": 2.34,
        "molecular_description": "Description of molecule"
    },
    ...
]  
```  

### 2. Replace API Key  

Update the script with your OpenAI API key:  
```python  
api_key="your_api_key_here"  
```  

### 3. Run the Script  

Execute the script to generate SELFIES and SMILES strings:  
```bash  
python script_name.py  
```  

### 4. Review the Results  

The results will be saved in `generated_results.json` in the following format:  
```json  
[
    {
        "index": 0,
        "generated_selfies": "SELFIES_STRING",
        "generated_smiles": "SMILES_STRING"
    },
    ...
]  
```  

## Key Functionality  

### API Call with Timeout  

The `call_api_with_timeout` function ensures that API requests are completed within a specified timeout period. If the API call exceeds the timeout, the function returns a timeout error.  

### SELFIES and SMILES Generation  

Two prompts are sent to the API for each molecular entry:  
1. To generate the **SELFIES** string.  
2. To generate the **SMILES** string.  

Both outputs are stored in the results file.  

## Notes  

1. Replace the placeholder `api_key` with your actual API key.  
2. The project uses a fixed timeout of 5 seconds for API calls. You can adjust this as needed.  
3. Ensure you have appropriate API permissions and quota for the number of requests.  

## Future Enhancements  

- Add parallel processing for faster generation.  
- Handle missing or invalid data entries in the input file.  
- Support alternative APIs for chemical informatics.  

## License  

This project is licensed under the [MIT License](LICENSE).  

--- 

Let me know if you have more changes in mind!
