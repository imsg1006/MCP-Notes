# 📝 Notes Tool via MCP-Server for ClaudeAI

This project is a custom **MCP-Server (Model-Context Protocol Server)** built using **Python** that enables **ClaudeAI** to create, read, append, and summarize notes stored locally within a specified folder structure. Once the tool is connected, ClaudeAI can interact with your file system to manage notes using natural language prompts.

---

## 📌 Project Overview

The Notes MCP-Server lets ClaudeAI interact with your local notes using a simple conversational interface. It leverages Claude's tool support to provide seamless access to operations like:

- ✍️ Creating new notes  
- 📖 Reading existing notes  
- ➕ Appending to notes  
- 📄 Summarizing note content

Once set up, prompts like:
> "Create a new note titled Meeting Ideas"  
> "Summarize all notes in this folder"  
> "Read my note on project milestones"

…will activate the tool and execute the requested operation inside your open folder's directory.

---

## ⚙️ Tech Stack

- **Python** – logic for file creation, reading, appending, and summarizing  
- **MCP Server Protocol** – enables ClaudeAI to invoke this as a tool  
- **Local FileSystem Access** – stores and reads `.txt` notes from the active folder  
- **ClaudeAI Desktop Configuration** – used for tool registration via `claude_desktop_config.json`  

---

## 🛠️ Setup Instructions

### 1. Clone this Repository

```bash
git clone https://github.com/your-username/notes-mcp-server.git
cd notes-mcp-server
```

### 2. Install Python Dependencies

Make sure you have Python 3.10+ installed.

```bash
pip install -r requirements.txt
```

You may want to create a virtual environment first:

```bash
# Linux/macOS
python -m venv venv && source venv/bin/activate

# Windows
python -m venv venv && .\venv\Scripts\activate
```

---

## 🚀 How to Run

### Step 1: Start the Notes MCP Server

```bash
python notes.py
```

This will launch your local server that handles note creation and interaction within the currently opened folder.

### Step 2: Register the Tool in claude_desktop_config

1. Open your `claude_desktop_config.json` file (usually located inside ClaudeAI's configuration directory)
2. Find the `arguments` field
3. Add or update it to point to your `notes.py` script like this:

```json
"arguments": [
  "python",
  "C:/full/path/to/notes.py"
]
```

4. Save the file and restart ClaudeAI Desktop

### Step 3: Use the Tool in ClaudeAI

1. Open ClaudeAI Desktop
2. You'll see a new tool appear automatically
3. Use natural language prompts such as:
   - "Create a note called todo-list"
   - "Append 'Finish report' to my todo-list note"
   - "Summarize all my notes"
4. Claude will request permission to use the tool — click **Allow** to enable it

---

## 📋 Features

- **Create Notes**: Generate new `.txt` files with specified content
- **Read Notes**: Access and display existing note content
- **Append Content**: Add new information to existing notes
- **Summarize**: Get AI-powered summaries of your notes
- **Folder-based Organization**: Works within your current directory structure

---

## 🔧 Configuration

The tool operates within the folder where the MCP server is running. Make sure to:

- Run the server from the directory where you want to store your notes
- Ensure proper file permissions for read/write operations
- Update the path in `claude_desktop_config.json` to match your installation

---

## 📄 File Structure

```
notes-mcp-server/
├── notes.py              # Main MCP server script
├── requirements.txt      # Python dependencies
├── README.md            # This file
└── [your-notes]/        # Generated notes folder
    ├── note1.txt
    ├── note2.txt
    └── ...
```

---

## 🤝 Contributing

Feel free to submit issues and pull requests to improve this tool. Make sure to:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📜 License

This project is open source. Please check the LICENSE file for details.

---

## 🆘 Support

If you encounter any issues:

1. Check that Python 3.10+ is installed
2. Verify the path in `claude_desktop_config.json` is correct
3. Ensure ClaudeAI Desktop has been restarted after configuration
4. Check file permissions in your target directory

For additional help, please open an issue in the repository.
