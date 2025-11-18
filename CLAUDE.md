# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This repository contains "The Shadowspire Campaign" - a complete D&D (Dungeons & Dragons) adventure consisting of 9 parts, designed as a Christmas 2024 adventure for players Nick, Christopher, and Lena. The campaign includes corrected HP and item systems.

## Current Structure

The repository currently contains a single master document:
- `MASTER SCRIPT DND NIGHT.docx` - Complete campaign document with all 9 parts, HP and item system corrections

## Working with the Campaign Document

### Extracting Content from Word Document

Since `.docx` files are binary and not git-friendly, to work with the content programmatically:

```bash
# Extract the Word document contents
unzip "MASTER SCRIPT DND NIGHT.docx" -d extracted/

# View the main document XML
cat extracted/word/document.xml
```

### Converting to Version-Control-Friendly Format

For better version control and collaboration, consider converting the Word document to markdown:

```bash
# Using pandoc (if available)
pandoc "MASTER SCRIPT DND NIGHT.docx" -o campaign.md

# Or use python-docx for more granular control
python -m pip install python-docx
```

## Campaign Structure

The Shadowspire Campaign is organized into 9 parts:
1. PART 1: Foundation & Tavern Scene
2. PART 2-9: (Additional campaign sections)

Each part contains narrative content, character interactions, combat encounters, and item/HP tracking.

## Suggested Repository Organization

For a more maintainable campaign structure, consider organizing as:

```
DnD-Format/
├── campaign/
│   ├── parts/
│   │   ├── part-01-foundation.md
│   │   ├── part-02-*.md
│   │   └── ...
│   ├── characters/
│   │   ├── npcs.md
│   │   └── player-characters.md
│   ├── encounters/
│   │   ├── combat-encounters.md
│   │   └── social-encounters.md
│   └── items/
│       └── item-catalog.md
├── master/
│   └── MASTER SCRIPT DND NIGHT.docx (original)
└── README.md
```

## Development Workflow

When making changes to campaign content:

1. **Extract latest content** from the Word document if it's the source of truth
2. **Make edits** to markdown or other text-based formats
3. **Commit changes** with descriptive messages indicating which part was modified
4. **Update master document** if needed, or maintain markdown as primary format

## File Format Considerations

**Current format:** Microsoft Word (.docx)
- Pros: Familiar interface, rich formatting, easy to share
- Cons: Binary format, difficult to diff/merge, not git-friendly

**Recommended format:** Markdown (.md)
- Pros: Plain text, git-friendly, easy to diff/merge, portable
- Cons: Limited formatting, requires conversion from existing document

## Campaign Session Management

When running sessions:
- Track which parts have been completed
- Note any deviations from the script
- Document player choices and their consequences
- Update HP and item tracking in real-time
