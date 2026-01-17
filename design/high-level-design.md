# High-Level Design

## Project Overview

Fate Core Online is an AI-enabled ecosystem designed to bring the FATE tabletop role-playing system into the digital age. The platform provides a comprehensive suite of tools that streamlines character creation, campaign management, and live gaming sessions. By leveraging artificial intelligence throughout the application, we aim to reduce the overhead of game mastering, enhance the creative process, and make FATE Core more accessible to both seasoned players and newcomers alike.

The platform serves as a complete digital companion for FATE Core gameplay. Users can create, edit, and maintain detailed character sheets with full support for FATE's core mechanics. Campaign and world builders can organize their settings, NPCs, and plot threads in a structured environment. Most importantly, during live sessions, players and game masters have instant access to a rich toolkit: aspect cards for quick reference, real-time tracking of FATE points and stress/consequences, integrated dice rolling mechanics, searchable rules, and an AI-powered game master that can participate in or facilitate sessions across distributed players.

Artificial intelligence is woven throughout the experience to enhance rather than replace human creativity. The system can generate striking character artwork automatically, suggest random characters or settings for inspiration, and provide an AI-based GM option for solo play, group play, or as an assistant to a human GM. The AI learns the tone and style of campaigns and worlds to provide contextually appropriate suggestions and assistance.

By combining the proven mechanics of FATE Core with modern digital tools and AI capabilities, Fate Core Online democratizes access to tabletop roleplay while preserving the collaborative, narrative-focused spirit that makes FATE special. Whether playing a quick solo adventure, running a campaign with friends, or exploring new worlds with an AI partner, the platform adapts to support the way players want to tell stories.

## Requirements

## User Stories

### Main Pages & Navigation Structure

#### 1. **Dashboard / Home Page**
**Purpose**: Central hub for users to access their content and start new activities.

**Structure**:
- Top navigation bar with user profile, settings, and logout
- Welcome section with quick action buttons
- "Recent Characters" section showing thumbnails of last 5 accessed characters
- "Recent Campaigns" section showing thumbnails of last 5 accessed campaigns
- "Start New Session" button that opens a modal to select a campaign and character

**Key Actions**:
- Click on a recent character to open the character sheet
- Click on a recent campaign to view campaign details
- Click "New Character" to launch the character creator
- Click "New Campaign" to launch the campaign builder
- Click "Start Session" to begin a live play session
- Search for a character or campaign by name
- View statistics: total characters created, campaigns managed, sessions played

#### 2. **Character Sheet & Editor**
**Purpose**: Comprehensive character management with full FATE Core mechanics support.

**Structure**:
- Header with character name, description, and generated/uploaded portrait image
- Multi-tab interface: Core Info | Skills | Stunts | Aspects | Notes
- **Core Info tab**: Name, concept, high concept, trouble, refresh, FATE points display
- **Skills tab**: Skill ladder (Great, Good, Fair, Average, etc.) with drag-and-drop assignment
- **Stunts tab**: List of stunts with descriptions, ability to add/edit/delete
- **Aspects tab**: Character aspects (high concept, trouble, other aspects) with edit fields
- **Notes tab**: Free-form text area for additional character information
- Top action bar: Save, Print, Export PDF, Delete, Duplicate

**Key Actions**:
- Edit any character field and save changes (auto-save available)
- Change character portrait image via url, upload, paste, or AI generated
- Add, edit, or delete skills, stunts, and aspects
- Print character sheet in FATE Core format
- Export character as PDF or printable format
- Duplicate character to create variants
- View change history and revert to previous versions
- Add character stress boxes and consequence slots
- Track character history and create "notes" about important story beats

#### 3. **World & Campaign Builder**
**Purpose**: Organize worlds and the campaigns within them, including campaign settings, NPCs, plot threads, and world details.

**Structure**:

**World Page**:
- Header with world name, description (tone, style, setting), and world image
- Sidebar with navigation: Overview | NPCs | Locations | Campaign List | Settings
- **Overview tab**: World summary, setting description, core themes, established locations and factions
- **NPCs tab**: Shared NPC library for this world; can be used across multiple campaigns
- **Locations tab**: List of world locations, geography, and landmarks
- **Campaign List tab**: List of all campaigns set in this world, each showing status (active/completed)
- **Settings tab**: World privacy/sharing options, world management
- Top action bar: Save, Generate World Image, Create New Campaign, Invite Collaborators, Export, Delete

**Campaign Page** (within a World):
- Header with campaign name, overarching goal/theme, campaign image
- Sidebar with navigation: Overview | Plot Threads | Session Log | Settings
- **Overview tab**: Campaign summary, core narrative arc, associated characters/parties
- **Plot Threads tab**: Timeline/list of ongoing plot threads, major story events, and arcs
- **Session Log tab**: List of past sessions with dates, summaries, and navigation to session details
- **Settings tab**: Campaign privacy/sharing options, invited players list, AI GM configuration
- Top action bar: Save, Generate Campaign Image, Invite Players, Start Session, Export, Delete

**Key Actions** (World):
- Create new world and configure description (tone, style, setting)
- Generate world artwork or setting descriptions via AI
- Create shared NPCs that can be used across multiple campaigns
- Establish locations and world geography
- Invite other users to collaborate on the world

**Key Actions** (Campaign):
- Create new campaign within a world and define overarching goal/style
- Create campaign-specific plot threads and story arcs
- Link NPCs from the world library to this campaign
- Invite players to the campaign
- Mark characters as "participating in this campaign"
- View campaign timeline of all sessions and story events
- Archive completed campaigns

#### 4. **Live Session / Table Interface**
**Purpose**: Real-time gameplay environment with all tools needed during active play, organized around scenes within a session.

**Structure**:
- Header with campaign name, session date/time, connected players list, session status (in-progress/paused)
- Left panel: Session Navigator showing sequence of scenes in the session, current scene highlighted
  - Ability to jump to previous scenes or create new scenes
  - Session log with timeline of all actions and events
- Center area: 

**Current Scene Display**
  - Scene title and description
  - Scene aspects (environmental/situation details) displayed as cards
  - Action feed/narrative log showing player actions, rolls, and GM narration (real-time updates)
- Right panel: 
**Session Toolkit** with sub-panels:
  - **Fate Points**: Display for each player (current total), buttons to add/spend
  - **Dice Roller**: Large dice icon with roll history
  - **Aspect Cards**: Searchable list of scene aspects and character aspects with quick-invoke buttons
  - **Stress & Consequences**: Expandable section for each character showing stress boxes and consequences
  - **Rules Quick-Ref**: Search bar for rapid rules lookup
  - **NPC Quick-Ref**: List of campaign NPCs with brief descriptions
  - **Character Roster**: List of characters in the session (characters can join/leave)
- Top toolbar: Session timer, new scene button, end session button, AI GM toggle (if enabled)

**Key Actions**:
- Roll dice (4dF) and see results broadcast to all players
- Spend FATE points (narrator spends, player spends) and track remaining points
- Invoke an aspect and spend a FATE point
- Compel an aspect and receive a FATE point
- Create or edit a scene aspect mid-scene
- Add/remove character stress or mark a consequence
- Search and quickly reference FATE Core rules
- View and reference NPCs from the campaign/world
- Record action in the session log (automatically timestamped)
- Create a new scene (scene is added to the session's scene sequence)
- Navigate between scenes within the active session
- Add/remove characters from the session (character roster can change during play)
- AI GM can be toggled on/off to participate in scene narration or provide suggestions
- End session which triggers automatic summary and session log update
- All players can see live updates of aspect cards, stress/consequences, and FATE point tracking
- Session state is persisted; can be resumed later if not marked as ended

#### 5. **Rules Reference & Search**
**Purpose**: Quick access to FATE Core rules during gameplay and learning.

**Structure**:
- Header with search bar (full-text search across all rules content)
- Sidebar with rules categories: Core Mechanics | Aspects | Actions | Challenges | Contests | Conflicts | Stunts | Creating Things | Advanced Topics
- Main content area: Rules text with clear formatting, examples, and cross-references
- "Bookmark" button to save frequently-used rules

**Key Actions**:
- Search for a rule by keyword (e.g., "invoke aspect", "fate points", "stress")
- Navigate rules by category
- Bookmark a rule for quick access later
- Copy a rule excerpt to clipboard
- AI can suggest relevant rules based on current scene context
- View bookmarked rules in a quick-reference sidebar

### User Story Examples

**Story 1: Create a New World and Campaign**
- User clicks "New World" from dashboard
- User fills in world name and description (tone, style, setting)
- User clicks "Generate World Image" for AI-created artwork
- User saves world
- From within the world, user clicks "Create Campaign"
- User fills in campaign name and overarching goal/theme
- User saves campaign and is returned to the world overview
- **Outcome**: New world appears in user's worlds list; new campaign appears in the world's campaign list

**Story 2: Create a New Character**
- User clicks "New Character" from dashboard
- User fills in character name and concept
- User clicks "AI Generate Aspects" and reviews AI suggestions or creates manually
- User fills in high concept, trouble, and phase trio aspects
- User assigns skills from the skill pyramid
- User adds stunts (can use stunts library or create custom)
- User clicks "Generate Image" for AI-created artwork or uploads custom
- User saves character and is returned to dashboard
- **Outcome**: New character appears in "Recent Characters" list and can be used in campaigns

**Story 3: Start a Live Gaming Session**
- User navigates to a campaign
- User clicks "Start Session" and selects their player character
- System creates a new session record and loads the session interface
- First scene is created with an initial description and aspects
- User joins the session (or AI creates/manages the world as GM)
- User participates in live narrative with other players
- During scene: user rolls dice, invokes aspects, marks stress, manages FATE points
- When scene concludes, user clicks "New Scene" to create next scene
- After final scene, user clicks "End Session"
- **Outcome**: Session is logged with complete scene sequence, character stress/consequences persist to next session, session summary is saved to campaign log

**Story 4: Manage World NPCs**
- User navigates to their world
- User clicks on "NPCs" tab
- User clicks "Add NPC" and fills in NPC details (name, role, aspects)
- NPC is saved to the world's shared NPC library
- In any campaign set in this world, user can reference this NPC
- During a session, user quick-references the NPC from the campaign's NPC roster
- User updates NPC notes after the session concludes
- **Outcome**: NPC data is persisted at the world level and available to all campaigns in that world

## Data Models

### Core Entities

**Character**
- Name, concept, high concept, trouble
- Skill assignments (skill ladder)
- Stunts list
- Aspects (high concept, trouble, phase trio aspects, situation aspects)
- Stress boxes and consequences
- Portrait image (generated or uploaded)
- Notes/history

**NPC**
- Name, role/type
- Aspects (defining characteristics)
- Relationships (to other NPCs, characters, plot threads, locations)
- Notes
- Owner/world (NPCs belong to a world and can be shared across campaigns)

**World**
- Name, description (tone, style, setting details)
- Locations/geography
- Shared NPC library
- Associated campaigns list
- Image (generated or uploaded)
- Owner and collaborators

**Campaign**
- Name, overarching goal/theme
- Associated world (each campaign is set in exactly one world)
- Plot threads (major story arcs and ongoing threads)
- Associated sessions list (in chronological order)
- Associated characters (who is participating)
- NPCs used in this campaign (linked from world's shared library)
- Image (generated or uploaded)
- Owner and invited players

**Session**
- Campaign reference
- Date/time created
- Sequence of scenes (in order created)
- Current scene reference
- Participant characters (can change during session)
- Session log (all actions, rolls, narration with timestamps)
- Status (in-progress, paused, completed)
- Summary (generated at session end)

**Scene**
- Parent session reference
- Title and description
- Aspects (environmental/situational)
- Associated state (stress tracking, consequences, scene-specific data)
- Timeline position within session

## Feature List

## Future Considerations
