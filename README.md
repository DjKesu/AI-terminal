# GPT-Powered Linux Terminal Assistant

## Overview
This project is an interactive Linux terminal assistant powered by OpenAI's GPT-4o-mini. It provides users with Linux command suggestions based on natural language prompts, detailed explanations for commands, and options for executing commands directly from the terminal. The assistant aims to streamline terminal usage for both new and experienced users.

## Features
- **Command Generation**: Uses GPT-4o-mini to generate safe and efficient Linux commands from user prompts.
- **Command Execution**: Supports executing generated commands via `subprocess` with safety checks and user confirmation.
- **Command Explanation**: Provides detailed explanations of commands generated by GPT-4o-mini.
- **Interactive Mode**: Allows users to enter interactive shell mode to ask multiple queries without restarting the script.
- **Safety Checks**: Implements validation to prevent potentially dangerous commands (e.g., `rm -rf`).
- **Logging**: Logs user queries, generated commands, and command execution details for transparency and troubleshooting.

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/DjKesu/AI-terminal.git
   cd gpt-linux-assistant
   ```

2. **Install Dependencies**:
   This project requires Python 3 and `openai` library.
   ```bash
   pip install openai
   ```

3. **Set Up OpenAI API Credentials**:
   Set your OpenAI API key and Organization ID as environment variables:
   ```bash
   export openAIKey='your-api-key'
   export openAIOrgId='your-org-id'
   ```

4. **Set Up Alias for Startup**:
   To easily run the assistant from anywhere, set up an alias in your shell configuration file (e.g., `.bashrc`, `.zshrc`). Add the following line:
   ```bash
   alias askgpt="/path/to/AI-terminal/askgpt.py"
   ```
   Replace `/path/to/AI-terminal/` with the actual path to the cloned repository.

   After adding the alias, run the following command to apply the changes:
   ```bash
   source ~/.bashrc  # or source ~/.zshrc
   ```

## Usage
Run the script with the following options:
- **Generate a Command**:
  ```bash
  askgpt -p "list all files in the current directory"
  ```
- **Generate and Run a Command**:
  ```bash
  askgpt -p "find files with name ai included in them" -r
  ```
- **Interactive Mode**:
  ```bash
  askgpt -i
  ```

## Command-Line Arguments
- `-p`, `--prompt`: The prompt you want to ask GPT.
- `-r`, `--run`: Automatically run the generated command.
- `-e`, `--explain`: Provide an explanation of the generated command.
- `-i`, `--interactive`: Enter interactive mode to ask multiple queries.

## Example Commands
- **Prompt for a Linux Command**:
  ```
  askgpt -p "how to find all .txt files in a directory"
  ```
  **Output**:
  ```
  Generated Command:
  find . -name "*.txt"
  ```

- **Explanation**:
  ```
  askgpt -p "how to find all .txt files" -e
  ```
  **Output**:
  ```
  The command `find . -name "*.txt"` searches the current directory and all subdirectories for files ending with `.txt`.
  ```

## Safety Considerations
- The assistant includes checks to prevent execution of dangerous commands (e.g., `rm -rf`, `mkfs`).
- Commands are only executed after user confirmation, ensuring you have full control.

## Logging
- All commands, queries, and execution details are logged to `~/askgpt.log` for reference and debugging.

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests to improve functionality or add new features.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact
For any questions, feel free to contact me at [krish.mehta@uwaterloo.ca](mailto:krish.mehta@uwaterloo.ca).
