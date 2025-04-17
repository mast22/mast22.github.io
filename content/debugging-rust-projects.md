+++
title = "Modern debugging Rust projects in VSCode"
date = "2023-02-12"
+++

# Introduction
I won’t bug you with an explanation, at this level you should be perfectly knowledgeable to reason and be able to retrieve information from the internet as efficiently as possible. I won't even blame if you don't read this paragraph, just go copy-and-paste config I've provided below this wall of text.

# The config

1. Setup a `.vscode/tasks.json` file in your project, don't forget to add it to `.gitignore`. It will include a job that will build your rust project every time you start a debugging session.

2. Setup a `.vscode/launch.json` as well. It will be responsible for launching the debugging session. **Notice that you will need to change 2 things in launch.json**: program argument, replace `<your_binary>` with well... you know. Secondly, remove or edit `args` to pass your arguments to the program.

3. Run with F5, you should be good to go.

`.vscode/tasks.json`
```
{
	"version": "2.0.0",
	"tasks": [
		{
			"label": "rust: cargo build",
			"type": "cargo",
			"command": "build",
			"problemMatcher": [
				"$rustc"
			],
			"group": "build"
		}
	]
}
```

`.vscode/lauch.json`
```
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "lldb",
            "request": "launch",
            "name": "Run app with test args",
            "program": "${workspaceFolder}/target/debug/<your_binary>",
            "args": ["--config", "./etc/config.dev.toml"],
            "cwd": "${workspaceFolder}",
            "preLaunchTask": "rust: cargo build"
        }
    ]
}
```
