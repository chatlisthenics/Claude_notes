# MacBook Air Data Science Setup & Organization Guide

## Phase 1: Core System Setup (Week 1)

### Essential Developer Tools
- [ ] **Xcode Command Line Tools**: `xcode-select --install`
- [ ] **Homebrew** (package manager): `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
- [ ] **Git**: `brew install git` + configure with your GitHub credentials
- [ ] **Oh My Zsh** (terminal enhancement): `sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

### Python Environment Management
- [ ] **Anaconda**: Download from anaconda.com (includes Jupyter Lab, conda package manager)
- [ ] **Python version manager**: `brew install pyenv` (for managing multiple Python versions)
- [ ] Create base environments:
  - `conda create -n ds python=3.11 pandas numpy matplotlib seaborn scikit-learn`
  - `conda create -n ml python=3.11 pytorch tensorflow transformers`
  - `conda create -n web python=3.11 flask fastapi streamlit`

### Hardware Interface Tools
- [ ] **Arduino IDE**: Download from arduino.cc
- [ ] **PlatformIO** (advanced Arduino development): Install as VS Code extension
- [ ] **Serial monitor tools**: `brew install minicom` or use Arduino IDE's built-in monitor

## Phase 2: Data Science & Analytics Stack (Week 1-2)

### Core Data Tools
- [ ] **Jupyter Lab**: Included with Anaconda
- [ ] **VS Code**: Download from code.visualstudio.com
  - Extensions: Python, Jupyter, GitHub Copilot, Remote SSH
- [ ] **R & RStudio**: `brew install r` then download RStudio
- [ ] **SQL Tools**: 
  - **PostgreSQL**: `brew install postgresql`
  - **MySQL**: `brew install mysql` 
  - **SQLite Browser**: `brew install --cask db-browser-for-sqlite`
  - **DBeaver** (universal database tool): `brew install --cask dbeaver-community`

### Visualization & Analysis
- [ ] **Tableau** (when ready): Download from tableau.com
- [ ] **Observable Plot** (web-based): Setup through npm later
- [ ] **Plotly Dash**: `pip install dash plotly`

## Phase 3: File Organization System

### Root Directory Structure
```
~/
├── Development/
│   ├── Projects/
│   │   ├── data-science/
│   │   ├── web-apps/
│   │   ├── arduino-iot/
│   │   └── personal/
│   ├── Learning/
│   │   ├── courses/
│   │   ├── tutorials/
│   │   └── experiments/
│   └── Tools/
│       ├── scripts/
│       └── templates/
├── Data/
│   ├── raw/
│   ├── processed/
│   ├── external/
│   └── backups/
├── Documents/
│   ├── Research/
│   ├── Notes/
│   └── References/
└── AI-Models/
    ├── local-llms/
    ├── fine-tuned/
    ├── datasets/
    └── model-configs/
```

### LLM Organization Best Practices
- [ ] **Model Storage**: `~/AI-Models/local-llms/` with subfolders by model family
- [ ] **Experiment Tracking**: Use MLflow or Weights & Biases
- [ ] **Version Control**: Git repos for each fine-tuning project
- [ ] **Documentation**: README.md in each model folder with performance notes

## Phase 4: Cloud & Sync Setup

### File Sync & Backup
- [ ] **Dropbox**: Install app, sync selective folders
- [ ] **Google Drive**: Install Google Drive for desktop
- [ ] **iCloud**: Configure for Documents & Desktop (built-in)
- [ ] **Time Machine**: Set up with external drive for full system backups
- [ ] **Cloud backup strategy**: 
  - Code → GitHub
  - Data → Dropbox/Google Drive
  - Models → External drive + cloud storage
  - System → Time Machine

### Account Organization
- [ ] **Password Manager**: 1Password or Bitwarden
- [ ] **Google Accounts**: Document which account is for what purpose
- [ ] **SSH Keys**: Generate and add to GitHub, servers, etc.

## Phase 5: Security & Privacy

### VPN Setup
- [ ] **Research options**: NordVPN, ExpressVPN, or Mullvad
- [ ] **Consider needs**: General privacy vs development work vs international access
- [ ] **Install & configure** chosen VPN client

### Security Tools
- [ ] **Malwarebytes** (optional, Macs are generally secure)
- [ ] **Little Snitch** (network monitoring)
- [ ] **Enable FileVault** (disk encryption) in System Preferences

## Phase 6: Productivity & Learning Tools

### Knowledge Management
- [ ] **Anki**: Download from ankiweb.net
- [ ] **Obsidian** or **Notion**: For note-taking and knowledge graphs
- [ ] **Papers** or **Zotero**: For research paper management

### Media & Creative
- [ ] **DaVinci Resolve**: Download from blackmagicdesign.com
- [ ] **Homebrew media tools**: `brew install ffmpeg imagemagick`

## Phase 7: RAG Database Setup

### RAG Infrastructure
- [ ] **Vector Database**: 
  - **Chroma**: `pip install chromadb`
  - **Pinecone**: Create account, install client
  - **Weaviate**: Local or cloud setup
- [ ] **Document Processing**: 
  - `pip install langchain unstructured pypdf2 python-docx`
- [ ] **Embedding Models**: 
  - **Sentence Transformers**: `pip install sentence-transformers`
  - **OpenAI Embeddings**: Set up API keys

### RAG Organization
```
~/AI-Models/rag-system/
├── documents/
│   ├── pdfs/
│   ├── web-scrapes/
│   └── personal-notes/
├── vector-stores/
├── retrieval-configs/
└── query-interfaces/
```

## Maintenance Schedule

### Daily (5 minutes)
- [ ] Review downloads folder, organize files
- [ ] Check system updates available
- [ ] Quick scan of running processes in Activity Monitor

### Weekly (30 minutes)
- [ ] **File Audit**: Run the "Weekly Report Script" (see below)
- [ ] **Update packages**: `brew update && brew upgrade`, `conda update --all`
- [ ] **Clear cache**: Browser cookies, temporary files
- [ ] **Backup check**: Ensure Time Machine ran, cloud sync is current

### Monthly (1 hour)
- [ ] **Deep clean**: Clear old logs, unused downloads
- [ ] **Security audit**: Review installed apps, check for unused accounts
- [ ] **Performance check**: Disk space, memory usage patterns
- [ ] **Backup rotation**: Archive old project versions

### Quarterly (2 hours)
- [ ] **Full system backup** to external drive
- [ ] **Software audit**: Remove unused applications
- [ ] **Security updates**: Check all passwords, 2FA settings
- [ ] **Project archival**: Move completed projects to long-term storage

## Terminal Tutorial Basics

### Essential Commands to Master
```bash
# Navigation
pwd                    # Where am I?
ls -la                # List all files (including hidden)
cd ~/Development      # Go to Development folder
cd ..                 # Go up one directory

# File Operations
mkdir new-project     # Create directory
touch README.md       # Create empty file
cp file.txt backup/   # Copy file
mv old.txt new.txt    # Rename/move file
rm unwanted.txt       # Delete file (careful!)

# System Information
top                   # Running processes
df -h                 # Disk space usage
du -sh *              # Folder sizes in current directory
ps aux | grep python # Find Python processes

# Development Workflow
git status            # Check git status
git add .             # Stage all changes
git commit -m "message" # Commit changes
conda activate ds     # Switch to data science environment
jupyter lab           # Start Jupyter Lab
```

### Useful Aliases to Add to ~/.zshrc
```bash
alias ll='ls -la'
alias dev='cd ~/Development'
alias jlab='conda activate ds && jupyter lab'
alias gst='git status'
alias brewup='brew update && brew upgrade'
alias condaup='conda update --all'
```

## Weekly Report Script

Create this script at `~/Development/Tools/scripts/weekly_report.sh`:

```bash
#!/bin/bash
echo "=== WEEKLY MACBOOK REPORT - $(date) ==="
echo ""
echo "🗂️  LARGE FOLDERS (>1GB):"
find ~ -type d -exec du -sh {} \; 2>/dev/null | grep -E "^[0-9.]+G" | head -10
echo ""
echo "📦 RECENT DOWNLOADS:"
ls -lt ~/Downloads | head -10
echo ""
echo "🔧 CONDA ENVIRONMENTS:"
conda env list
echo ""
echo "💾 DISK USAGE:"
df -h
echo ""
echo "🔄 RECENT GIT ACTIVITY:"
find ~/Development -name ".git" -type d -exec sh -c 'cd "{}/.."; echo "=== $(pwd) ==="; git log --oneline -5' \;
```

Make it executable: `chmod +x ~/Development/Tools/scripts/weekly_report.sh`

## Installation Order Recommendation

1. **Week 1**: Core system tools, Homebrew, Git, Anaconda
2. **Week 2**: Development environments, VS Code, database tools  
3. **Week 3**: File organization, cloud sync, backup system
4. **Week 4**: Security tools, VPN, advanced configurations
5. **Week 5+**: RAG system, specialized tools as needed

## Quick Wins to Start With

1. Install Homebrew and Anaconda
2. Set up the folder structure
3. Configure git with your credentials
4. Install a password manager
5. Set up Time Machine backup

The key is not to do everything at once. Pick 2-3 items per day and build momentum!