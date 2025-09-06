
# AI-Based Client Clearance Recommendation System  

## Overview  
An advanced AI-powered recommendation engine designed to analyze client requirements and provide tailored software development recommendations. This system combines rule-based logic with semantic similarity matching to deliver intelligent, context-aware suggestions for software platforms, features, technology stacks, and cost estimates.

## Key Features  
- **Hybrid AI Architecture:** Combines rule-based keyword matching with semantic similarity analysis  
- **Context-Aware Clarification:** Asks intelligent follow-up questions for vague inputs  
- **Comprehensive Recommendations:** Suggests platforms, features, tech stacks, timelines, and costs  
- **Scalable Design:** Easily expandable dataset with new business scenarios  
- **Professional-Grade Implementation:** Production-ready code structure with modular components  

## System Architecture  

### Core Components  
1. **NLP Processing Module (`nlp_processor.py`)**  
   - Intent classification using spaCy  
   - Entity recognition for business domains and features  
   - Vagueness detection with heuristic analysis  
   - Context-aware follow-up question generation  

2. **Recommendation Engine (`recommendation_engine.py`)**  
   - Semantic similarity matching using sentence transformers  
   - Cosine similarity-based scenario matching  
   - Confidence scoring for recommendations  
   - Integration with NLP processing module  

3. **Knowledge Base (`client_scenarios.json`)**  
   - Curated dataset of business scenarios  
   - Comprehensive recommendation profiles  
   - Expandable structure for new domains  

### Technical Stack  
- **Natural Language Processing:** spaCy with en_core_web_md model  
- **Semantic Similarity:** Sentence Transformers (all-MiniLM-L6-v2)  
- **Similarity Calculation:** scikit-learn cosine similarity  
- **Data Handling:** JSON-based knowledge base  
- **Development Environment:** Google Colab (Python 3.10+)  

## Installation & Setup  

### Google Colab Implementation  
1. Create a new Colab notebook  
2. Run the installation cell:  
   ```
   !pip install spacy==3.7.2 sentence-transformers==2.2.2 scikit-learn==1.2.2 numpy==1.24.3
   !python -m spacy download en_core_web_md
   ```  
3. Execute remaining cells in order:  
   - Dataset creation  
   - NLP processor implementation  
   - Recommendation engine implementation  
   - Main application  

### Local Installation (Alternative)  
1. Clone the repository  
2. Install dependencies:  
   ```
   pip install -r requirements.txt
   python -m spacy download en_core_web_md
   ```  
3. Run the application:  
   ```
   python main.py
   ```  

## Usage Instructions  

### Interactive Mode  
1. Run the main application cell in Colab or start locally  
2. Type your business requirements when prompted with "You:"  
3. System behavior:  
   - Asks clarifying questions if input is vague  
   - Provides comprehensive recommendations for clear inputs  
   - Displays confidence scores for each recommendation  

### Example Inputs  

**Specific inputs that yield direct recommendations:**  
- "I want to create an online store for handmade products"  
- "I need a delivery tracking app for my courier business"  
- "I run a restaurant and want online ordering"  

**Vague inputs triggering follow-up questions:**  
- "I need an app for my business"  
- "I want to build something online"  
- "How much would software cost?"  

### Output Format  
The system provides:  
- Recommended platforms (Web, Mobile, Desktop)  
- Key domain-specific features  
- Suggested technology stack  
- Estimated development timeline  
- Cost range estimation  
- Confidence score for the recommendation  

## Dataset Structure  
The knowledge base (`client_scenarios.json`) contains scenario entries as follows:  
```
{
  "id": 1,
  "business_domain": "Retail",
  "business_type": "Clothing Store",
  "client_input": "Example input text",
  "client_input_vagueness": "low/medium/high",
  "required_follow_up": "Clarification question or null",
  "recommended_platform": ["Web App", "Mobile App"],
  "recommended_features": ["Feature 1", "Feature 2"],
  "recommended_tech_stack": {
    "frontend": "React.js",
    "backend": "Node.js",
    "database": "PostgreSQL"
  },
  "estimated_dev_time": "3-5 months",
  "estimated_cost_range": "$20,000 - $40,000"
}
```

## Customization & Expansion  

### Adding New Business Domains  
1. Extend domain keywords in the `NLPProcessor` class:  
   ```
   self.domain_keywords = {
     "new_domain": ["keyword1", "keyword2", "keyword3"],
     # ... existing domains
   }
   ```  
2. Add new scenarios to `client_scenarios.json`:  
   ```
   {
     "id": 6,
     "business_domain": "NewDomain",
     // ... complete scenario details
   }
   ```  
3. Update follow-up questions in `generate_follow_up()` method as needed  

### Tuning Performance  
- Adjust similarity threshold in `find_most_similar_scenario()` (default 0.3)  
- Modify vagueness detection thresholds in `analyze_input()`  
- Expand keyword lists for improved intent recognition  

## Testing & Validation  
1. Run the included test cell to verify basic functionality  
2. Test with diverse inputs covering all business domains  
3. Validate follow-up questions are triggered for vague inputs  
4. Confirm recommendation accuracy versus expected outcomes  

## Performance Considerations  
- Precomputed embeddings for efficient similarity matching  
- Lightweight Sentence Transformer (all-MiniLM-L6-v2) for balanced performance  
- Modular component design for independent optimization  

## Limitations & Future Enhancements  

### Current Limitations  
- Limited to predefined business domains present in knowledge base  
- Relies on keyword matching for initial intent classification  
- English language support only  

### Potential Enhancements  
- Integration with large language models for nuanced conversation handling  
- Real-time data integration for dynamic technology stack suggestions  
- Multi-language support via translation APIs  
- Frontend UI/UX for enhanced user experience  
- Integration with project management and tracking tools  

## Ethical Considerations  
- Uses synthetic and anonymized data only  
- Clearly communicates system limitations and estimate nature  
- Confidence scoring provided to indicate certainty levels  

## Support  
- spaCy documentation: [https://spacy.io/](https://spacy.io/)  
- Sentence Transformers documentation: [https://www.sbert.net/](https://www.sbert.net/)  
- Google Colab documentation: [https://colab.research.google.com/](https://colab.research.google.com/)  

## License  
This project is provided as part of the Rayonix Solutions internship program. Please refer to your program guidelines for usage terms.

---



