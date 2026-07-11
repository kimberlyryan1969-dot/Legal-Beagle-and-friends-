# Example: Property Dispute Brief

This example shows how to use Legal Beagle and Friends to create a property dispute brief.

## Sample Case: Williams v. Martinez (Property Boundary Dispute)

### Scenario

Two neighboring property owners dispute the boundary line of their adjacent properties. 
Mr. Williams claims the boundary is at a certain fence line based on his deed, while 
Ms. Martinez claims it's several feet to the west based on adverse possession.

### Step 1: Property Information

**Property Description:**
- Address: 150 Oak Street, Anytown, State
- Lot Size: Approximately 2 acres
- Description: Residential property with house, driveway, and fence

**Dispute Details:**
- Disputed area: 50-foot strip along western property line
- Fence erected: 1985 by previous owner
- Current dispute started: 2024 when Ms. Martinez built garage

### Step 2: Create Brief with Legal Beagle

```python
from agents.document_writer import document_writer
from agents.citation_manager import citation_manager

# Add relevant citations for property law
citations = [
    citation_manager.add_statute_citation("Title 5, Chapter 105, § 105.3", "2023"),
    citation_manager.add_case_citation(
        "Williams v. Martinez", "State Reporter", "page", "2024"
    ),
    citation_manager.add_statute_citation("Adverse Possession Statute, § 522.3", "2023"),
]

# Create property brief
brief = document_writer.create_property_dispute_brief(
    property_description="""
    Real property located at 150 Oak Street, Anytown, consisting of 
    approximately 2 acres with a single-family residence built in 1995.
    The property is described in the deed as follows: [insert legal description]
    """,
    dispute_details="""
    The parties dispute the boundary line separating the Williams and Martinez 
    properties. The dispute concerns approximately 50 feet of the western property 
    line. Ms. Martinez claims this area through adverse possession (open, notorious, 
    exclusive possession for 20+ years marked by a fence). Mr. Williams claims 
    the boundary is established by his deed and survey.
    """,
    ownership_claims=[
        "Mr. Williams: Owns to the fence line based on valid deed and recent survey",
        "Ms. Martinez: Claims adverse possession of the disputed strip based on 39 years of exclusive possession and maintenance",
        "Historical fence: Built in 1985 and maintained continuously by previous owner"
    ],
    supporting_evidence=[
        "Original deed from 1992 showing legal description",
        "Recent survey from 2024 showing boundary per deed",
        "Tax assessments showing property line at deed boundary",
        "Property records showing continuous fence maintenance",
        "Witness testimony regarding fence construction in 1985",
        "Photos showing current fence and Ms. Martinez's use"
    ]
)

print(brief['content'])
```

### Step 3: Output Format

```
PROPERTY DISPUTE BRIEF

I. PROPERTY DESCRIPTION
Real property located at 150 Oak Street, Anytown, consisting of 
approximately 2 acres with a single-family residence built in 1995...

II. DISPUTE DETAILS
The parties dispute the boundary line separating the Williams and Martinez 
properties. The dispute concerns approximately 50 feet of the western property line...

III. OWNERSHIP CLAIMS

1. Mr. Williams: Owns to the fence line based on valid deed and recent survey
2. Ms. Martinez: Claims adverse possession of the disputed strip based on 39 years 
   of exclusive possession and maintenance
3. Historical fence: Built in 1985 and maintained continuously by previous owner

IV. SUPPORTING EVIDENCE

1. Original deed from 1992 showing legal description
2. Recent survey from 2024 showing boundary per deed
3. Tax assessments showing property line at deed boundary
[Additional evidence listed...]

V. LEGAL ANALYSIS

A. Adverse Possession Requirements

Under [State] law, adverse possession requires: (1) actual possession, (2) open 
and notorious possession, (3) exclusive possession, and (4) continuous possession 
for the statutory period (20 years in this jurisdiction).

B. Applicability to This Case

While Ms. Martinez may have maintained the fence area for 39 years, the fence 
was originally erected by the prior owner with Mr. Williams' knowledge and consent, 
negating the "adverse" element. The deed and survey controls the boundary.

C. Relevant Statute

[State] Statute § 522.3 establishes the adverse possession standard and requires 
that possession be truly adverse (hostile to true owner's rights).
```

## Property Law Research

Use Legal Beagle to research property law issues:

```python
from agents.research_agent import research_agent

# Research adverse possession
results = research_agent.search_property_law(
    "adverse possession boundary fence continuous possession"
)

# Research boundary disputes
results = research_agent.search_property_law(
    "boundary line determination deed survey conflict"
)

# Research fence disputes
results = research_agent.search_property_law(
    "boundary fence encroachment trespass remedies"
)
```

## Key Elements for Property Briefs

1. **Exact Property Description** - Legal description from deed
2. **Chain of Title** - Ownership history
3. **Survey Information** - Current surveys and markings
4. **Adverse Possession Analysis** - If applicable
5. **Deed Language** - Exact boundary language
6. **Tax Records** - Government records
7. **Historical Evidence** - Photos, witness testimony
8. **Applicable Statutes** - State property laws

## Common Property Dispute Issues

1. **Boundary Disputes** - Disagreement about property lines
2. **Adverse Possession** - Long-term use by non-owner
3. **Encroachment** - Structure built on neighbor's land
4. **Easement Disputes** - Rights to cross or use neighbor's land
5. **Deed Ambiguity** - Unclear language in original deed
6. **Survey Conflicts** - Disagreement between surveys

## Evidence to Gather

- Original deed and any amendments
- Surveys (old and new)
- Tax assessment records
- Property records from government office
- Photos and videos of property
- Witness statements (especially long-term residents)
- Fence or improvement maintenance records
- Insurance records
- Historical maps or documents

## Tips for Property Briefs

- **Be precise with measurements** - Use exact distances and coordinates
- **Include visual aids** - Sketches and survey maps
- **Document possession** - Photos showing use and maintenance
- **Get expert opinions** - Surveyor and possibly appraiser
- **Research jurisdiction law** - Adverse possession rules vary by state
- **File promptly** - Statutes of limitation apply

## Next Steps

1. Consult with a real estate attorney
2. Obtain current survey
3. Gather all historical documents
4. Research applicable state law using Legal Beagle
5. Prepare evidence and witness statements
6. File formal dispute action if necessary

**Important**: Property disputes can be complex. Always consult with a qualified real estate attorney before taking action!
