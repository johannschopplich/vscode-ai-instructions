# VSCode AI Instructions

> [!NOTE]
> A collection of guidelines for AI responses that match my specific coding practices, preferred technologies, and project requirements.

Hot take: VS Code has catched up to Cursor in terms of AI features. I actually prefer VS Code over Cursor for its tidy Copilot chat interface. Agent mode is pretty usable for months now and with the [latest version 1.100](https://code.visualstudio.com/updates/v1_100), it supports [intruction files for code style rules](https://code.visualstudio.com/docs/copilot/copilot-customization#_use-instructionsmd-files) or framework-specific guidelines.

## Usage

### Project-specific Instructions

VS Code automatically includes the instructions from the `.github/copilot-instructions.md` file to every chat request and applies them for generating code.

If you don't want to use the custom instructions from this repository for all your projects, you can pick one of the instructions files from the [`instructions`](./instructions) directory and save it as `.github/copilot-instructions.md` in your project root.

> [!TIP]
> Make sure the [`github.copilot.chat.codeGeneration.useInstructionFiles`](vscode://settings/github.copilot.chat.codeGeneration.useInstructionFiles) setting is enabled in your workspace settings.

### Specify Custom Instructions in Settings

Custom instructions can be defined as text in the settings value or referenced from an external file.

To reference the custom instructions from this repository in your user or workspace [`github.copilot.chat.codeGeneration.instructions`](vscode://settings/github.copilot.chat.codeGeneration.instructions) settings, add the following lines to your `settings.json` file:

```json
"github.copilot.chat.codeGeneration.instructions": [
  {
    "file": "<root>/vscode-ai-instructions/instructions/general-coding.instructions.md",
  },
  {
    "file": "<root>/vscode-ai-instructions/instructions/typescript-vue.instructions.md",
  }
]
```

### Generate Instructions From Your Codebase

Use the [Instruction Generator](./generate-instruction-prompt.md) prompt to create a set of coding instructions that accurately reflect your coding practices and tech stack.

Paste the prompt into your Copilot chat window, append some files for context or use the `#codebase` tool and run it. The AI will analyze the codebase and generate a set of coding instructions that you can use to guide your coding practices.

## Tips for Defining Custom Instructions

Excerpt from the VS Code documentation on [Customize chat responses in VS Code](https://code.visualstudio.com/docs/copilot/copilot-customization#_tips-for-defining-custom-instructions):

- Keep your instructions short and self-contained. Each instruction should be a single, simple statement. If you need to provide multiple pieces of information, use multiple instructions.
- Don't refer to external resources in the instructions, such as specific coding standards.
- Split instructions into multiple files. This approach is useful for organizing instructions by topic or type of task.
- Make it easy to share custom instructions with your team or across projects by storing your instructions in instruction files. You can also version control the files to track changes over time.
- Use the `applyTo` property in the instruction file header to automatically apply the instructions to specific files or folders.
- Reference custom instructions in your prompt files to keep your prompts clean and focused, and to avoid duplicating instructions for different tasks.
