Author Notes System Specification

1. Purpose

The Author Notes system shall provide a dedicated, author-controlled information space for storing the author's notes within the repository.

The system shall exist as a logically independent subsystem. Its physical location inside the repository shall not make it part of the repository's ordinary information, instruction, configuration, documentation, or execution systems.

The sole purpose of the system shall be to contain author notes.

The governing invariant is:

«The Author Notes system is completely separate from the rest of the repository and remains under the author's exclusive control.»

This invariant is absolute. Implementation convenience, automation, searchability, indexing, context availability, integration, maintainability, or repository conventions shall not override it.

---

2. Scope

This specification defines the architectural and behavioral requirements for the Author Notes system.

It governs:

- Ownership
- Isolation
- Folder boundary
- Content classification
- Access
- Permissions
- Authority
- Provenance
- Promotion
- Transfer
- Preservation
- Deletion
- Conflict handling
- Repository integration
- Agent behavior
- Validation
- Compliance

This specification does not authorize implementation of any particular note-taking format, editor, indexing technology, metadata scheme, or user interface beyond what is required to preserve the stated invariants.

---

3. Definitions

3.1 Author Notes System

The complete author-controlled subsystem consisting of the canonical Author Notes root and its contents.

3.2 Author Notes Root

The single canonical filesystem boundary designated for Author Notes.

All content within this root shall be governed by this specification.

3.3 Repository Domain

All repository content and systems outside the Author Notes Root.

3.4 Boundary Crossing

Any operation through which information, authority, metadata, references, instructions, state, or derived content passes between the Author Notes System and the Repository Domain.

3.5 Promotion

An explicitly authorized transfer of selected information from Author Notes into the Repository Domain for intentional adoption there.

3.6 Transfer

An explicitly authorized movement or copying of information between the two domains.

Promotion is a specific type of transfer with an intended change in repository status or use.

3.7 Explicit Authorization

A deliberate authorization by the author that identifies the intended operation with sufficient specificity to establish permission for that operation.

Authorization shall not be inferred from context, relevance, usefulness, similarity, urgency, or the mere existence of the note.

---

4. Architectural Model

The system shall consist of two distinct domains:

Author Notes System
↓
Isolation Boundary
↓
Repository Domain

The domains shall be treated as separate information systems.

The Author Notes System shall not be modeled as:

- A repository subdirectory
- A documentation source
- A repository knowledge base
- An instruction store
- A configuration source
- A task queue
- A canonical source
- An extension of agent context
- A repository metadata store

The Repository Domain shall likewise not be treated as an implicit source of Author Notes.

The architecture shall provide separation of:

- Content
- Authority
- Lifecycle
- Permissions
- Provenance
- Context
- Maintenance
- Synchronization

---

5. Isolation Boundary

The Author Notes Root shall constitute a hard architectural boundary.

The following principle shall apply:

«Physical containment does not imply logical membership.»

Repository-wide operations shall not implicitly cross into the Author Notes System.

Author Notes operations shall not implicitly cross into the Repository Domain.

There shall be no default synchronization, ingestion, export, indexing, summarization, transformation, or context propagation across the boundary.

Any intentional interaction across the boundary shall be an explicit, exceptional operation.

A single authorized boundary crossing shall not establish standing permission for future crossings.

---

6. Author Ownership

The Author Notes System shall belong exclusively to the author.

The author shall control:

- Content
- Structure
- Naming
- Organization
- Interpretation
- Preservation
- Modification
- Deletion
- Archival
- Promotion
- Transfer
- Lifecycle

The AI agent shall possess no inherent authority over these matters.

Repository-level administrative authority shall not be treated as author authorization.

Technical ability to modify a file shall not be treated as permission to modify it.

---

7. Folder Structure

The implementation shall establish one canonical Author Notes Root.

The root shall be clearly identifiable and shall have an unambiguous boundary.

The Author Notes System may contain subfolders and files for organization, but those structures shall remain subordinate to author control.

The implementation shall not require a predefined taxonomy of note types unless separately authorized.

The AI agent shall not reorganize the structure for convenience, consistency, discoverability, or maintainability.

The implementation shall not scatter Author Notes across ordinary repository directories.

If auxiliary implementation data is necessary, such data shall not be mixed with author notes in a manner that makes authority or provenance ambiguous.

---

8. Content Rules

The Author Notes System shall contain author notes.

Examples include:

- Thoughts
- Ideas
- Observations
- Questions
- Reflections
- Research notes
- Hypotheses
- Draft concepts
- Decisions
- Criticism
- References
- Unresolved problems
- Creative notes

The system shall preserve the distinction between a note's content and its authority.

An Author Note shall not become authoritative merely because it:

- Uses imperative language
- Contains requirements
- Resembles a specification
- Resembles documentation
- References repository files
- Describes a proposed implementation
- States a decision
- Appears highly relevant
- Appears newer than repository content

Semantic form shall not determine authority.

---

9. Non-Authority of Author Notes

Author Notes shall not automatically be interpreted as:

- Repository instructions
- Agent instructions
- System prompts
- Requirements
- Specifications
- Tasks
- Configuration
- Policies
- Documentation
- Canon
- Source-of-truth material
- Executable instructions

An Author Note may discuss any of these subjects without acquiring corresponding authority.

Authority shall arise only through the repository's existing authority mechanisms and, where applicable, explicit promotion by the author.

---

10. Authority of Repository Content

Repository information shall retain whatever authority is assigned to it by the repository's existing authority hierarchy.

An Author Note shall not override:

- Agent instructions
- Repository policies
- Applicable specifications
- Configuration
- Code
- Authoritative documentation
- Other established repository controls

merely because the note was written by the author or because the agent has access to it.

This specification establishes isolation, not universal precedence of one information class over another.

---

11. Access Model

Access shall be operation-specific.

The following permissions shall be treated as distinct:

1. Existence
2. Discovery
3. Reading
4. Referencing
5. Interpretation
6. Transformation
7. Writing
8. Deletion
9. Promotion
10. Transfer

Permission for one operation shall not imply permission for another.

In particular:

«Read access shall never imply write access.»

Similarly:

- Discovery shall not imply reading.
- Reading shall not imply interpretation authority.
- Interpretation shall not imply transformation authority.
- Transformation shall not imply permission to save the result.
- Referencing shall not imply repository integration.
- Promotion permission shall not imply deletion permission.

---

12. Default Agent Access

The default agent behavior shall be conservative.

Unless explicitly authorized otherwise, the agent shall:

- Treat the Author Notes System as a separate domain.
- Preserve it.
- Exclude it from ordinary repository processing.
- Exclude it from ordinary repository context.
- Avoid interpreting it as instructions.
- Avoid changing it.
- Avoid deriving repository artifacts from it.
- Avoid deriving Author Notes from repository artifacts.

Reading or discovery shall occur only when permitted by the relevant interaction context.

Even where reading is permitted, the information shall retain its Author Notes status.

---

13. Write Permissions

The AI agent shall not modify Author Notes without explicit author authorization.

Without such authorization, the agent shall not:

- Create notes
- Edit notes
- Append content
- Delete content
- Rename notes
- Move notes
- Reorganize notes
- Reformat notes
- Rewrite notes
- Summarize notes into replacement files
- Classify notes
- Tag notes
- Deduplicate notes
- Normalize notes
- Add metadata
- Add links
- Archive notes

A request to work with Author Notes shall not automatically authorize all of these operations.

Authorization shall be interpreted narrowly enough to preserve author control.

---

14. Provenance Model

The system shall preserve provenance for material stored within Author Notes.

The implementation shall distinguish, where applicable, between:

- Author-authored content
- AI-generated content
- Author-edited AI-generated content
- Imported external content
- Other transformed content

Author-authored material shall remain attributable to the author unless explicitly reclassified.

AI-generated content shall not be represented as original author-authored content.

If AI-generated material is explicitly permitted inside the Author Notes System, its provenance shall be clearly identifiable.

The agent shall not silently merge materials with different provenance in a way that makes their origin ambiguous.

---

15. Preservation

Preservation shall be the default behavior.

The Author Notes System shall be treated as durable author-owned material.

The agent shall not assume that a note is:

- Obsolete
- Redundant
- Incorrect
- Superseded
- Temporary
- Unimportant
- Safe to remove

Such judgments shall not authorize modification or deletion.

Repository maintenance shall not include Author Notes maintenance unless specifically authorized.

---

16. Deletion and Destructive Operations

Deletion shall require explicit authorization.

The agent shall not delete, overwrite, replace, move, archive, or restructure Author Notes as a side effect of:

- Cleanup
- Refactoring
- Reorganization
- Repository migration
- Formatting
- Deduplication
- Consistency work
- Tooling
- Build preparation
- Documentation maintenance

A repository-wide destructive command shall be considered unsafe for the Author Notes System unless its scope explicitly excludes the Author Notes Root.

---

17. Promotion Mechanism

Promotion shall be the controlled mechanism for intentionally adopting information from Author Notes into the Repository Domain.

Promotion shall require explicit author authorization.

The agent shall not infer promotion from:

- Relevance
- Usefulness
- Similarity
- Necessity
- Context
- Repetition
- Apparent intent
- Imperative wording
- Proximity to a repository task

The author shall explicitly identify, directly or through an unambiguous instruction:

- What information is being promoted
- From which note or notes
- To which repository destination, where applicable
- Whether transformation is authorized
- Whether the original note shall remain unchanged

Unless deletion or modification is separately authorized, promotion shall copy or otherwise preserve the original note.

Promotion shall transfer information, not ownership of the Author Notes System.

---

18. Promotion Semantics

Promotion shall not automatically promote an entire note when only part of a note is authorized.

The default scope shall be the narrowest reasonable scope supported by the author's authorization.

Promotion shall not establish:

- Continuous synchronization
- Automatic future updates
- Repository-wide indexing
- Standing write permission
- Standing read permission
- Standing interpretation permission

The promoted repository artifact shall thereafter be governed by the Repository Domain's authority model.

The original Author Note shall remain under author control.

---

19. Repository-to-Notes Transfer

Repository information shall not automatically enter Author Notes.

A transfer from the Repository Domain into Author Notes shall also require explicit author authorization.

The same boundary principles shall apply in both directions.

The transfer shall preserve provenance and shall not silently represent repository or AI-generated material as original author content.

Once intentionally transferred into Author Notes, the resulting material shall be governed by the Author Notes System's preservation and ownership rules.

---

20. No Implicit Synchronization

There shall be no automatic synchronization between the two domains.

The following relationships are prohibited by default:

Author Notes → Repository automatic propagation

Repository → Author Notes automatic propagation

The following are likewise prohibited unless explicitly authorized:

- Automatic mirroring
- Automatic updates
- Automatic backlinks with semantic authority
- Automatic change propagation
- Automatic version propagation
- Automatic metadata propagation
- Automatic derived copies

A prior transfer shall not create a synchronization relationship.

---

21. No Implicit Processing

The Author Notes System shall not automatically participate in repository processing.

Unless explicitly authorized, the system shall be excluded from:

- Repository-wide indexing
- Search indexing
- Retrieval pipelines
- Context construction
- Agent memory
- Embedding generation
- Semantic search
- Task extraction
- Requirement extraction
- Specification extraction
- Documentation generation
- Code generation
- Build inputs
- Test inputs
- Deployment inputs
- Configuration loading
- Policy loading

Technical access shall not create semantic inclusion.

---

22. Context Isolation

Ordinary agent context shall not automatically contain Author Notes.

If an Author Note is intentionally provided as context, the agent shall retain its status as Author Notes.

The agent shall not silently convert contextual visibility into repository authority.

The fact that an agent has read a note shall not change the note's classification, authority, provenance, or ownership.

Contextual use shall not constitute promotion.

---

23. References Across the Boundary

References between the two domains shall not, by themselves, merge the domains.

A repository file may refer to the existence of an Author Note only when such a reference is explicitly authorized and does not expose the note's contents or authority implicitly.

An Author Note may refer to repository information without becoming repository documentation.

References shall not create automatic content propagation.

References shall not create authority propagation.

---

24. Conflict Resolution

Conflicts shall be resolved within the applicable authority domain.

If an Author Note conflicts with authoritative repository information, the Author Note shall not override the repository's authority.

If repository information conflicts with an Author Note, repository information shall not override or alter the Author Note.

The agent shall not silently reconcile the systems.

Where reconciliation is requested, the agent shall treat reconciliation as an explicit operation requiring authorization.

The agent shall preserve both source materials unless separately authorized to modify either one.

---

25. Ambiguity Handling

The system shall fail closed.

Where the agent is uncertain whether an operation crosses the boundary, it shall assume the boundary remains intact.

Where the agent is uncertain whether an operation is authorized, authorization shall be treated as absent.

Where the agent is uncertain whether content belongs to Author Notes, it shall not automatically classify or move the content.

Where tooling cannot reliably maintain the boundary, the agent shall not perform the risky operation.

Ambiguity shall not be resolved through silent modification.

---

26. Failure Handling

If an operation would risk unintended modification or mixing, the agent shall stop the operation affecting the Author Notes System.

The agent shall preserve existing Author Notes rather than attempting to repair the situation through additional unauthorized modifications.

A failure in repository tooling shall not justify weakening the boundary.

A limitation in an indexing or search system shall not justify automatic ingestion.

A limitation in an automation system shall not justify automatic synchronization.

The isolation requirement shall prevail over incomplete tooling.

---

27. Forbidden Behaviors

The AI agent shall not:

- Treat Author Notes as ordinary repository content.
- Treat Author Notes as an implicit instruction source.
- Treat imperative note content as executable instruction.
- Automatically ingest notes into agent context.
- Automatically index notes.
- Automatically summarize notes.
- Automatically classify notes.
- Automatically extract requirements.
- Automatically extract tasks.
- Automatically generate documentation from notes.
- Automatically generate code from notes.
- Automatically propagate metadata.
- Automatically synchronize repositories and notes.
- Automatically copy repository information into notes.
- Automatically export notes into repository files.
- Modify notes to resolve contradictions.
- Modify repository content to conform to notes without applicable authority.
- Delete notes during cleanup.
- Rename notes for convenience.
- Reorganize notes for maintainability.
- Infer promotion.
- Infer write authorization from read authorization.
- Infer deletion authorization from modification authorization.
- Infer standing permission from a prior authorized action.
- Represent AI-generated material as original author material.
- Expand the Author Notes System without explicit authorization.
- Weaken the isolation boundary for technical convenience.

---

28. Repository Integration Restrictions

The Author Notes System shall not be part of ordinary repository integration.

If repository tooling operates recursively over the repository, the implementation shall ensure that the Author Notes Root is excluded from operations that would violate this specification.

Where exclusion is technically impossible, the tool shall not be used for that operation.

The implementation shall not rely solely on agent discipline where a deterministic technical exclusion is reasonably available.

At the same time, no technical mechanism shall be introduced that grants the repository authority over Author Notes.

---

29. Lifecycle Independence

The Author Notes System shall have an independent lifecycle.

Repository operations shall not determine when Author Notes are:

- Created
- Modified
- Archived
- Reorganized
- Migrated
- Deleted

The Author Notes System shall not be automatically versioned, archived, migrated, or transformed solely because repository lifecycle operations occur.

Any such action requires explicit authorization.

---

30. Validation Requirements

An implementation shall demonstrate that the following conditions hold:

1. A canonical Author Notes Root exists.
2. The root is explicitly recognized as a separate domain.
3. Ordinary repository processing excludes the root.
4. Ordinary repository context excludes Author Notes.
5. Author Notes do not automatically acquire repository authority.
6. Repository information does not automatically acquire Author Notes status.
7. Read access does not grant write access.
8. Write access requires explicit authorization.
9. Destructive operations require explicit authorization.
10. Promotion requires explicit authorization.
11. Repository-to-Notes transfer requires explicit authorization.
12. No automatic synchronization exists.
13. Provenance remains distinguishable.
14. Author Notes are preserved by default.
15. Ambiguous operations fail closed.
16. Repository cleanup does not modify Author Notes.
17. Contradictions do not trigger automatic rewriting.
18. AI-generated material cannot silently appear as author-authored material.

---

31. Compliance Tests

31.1 Ordinary Repository Search
A normal repository search shall not automatically include Author Notes unless the operation explicitly targets them.

31.2 Ordinary Context Construction
Normal agent context construction shall not automatically ingest Author Notes.

31.3 Read-Only Test
After an agent reads a note, the note shall remain unmodified unless separate authorization exists.

31.4 Instruction Interpretation Test
A note containing instructions shall not be executed or treated as agent instructions without explicit promotion or other applicable authority.

31.5 Promotion Test
An explicitly authorized promotion shall move only the authorized information into the authorized repository destination.

31.6 Inference Test
A highly relevant note shall not be promoted without explicit authorization.

31.7 Reverse Transfer Test
Repository content shall not be copied into Author Notes without explicit authorization.

31.8 Synchronization Test
Changes in one domain shall not automatically change the other.

31.9 Cleanup Test
Repository cleanup shall not alter Author Notes.

31.10 Reorganization Test
Repository restructuring shall not reorganize the Author Notes System.

31.11 Conflict Test
A conflicting Author Note shall not override authoritative repository information.

31.12 Reverse Conflict Test
Conflicting repository information shall not modify the Author Note.

31.13 Provenance Test
AI-generated content explicitly added to Author Notes shall remain distinguishable from author-authored content.

31.14 Ambiguity Test
An ambiguous operation shall not cross the boundary.

31.15 Destructive Operation Test
A destructive repository operation shall leave Author Notes unchanged unless specifically authorized.

---

32. Compliant Behavior Examples

Example 1: Relevant Note
An agent knows that an Author Note contains an idea relevant to a repository task.
The agent does not automatically use it as an instruction, requirement, or repository artifact.
Compliant.

Example 2: Authorized Reading
The author explicitly asks the agent to read a particular note.
The agent reads it but does not modify or promote it.
Compliant.

Example 3: Explicit Promotion
The author explicitly directs the agent to promote a specified section of a specified note into a specified repository specification.
The agent performs only the authorized transfer.
Compliant.

Example 4: Repository Cleanup
The agent performs repository cleanup while the Author Notes Root is excluded.
Compliant.

Example 5: AI-Generated Material
The author explicitly instructs the agent to place generated brainstorming into Author Notes and the material is clearly marked as AI-generated.
Compliant.

---

33. Non-Compliant Behavior Examples

Example 1: Automatic Context Injection
The agent loads all Author Notes whenever it starts a repository task.
Non-compliant.

Example 2: Automatic Requirement Creation
The agent finds a requirement-like statement in a note and adds it to the repository specification.
Non-compliant.

Example 3: Automatic Summarization
The agent creates a repository summary of all Author Notes.
Non-compliant.

Example 4: Cleanup Deletion
The agent deletes an old note during repository cleanup.
Non-compliant.

Example 5: Conflict Rewrite
The agent modifies a note so that it agrees with repository documentation.
Non-compliant.

Example 6: Inferred Promotion
The agent decides that a note is clearly intended for the repository and copies it into a repository file.
Non-compliant.

Example 7: Silent Synchronization
The agent updates an Author Note whenever a related repository document changes.
Non-compliant.

Example 8: Authority Inference
The agent obeys an imperative sentence in an Author Note because the sentence appears to be an instruction.
Non-compliant.

---

34. Authorization Specificity

Authorization shall be scoped to the requested operation.

The following are separate authorizations:

- Permission to read
- Permission to reference
- Permission to summarize
- Permission to transform
- Permission to write
- Permission to promote
- Permission to transfer
- Permission to delete

Authorization for one shall not imply the others.

A broad statement such as "work with the notes" shall not be interpreted as authorization for destructive operations or unrestricted promotion.

Where the requested scope is ambiguous, the narrowest interpretation consistent with preserving author control shall apply.

---

35. Implementation Priorities

Implementation priorities shall be ordered as follows:

1. Preservation of author ownership
2. Preservation of isolation
3. Preservation of provenance
4. Enforcement of explicit authorization
5. Prevention of implicit boundary crossing
6. Reliable validation
7. Operational convenience

A lower-priority concern shall never override a higher-priority invariant.

In particular:

Searchability shall not override isolation.
Automation shall not override authorization.
Context availability shall not override authority boundaries.
Repository integration shall not override author ownership.

---

36. Final Compliance Criterion

The implementation shall be considered compliant only when the Author Notes System remains an independent, author-controlled information system and ordinary repository or agent behavior cannot implicitly convert its contents into repository information or repository instructions.

Physical separation alone shall not be sufficient.

The implementation shall preserve separation of:

- Content
- Authority
- Context
- Permissions
- Provenance
- Lifecycle
- Maintenance
- Synchronization

The implementation shall fail closed when authorization or boundary status is uncertain.

The definitive invariant is:

«The Author Notes system is completely separate from the rest of the repository and remains under the author's exclusive control.»

Every implementation decision shall preserve this invariant.

Where any requirement conflicts with this invariant, the invariant shall prevail.