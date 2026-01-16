# Discussion 2: 1/14

### Commands:


### How AI Thinks:
Alright—today we’re going to demystify a question that people keep asking in half-serious, half-existential ways: “How does AI think?” And we’re going to do it the way this slide deck intends: conceptually, without diving into the math or code rabbit hole. The goal isn’t to turn you into an ML engineer overnight—it’s to give you a working mental model that’s accurate enough to reason with.  ￼

**“Tree-in-the-woods setup**

The opening slide frames the whole lecture with the classic: “If a tree falls in the woods…” (page 1). That’s not a random philosophy cameo. It’s pointing to a core issue in AI: what counts as “understanding,” “meaning,” or “knowing,” when the system is fundamentally operating on patterns in data.

Humans tend to treat “thinking” as something internal and conscious. But most AI systems—especially modern generative ones—are better understood as machines that model relationships between pieces of information and then produce outputs that statistically fit the situation. The tree question is basically a trap door into: Is AI doing anything like human cognition, or just producing plausible behavior? This deck’s answer is: it mimics cognitive functions, but via very different mechanisms.

**Preliminaries—what we are and aren’t doing**

This is the instructor drawing boundaries (page 2):
- Not covering: algorithms, math, coding, implementation specifics like RAG.
- Covering: a brief history of AI, theories of cognition/language AI mimics, and a conceptual view of the components of AI systems.

Translation: you’re getting the architecture-level story, not the circuit-level story. In STS terms, this matters because people often argue about AI using the wrong “level of explanation.” They’ll demand a human-style explanation from a system that isn’t built like a human, then act shocked when it doesn’t behave like one.

**Domains of cognitive function (human reference point)**

This slide lays out cognitive domains (page 3): attention, executive function, learning & memory, language, perceptual motor control, social cognition.

Important move here: the lecture is setting up an analogy. It’s saying: if we want to talk about AI “thinking,” we can map parts of AI systems to functions that humans have—even if the underlying mechanism is not the same.

Also notice the source framing (DSM-5-TR shown on the slide): that’s a reminder that these “domains” are a formalized way humans talk about cognition, not an objective list handed down by the universe. STS vibe: even the categories we use to describe minds are socially constructed tools.

**Slide 4: Cognitive domains mapped onto a basic AI workflow**

This is one of the most important slides (page 4). The diagram breaks a generative AI system into:
- Generative UI: prompt → response (what you see)
- Generative functions: safety/responsibility filter, context engineering, response generation (the “middle”)
- Knowledge model: knowledge corpus → model generation → working model (the trained system and what it draws from)

Then it maps cognitive domains roughly like:
- Attention, executive function, social cognition (in the generative functions)
- Learning & memory, language (in the knowledge/model side and also during generation)

The big takeaway: what you experience as “chatting with AI” is the thin UI layer over a multi-stage pipeline. The AI isn’t just “answering.” It’s being:
	1.	constrained (safety),
	2.	guided (context engineering),
	3.	generated (response generation),
	4.	grounded in whatever the working model learned from a corpus.

So when the output is weird, it’s not one failure—it could be failure at any stage.

**Slide 5: Learning and memory—why the UCSD street view?**

This slide (page 5) shows a real-world image intersection. It’s basically a metaphor for memory: humans can recognize places, retrieve associated details, and generalize from experience. The lecture is using a concrete scene to set up: AI memory is not like a mental photo album.

Human memory feels like “stored things.” AI “memory,” in modern models, is more like distributed associations—which leads directly into the next slide.

**Slide 6: Holographic vs localized information (two memory metaphors)**

This is the conceptual pivot (page 6).
- Localized memory: discrete tokens stored in specific “places.”
- Holographic memory: meanings distributed across a system; each idea defined relative to other ideas.

The key claim here is basically: LLM-style systems behave more like “holographic memory” than “localized memory.” Not literally holograms—conceptually: information is smeared across many parameters, so no single neuron/weight “is” the definition of a concept.

Why this matters:
	•	It explains why you can’t point to one place in the model and say, “That’s where it stored the fact.”
	•	It explains why models can generalize in spooky ways: because they’ve learned relationships, not just stored entries.
	•	It also explains why they can hallucinate: because they’re not retrieving a “file,” they’re reconstructing a best-fit continuation from distributed patterns.

Slide 7–8: The vector model (dense vectors, tensors) using planets

These slides are doing the core embedding idea in a friendly way (pages 7–8).

They show planets as lists of numbers:
	•	Neptune = [2, 3, 1, 6, …]
	•	Mars = [2, 1, 3, 1, …]
	•	Earth = [1, 1, 0, 4, …]
	•	Jupiter = [1, 1, 0, 4, …]

And they say: each element reflects a relationship between that object and others. Then they name the concepts:
	•	Each object’s vector = dense vector
	•	The matrix of vectors = tensor

What you should understand here:
	•	Vectors are the system’s internal “coordinates” for meaning.
	•	Similar things end up near each other in that space.
	•	“Meaning” becomes geometry: distance, direction, clustering.

One thing to be careful about: the slide’s example makes it sound like humans hand-designed those dimensions (average distance, median, etc.). In real embeddings, the dimensions are not that interpretable. They’re learned features. The point isn’t “dimension 12 equals ‘planet-ness.’” The point is the whole vector encodes a position in a learned meaning-space.

Slide 9: Percy Shelley + pixel cat

This slide looks like a weird detour (page 9), but it’s doing rhetorical work.

The quote is basically warning: we can have expanding power over the external world (science/tech) while shrinking internal life (imagination, “poetry of life”). Then the slide shows waveforms and a pixel art cat.

So what’s the move?
	•	It’s hinting that AI is a machine for patterns (waves/signals), and we’re tempted to confuse pattern mastery with human depth (poetry, agency, moral imagination).
	•	It’s also a warning that our “calculations” might outrun our “conception”—we can build these systems faster than we can socially digest what they mean.

Very STS: capability is not the same thing as wisdom.

Slide 10: Co-occurrence → vector similarity → meaning proximity

This is a clean summary of distributional semantics (page 10):
	•	Tokens that appear closer in training data have more similar vectors.
	•	Tokens with similar vectors are closer in meaning.

This is the engine behind modern language models. It’s the “show me your neighbors and I’ll tell you who you are” version of semantics.

Crucial implication:
	•	AI meaning is largely relational, not grounded in sensory experience.
	•	It’s built from how words/tokens are used across huge corpora.

This is why the model can define “apple” in both fruit and company senses—because the corpora contain both patterns, and the system learns multiple neighborhoods.

Slide 11–14: “You shall know a word by the company it keeps” (Firth) + examples

These slides push the idea with examples (pages 11–14).
	•	Slide 11 quotes Firth: You know a word by the company it keeps.
	•	Slide 12 shows “Carl Likes Cats” and then word-order variants.
	•	Slide 13 expands: “Carl Likes Dogs When they Stay Over There.”
	•	Slide 14 contrasts “Carl Hates” vs “Carl Likes” with different images.

This sequence is doing two things:

1) Distributional meaning

Words get meaning from contexts. “Cats” shows up near “likes,” “pets,” “fur,” “purr,” etc. So the model learns that vector neighborhood.

2) Structure matters (not just a bag of words)

By showing different word orders, the deck is hinting that syntax changes meaning, and AI systems try to model that too—not perfectly, but substantially.

This is also where you can see the bridge from embeddings to “language ability”: it’s not that the model has a dictionary. It’s that it has a learned probability space where certain sequences are more coherent than others.

Slide 15: Workflow diagram returns (repetition on purpose)

This repeats slide 4 (page 15). Repetition in lectures is a feature, not a bug. The instructor wants you to keep coming back to the pipeline: UI → safety → context → generation → model/knowledge.

If you remember only one diagram, it’s this one.

Slide 16: The black box

This slide literally shows a black box (page 16), and it flags the “black box” problem.

In plain language: modern models are often hard to interpret internally, even by their creators. You can measure behavior, you can probe outputs, you can test—yet the internal representations are complex and distributed.

STS angle: “black box” is also social. Systems become black-boxed when:
	•	they’re too complex to inspect,
	•	proprietary barriers block inspection,
	•	and institutions treat outputs as authoritative anyway.

So the black box isn’t just technical opacity—it’s power + opacity.

Slide 17: Model-based research

This slide says many tasks involve direct engagement with the model (page 17):
	•	clustering
	•	classification
	•	similarity-based search
	•	corpus analytics

So generative chat is only one use case. Another big chunk of AI is: use the model as a measurement instrument.

Think of it like this:
	•	Instead of asking the model to write,
	•	you ask the model to organize and relate information—group documents, detect similarity, classify themes.

This matters in “Data Sense” contexts: AI isn’t just a writer-bot. It becomes infrastructure for research workflows.

Slide 18: Let’s talk about inference (focus on the middle layer)

The diagram is shown again with the “generative functions” emphasized (page 18). Inference means: what happens at runtime when you prompt the model (not training).

This is the stage where:
	•	your prompt gets interpreted,
	•	relevant context is weighted,
	•	and output tokens get generated sequentially.

Key idea: the “thinking” you observe is inference-time behavior, built on training-time learned structure.

Slide 19: Executive function (in AI terms)

This slide highlights executive function (page 19). In humans, executive function is planning, controlling attention, coordinating tasks.

In AI workflow terms, “executive function” maps onto:
	•	managing goals and constraints (follow instructions, keep coherence),
	•	deciding what parts of context matter,
	•	maintaining task structure across a response.

This is why instruction-following models feel “more organized” than older ones: you can interpret that as improved “executive control” mechanisms in the overall system design (not one magic neuron).

Slide 20: Safety and responsibility (and social cognition)

This slide highlights the safety/responsibility filter and tags social cognition (page 20).

This is the lecture admitting something important: AI behavior is not only a technical outcome—it is also governed. The system includes a layer designed to reduce harmful outputs.

Two blunt realities:
	1.	This filter is not “the model being moral.” It’s a control layer.
	2.	It shapes what you experience as “what the AI can do,” even if the underlying model could output something else.

So when people argue “AI is biased” or “AI is censored,” they often conflate:
	•	model limitations,
	•	training data,
	•	and safety policy layers.

This slide is telling you to separate those.

Slide 21: Context engineering

This slide isolates “context engineering” (page 21). This is a huge deal.

Context engineering is basically: how the system builds the situation the model is responding to. It includes:
	•	system instructions,
	•	your prompt,
	•	conversation history,
	•	retrieved documents (in some systems),
	•	formatting and role cues.

If the model is the engine, context engineering is the steering wheel. And yes, you can crash the car by steering badly.

Slide 22–23: Attention + ambiguity + “gravity” (Apple the fruit vs Apple the company)

Slide 22 gives the classic ambiguity:
	•	“Please buy an apple and an orange.”
	•	“Apple unveiled a new phone.” (page 22)

Same token, different meaning neighborhood. The model has to decide which “Apple” you mean based on context.

Slide 23 adds the metaphor:
	•	Similar vectors exert more “force” on each other (page 23)

The “gravity” metaphor is trying to help you visualize attention: tokens that are semantically close pull interpretation toward them. In the shopping sentence, “orange” pulls “apple” toward fruit. In the phone sentence, “unveiled” pulls “Apple” toward the company.

So attention here is not just “looking at words.” It’s using learned relationships to resolve meaning under ambiguity.

Slide 24: Attention + NLP structure (parse tree)

This slide is doing a lot (page 24). It shows:
“Carl likes dogs when they are over there.”
and a syntactic parse tree (NP, VP, SBAR, etc.)

Then it says: grammar and syntax affect distance and semantic weight.

Translation:
	•	The model isn’t only tracking which words occur.
	•	It’s tracking how they relate structurally.
	•	The clause “when they stay over there” modifies the liking; it sets a condition. That changes meaning.

So this is the lecture tying together:
	•	distributional semantics (vectors),
	•	attention (what influences what),
	•	and linguistic structure (syntax shaping relationships).

Even if the model isn’t literally running that parse tree, it learns patterns that behave like it “knows” syntax because syntax is statistically encoded in training data.

Slide 25: Response generation (the part everyone thinks is the whole thing)

This slide isolates response generation (page 25). This is where the system produces output token-by-token.

Key conceptual point:
	•	The model is not retrieving a finished answer.
	•	It’s generating the next token repeatedly, conditioned on context.

That’s why it can:
	•	write in styles,
	•	continue arguments,
	•	mimic forms,
	•	but also occasionally produce confident nonsense (because it’s optimizing plausibility, not truth).

A useful mental model: it’s like an autocomplete with a doctorate and no shame.

Slide 26: Questions + the tree comes back

The closing slide returns to “If a tree falls in the woods…” (page 26). It’s bringing you back to the opening question: the system can produce behavior that looks like understanding, but the deeper question is what we mean by “understanding” in the first place.

And that’s the STS hook: AI isn’t just a technical object. It’s a cultural object that forces humans to renegotiate concepts like:
	•	knowledge,
	•	authorship,
	•	expertise,
	•	responsibility,
	•	and meaning.

⸻

Key takeaways
	•	Generative AI is best understood as a pipeline, not a single magic brain: UI → safety → context engineering → response generation → trained working model.  ￼
	•	“Meaning” inside these systems is largely geometric and relational: tokens become vectors; similarity becomes proximity; context pulls interpretation.  ￼
	•	AI “memory” is closer to distributed association than a storage cabinet of facts, which helps explain both generalization and hallucination.  ￼
	•	Attention and syntax are tools for deciding what matters and how parts of a sentence constrain each other, not just word counting.  ￼
	•	Safety layers shape what AI can say; that’s governance, not consciousness.  ￼

If you want, I can also rewrite this as a clean “lecture transcript” you could literally read aloud while studying—same content, just tighter flow and fewer headings.

