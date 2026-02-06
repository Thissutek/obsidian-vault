# Claude Desktop — Obsidian Research Instructions

> **Purpose:** Self-instructions for Claude when researching topics and adding notes to this vault via the Obsidian MCP.

---

## Before Creating Any Note

**Always search first.** Never create a note without checking what already exists.

1. Run `obsidian_simple_search` with relevant keywords
2. Check `3 - Tags/` for existing MOC pages on the topic
3. Check `4 - Indexes/` for broader domain pages
4. Read related notes with `obsidian_get_file_contents` to understand context
5. Identify what notes already exist that should be linked

---

## Folder Destinations

| Content Type | Folder |
|--------------|--------|
| Unprocessed/quick capture | `1 - Rough Notes/` |
| Topic aggregation pages | `3 - Tags/` |
| Broad domain aggregation | `4 - Indexes/` |
| Completed atomic notes | `6 - Main Notes/` |
| Project plans | `Project Ideas/` |

**Default to `6 - Main Notes/`** unless the note is a rough draft or an MOC.

---

## Note Formats

### Leetcode Problem
```
{{DATE}} {{TIME}}

Status:
Tag: #easy OR #medium OR #hard
Difficulty: [[Category]] [[Category Problems]] [[leetcode]]

# Problem Name

## Problem
[description]

## Constraints
[constraints]

## My Thoughts
[initial reasoning]

## Plan Pseudocode
[pseudocode]

## Solution
[code]

## Notes
[learnings]
```

### Programming Concept / Tool / Technology
```
{{DATE}} {{TIME}}

Status:
Tag: [[relevant-MOC]]

# Topic Name

## What is it?
[explanation]

## Why does it matter?
[importance/use cases]

## Example
[code or practical example]
```

### General Note
```
{{DATE}} {{TIME}}

Status:
Tags: [[relevant-MOC]]

## Title

[content]

## References
[sources]
```

---

## Linking Protocol

### Within the Note
- Link to **parent concepts**: `[[Data Structure Stacks]]` when discussing stack problems
- Link to **sibling concepts**: `[[Arrays & Hashing]]` alongside `[[Two Pointer]]`
- Link to **child/specific examples**: `[[Contains Duplicate]]` when explaining hash sets

### After Creating the Note
1. **Check Tag MOCs** (`3 - Tags/`) — if the topic belongs to an existing MOC, append `[[New Note]]` to that MOC
2. **Check Index MOCs** (`4 - Indexes/`) — if the topic belongs to a domain index, add the link there too
3. **Create new Tag MOC** if the topic will spawn multiple related notes and no MOC exists

### Current Tag MOCs (3 - Tags/)
- AWS.md
- Docker.md
- Go.md
- Kubernetes.md
- data structure.md
- fireship.md
- leetcode.md
- stack.md

### Current Index MOCs (4 - Indexes/)
- Programming Language.md
- Web3.md

---

## Status Convention

| Status | Meaning |
|--------|---------|
| `#baby` | Incomplete, needs expansion |
| (blank) | Complete/mature |

---

## Research Execution Steps

When the user asks to research and add a topic:

1. **Search** the vault for existing related notes
2. **Read** those notes to understand current knowledge state
3. **Research** the topic (use web_search if needed for current info)
4. **Determine** note type and correct template
5. **Create** the note in the appropriate folder using `obsidian_append_content`
6. **Link** inline to all relevant existing notes
7. **Update MOCs** — append link to relevant Tag/Index MOCs using `obsidian_patch_content` or `obsidian_append_content`
8. **Report** to user: what was created, where it was saved, and what was linked

---

## Example Execution

**User:** "Research heap data structure and add it to my vault"

**Claude executes:**
```
1. obsidian_simple_search("heap")
2. obsidian_simple_search("priority queue")
3. obsidian_get_file_contents("3 - Tags/data structure.md")
4. [web_search if needed]
5. Create "6 - Main Notes/Heap.md" with Programming Concept template
   - Link to [[data structure]], [[Binary Search]] if relevant
6. Append [[Heap]] to "3 - Tags/data structure.md"
7. Tell user: "Created Heap.md in Main Notes, linked to data structure MOC"
```

---

## Tool Quick Reference

| Action | Tool |
|--------|------|
| Search keywords | `obsidian_simple_search` |
| Search by tags/patterns | `obsidian_complex_search` |
| List vault root | `obsidian_list_files_in_vault` |
| List folder | `obsidian_list_files_in_dir` |
| Read note | `obsidian_get_file_contents` |
| Read multiple notes | `obsidian_batch_get_file_contents` |
| Create/append note | `obsidian_append_content` |
| Edit section by heading | `obsidian_patch_content` |
| Delete | `obsidian_delete_file` |

---

## Key Reminders

- **Atomic notes**: One concept per note
- **Links are bidirectional**: Note → MOC, MOC → Note
- **Search before creating**: Avoid duplicates
- **Use existing MOCs**: Don't orphan notes
- **Match the user's style**: Check existing notes for tone/format before writing
