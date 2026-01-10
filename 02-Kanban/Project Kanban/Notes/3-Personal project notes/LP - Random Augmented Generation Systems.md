# RAG systems - learning hub 
## Current Status 
**Weekend:** 1 of 4
**Day:** 1 of 8
**Focus:** What is RAG?
**Time invested:** 0 hours
**Mood:** a bit worn down

---
## Progress
```dataview
TABLE WITHOUT ID
	"Day" + Day as "Day",
	choice(Status = "Complete", "✅", "◻️") as "Status"
FROM "02-Kanban\Nested Kanban\Notes - RAG"
WHERE Weekend = 1
SORT Day = ASC
```

```dataview
TABLE WITHOUT ID
	"Day " + Day as "Day",
	choice(Status = "Complete", "✅", "◻️") as "Status"
FROM "02-Kanban/Nested Kanban/Notes - RAG"
WHERE Weekend = 1
SORT Day ASC
```

## Learning Checklist
- [ ] What is RAG?
	- [ ] The problems it solve
	- [ ] Its fundamental mechanics 
- [ ] Embeddings - RAG's foundation
	- [ ] Conceptual understanding
	- [ ] How they work
	- [ ] Key concepts
	- [ ] Finale - embedding vs keyword search
- [ ] Vector database
	- [ ] Purpose
	- [ ] Working principle
	- [ ] Key concepts
	- [ ] Popular options
- [ ] Chunking
	- [ ] Purpose and criticality
	- [ ] Chunking strategies
	- [ ] Key parameters
	- [ ] Advanced concepts
- [ ] Retrieval strategies
	- [ ] Basic retrieval
	- [ ] Key concepts
	- [ ] Advanced retrieval
- [ ] Prompt engineering
	- [ ] Advanced RAG
	- [ ] Agentic RAG
- [ ] Fine-tuning for RAG
	- [ ] What can be tuned? 
	- [ ] When to fine tune?
- [ ] Multi-modal RAG
	- [ ] Beyond text
	- [ ] Challenges
- [ ] Security and privacy 
	- [ ] Key concerns
	- [ ] Solutions
- [ ] Production considerations
	- [ ] Deployment
	- [ ] Monitoring
	- [ ] Scaling
- [ ] Alternatives to RAG
	- [ ] When not to use
	- [ ] Alternative approaches
- [ ] Common RAG failure modes
- [ ] Cost optimization