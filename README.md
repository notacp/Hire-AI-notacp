# HireAI - AI-Powered Tech Recruiting Copilot

HireAI is a browser-based hiring copilot that helps in-house tech recruiters run natural-language searches over uploaded résumés, extract key skills/location/experience, and send personalized outreach emails—cutting manual sourcing time from hours to minutes.

## Project Setup

### Prerequisites

- Node.js 18+ and npm
- Supabase account with Service Role key
- Groq API key for LLM integration

### Environment Setup

1. Create a `.env` file based on the `env.template`:

```sh
# Copy the template
cp env.template .env

# Edit the .env file with your actual keys
```

2. Install dependencies:

```sh
npm install
```

3. Run the Supabase setup script to create necessary tables and storage:

```sh
node scripts/setup-supabase.mjs
```

4. Start the development server:

```sh
npm run dev
```

## Implemented Features

### Phase 2: Resume Processing Pipeline

The resume processing pipeline has been implemented with the following components:

1. **Resume Upload UI** - A drag-and-drop interface for uploading resumes in PDF, DOC, or DOCX format
2. **PDF Text Extraction** - Using pdf.js to extract text content from uploaded PDF files
3. **Classical Parser** - Regex-based parsing to extract basic candidate information
4. **Supabase Storage** - Storing the original resume files in a secure Supabase bucket
5. **Groq API Integration** - Generating embeddings for semantic search and candidate summaries
6. **Database Storage** - Storing parsed candidate data in Supabase PostgreSQL with pgvector

## Project Structure

- `/src/components/resume` - Resume upload components
- `/src/utils` - Utilities for PDF parsing, resume processing, and storage
- `/src/integrations` - API integrations (Supabase, Groq)
- `/src/config` - Environment configuration
- `/scripts` - Setup and maintenance scripts

## Next Steps

The next phase to implement is Phase 3: Search functionality with pgvector to enable natural language searches over the resume database.

## Technologies

- Vite
- TypeScript
- React
- shadcn-ui
- Tailwind CSS
- Supabase (Auth, Storage, Database)
- pgvector for embeddings storage
- Groq API (Llama-3.3-70B)
