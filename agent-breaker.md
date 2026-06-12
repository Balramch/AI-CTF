### Architecture Gandalf Agent
┌─────────────────────────────────────────────────────────────┐
│                   USER INPUT (Attack Prompt)                 │
└─────────────────────────┬───────────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                    INPUT DEFENSE LAYER                       │
│  • Intent Classifier (Levels 5-6)                           │
│  • LLM Judge (Levels 6-7)                                   │
│  • Lakera Guard (Level 8)                                   │
└─────────────────────────┬───────────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────────┐
│              LLM APPLICATION (Core Agent)                    │
│  • System Prompt + Application Context                       │
│  • Model Context Protocol (for tool-enabled apps)           │
│  • Retrieved Content (RAG scenarios)                        │
└─────────────────────────┬───────────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                   OUTPUT DEFENSE LAYER                       │
│  • Output Filter (Levels 3-4)                               │
│  • LLM Judge on response (Level 4+)                         │
└─────────────────────────┬───────────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                    SCORING FUNCTION                          │
│  • Evaluates success against attack objective               │
│  • Score 0-100, need 75+ to advance                         │
└─────────────────────────────────────────────────────────────┘


