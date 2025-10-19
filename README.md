# Athlete's Temple Business Chatbot

A sophisticated business chatbot built with Gradio and OpenAI/Gemini that serves as an intelligent concierge for Athlete's Temple fitness and martial arts club.

## Features

- **Intelligent Q&A**: Answers questions about the business using a comprehensive knowledge base
- **Lead Collection**: Automatically captures customer interest and contact information
- **Feedback Logging**: Records unanswered questions for follow-up by staff
- **Tool Integration**: Uses OpenAI function calling for automated data collection
- **Mobile-Friendly UI**: Built with Gradio for responsive web interface
- **Dual Provider Support**: Works with both OpenAI and Gemini APIs

## Project Structure

```
├── business_agent.ipynb          # Main Jupyter notebook with chatbot implementation
├── feedback.csv                  # Logged unanswered questions and feedback
├── leads.csv                     # Collected customer leads and contact information
├── me/
│   ├── business_summary.txt      # Core business knowledge base
│   └── about business.pdf        # Additional business documentation
├── 1. C3 - Assignment.pdf        # Assignment instructions
├── requirements.txt              # Python dependencies
└── README.md                     # This file
```

## Setup Instructions

### Prerequisites

- Python 3.8+
- OpenAI API key or Gemini API key

### Installation

1. Clone this repository:
```bash
git clone <repository-url>
cd athlete-temple-chatbot
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file in the project root:
```env
OPENAI_API_KEY=your_openai_api_key_here
PROVIDER=openai
OPENAI_MODEL=gpt-4o-mini
OPENAI_TEMPERATURE=0.6
OPENAI_TOP_P=0.9
OPENAI_MAX_TOKENS=400
```

### Running the Application

1. Open the Jupyter notebook:
```bash
jupyter notebook business_agent.ipynb
```

2. Run all cells to start the application

3. The Gradio interface will launch automatically with a local URL and public sharing link

## How It Works

### Knowledge Base
The chatbot uses `me/business_summary.txt` as its authoritative source of information about Athlete's Temple, including:
- Mission and services
- Team member profiles
- Unique value propositions

### Tool Functions
The chatbot includes two main tools:

1. **`record_customer_interest`**: Captures customer contact information and notes when they express interest
2. **`record_feedback`**: Logs questions that couldn't be answered from the knowledge base

### Data Collection
- **Leads**: Stored in `leads.csv` with timestamp, name, email, notes, and source
- **Feedback**: Stored in `feedback.csv` with timestamp, user message, status, and tags

## Usage Examples

### Customer Questions
- "What martial arts classes do you offer?"
- "Tell me about your personal training programs"
- "Who are your coaches?"

### Lead Collection
When customers express interest or ask questions not covered in the knowledge base, the chatbot automatically:
1. Logs the interaction
2. Asks for contact information
3. Saves the lead for follow-up

## Technical Details

### Architecture
- **Frontend**: Gradio web interface
- **Backend**: OpenAI API with function calling
- **Data Storage**: CSV files for leads and feedback
- **Knowledge Management**: Text-based business summary

### Key Components
- `agentic_chat_once()`: Core chat function with tool calling
- `record_customer_interest()`: Lead capture functionality
- `record_feedback()`: Feedback logging system
- Gradio UI with multiple tabs for chat, leads, and logs

## Configuration

The application supports various configuration options through environment variables:

- `PROVIDER`: Choose between "openai" or "gemini"
- `OPENAI_MODEL`: Specify the OpenAI model to use
- `OPENAI_TEMPERATURE`: Control response creativity (0.0-1.0)
- `OPENAI_TOP_P`: Control response diversity (0.0-1.0)
- `OPENAI_MAX_TOKENS`: Limit response length

## Data Privacy

- All customer data is stored locally in CSV files
- No data is sent to external services except for AI processing
- Sensitive information should be handled according to privacy regulations

## Future Enhancements

- Integration with CRM systems
- Email automation for lead follow-up
- Analytics dashboard for lead conversion
- Multi-language support
- Voice interface integration

## License

This project is part of an academic assignment for EECE 798S course.

## Contact

For questions about this implementation, please refer to the assignment documentation or course instructor.
