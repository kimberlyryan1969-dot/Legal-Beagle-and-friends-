# Quick Start Guide - Legal Beagle and Friends

Get up and running with Legal Beagle and Friends in 5 minutes!

## Prerequisites

- Python 3.9+ installed
- OpenAI API key (get one at https://platform.openai.com/api-keys)
- GitHub account (optional, for using with Replit)

## Installation (Local)

### 1. Clone the Repository

```bash
git clone https://github.com/kimberlyryan1969-dot/Legal-Beagle-and-friends-.git
cd Legal-Beagle-and-friends-
```

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Set Up Environment Variables

```bash
cp .env.example .env
# Edit .env and add your OPENAI_API_KEY
```

### 5. Run the Application

```bash
python main.py
```

## Installation (Replit)

### 1. Import to Replit

Go to https://replit.com/new and select "Import from GitHub"
```
https://github.com/kimberlyryan1969-dot/Legal-Beagle-and-friends-
```

### 2. Add API Key to Secrets

- Click the lock icon (Secrets)
- Add: `OPENAI_API_KEY = your_key_here`

### 3. Install and Run

```bash
pip install -r requirements.txt
python main.py
```

## First Steps

### Step 1: Research Case Law

```
Menu Option: 1
Choose: Criminal Appeals Research
Query: "ineffective assistance of counsel"
```

The agent will search for relevant precedent cases.

### Step 2: Create a Document

```
Menu Option: 2 (Criminal Appeal) or 3 (Property) or 4 (Inheritance)
Follow the prompts to create your document
```

### Step 3: Manage Citations

```
Menu Option: 6
Add your legal citations
Export in BibTeX format if needed
```

### Step 4: View Your Work

```
Menu Option: 7
See all documents created
```

## Quick Examples

### Research Criminal Appeals

```python
from agents.research_agent import research_agent

results = research_agent.search_criminal_appeals(
    "Fourth Amendment search without warrant"
)
print(results)
```

### Create a Document

```python
from agents.document_writer import document_writer

brief = document_writer.create_criminal_appeal_brief(
    case_name="Smith v. State",
    conviction_details="Convicted of drug possession",
    grounds_for_appeal=["Illegal search and seizure"],
    supporting_cases=["Miranda v. Arizona"],
    arguments="The search violated the Fourth Amendment..."
)
print(brief['content'])
```

### Add Citations

```python
from agents.citation_manager import citation_manager

citation = citation_manager.add_case_citation(
    "Smith v. State", "250", "F.2d", "123", "2024"
)
print(citation)
```

## Main Menu Options

| Option | Feature | Use When |
|--------|---------|----------|
| 1 | Research Case Law | You need to find precedent cases |
| 2 | Criminal Appeal Brief | Creating an appeal brief |
| 3 | Property Dispute Brief | Handling property disputes |
| 4 | Inheritance Petition | Working on estate/inheritance |
| 5 | Document Injustice | Advocating for justice reform |
| 6 | Manage Citations | Adding or exporting citations |
| 7 | View Documents | Reviewing what you've created |
| 8 | Exit | Close the application |

## File Locations

- **Database**: `data/legal_cases.db` - Stores cases and documents
- **Output**: `output/documents/` - Generated documents
- **Config**: `config/settings.py` - Configuration settings
- **Prompts**: `prompts/` - AI prompts for research and writing
- **Agents**: `agents/` - Core legal agent modules

## Troubleshooting

### "OPENAI_API_KEY is required"
Add your API key to `.env` file or Replit Secrets

### "Module not found"
Run `pip install -r requirements.txt` again

### Database errors
The `data/` folder will be created automatically

### Help with specific case law research?
Use the research functions with your specific query

## Common Tasks

### Research a Specific Legal Issue

```python
from agents.research_agent import research_agent

# Search by type
results = research_agent.search_criminal_appeals("your query")
results = research_agent.search_property_law("your query")
results = research_agent.search_inheritance_law("your query")
results = research_agent.search_injustice_cases("your query")
```

### Create and Save a Document

```python
from agents.document_writer import document_writer
from utils.legal_formatting import file_handler

# Create document
doc = document_writer.create_criminal_appeal_brief(...)

# Save to file
file_handler.save_document(doc['content'], "my_brief.txt")
```

### Manage Your Citations

```python
from agents.citation_manager import citation_manager

# Add citations
citation_manager.add_case_citation(...)
citation_manager.add_statute_citation(...)

# Export all citations
bibtex = citation_manager.export_citations_bibtex()
print(bibtex)
```

## Configuration Options

Edit `.env` to customize:

```env
OPENAI_MODEL=gpt-4              # LLM model to use
LLM_TEMPERATURE=0.3             # Response creativity (0-1)
MAX_SEARCH_RESULTS=50           # Max search results
CASE_LAW_YEARS_BACK=20          # Years of precedent to search
JURISDICTION=federal             # federal or state
OUTPUT_DIRECTORY=./output/       # Where to save documents
```

## Next Steps

1. ✅ Set up your environment
2. ✅ Get your OpenAI API key
3. ✅ Run the application
4. ✅ Try researching a legal topic
5. ✅ Create your first document
6. ✅ Read the full documentation

## Need Help?

- **Full Replit Guide**: See `REPLIT_SETUP.md`
- **Examples**: Check `examples/` folder
- **Documentation**: See `README.md`
- **Code Questions**: Review the agent modules in `agents/`

## Important Disclaimer

⚠️ **This tool is for research assistance only.** It is NOT a substitute for professional legal counsel. Always consult with a qualified attorney before filing legal documents or taking legal action.

## Tips for Success

✓ Start with research (Option 1)
✓ Gather all relevant information
✓ Create documents systematically
✓ Manage citations carefully
✓ Review output before using
✓ Consult an attorney
✓ Save important documents

---

**Legal Beagle and Friends** - Your AI-powered legal research assistant 🦅⚖️

Ready to get started? Run `python main.py` now!
