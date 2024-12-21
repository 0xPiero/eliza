# Getting Started with Building AI Agents using ELIZA with no code experience

## Key Terms 
- **TypeScript**: 
  - TypeScript is a *programming language* (more flexible compared to Python). It is essentially JavaScript with added type system
  - Most popular programming language ecosystem globally, used in major applications like Discord, Microsoft Teams etc
  - Excellent handling of streaming and audio streams, strong HTTP and browser capabilities, superior async programming patterns, easy to work with async/await compared to alternatives
  - Works well for cross-platform applications (web, mobile, desktop)
  - Can interface with native code (C++, Swift, Objective-C, Java) through bridges like React Native or Capacitor.js
    - *tips: to learn JavaScript: https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/ and typescript: https://www.freecodecamp.org/news/learn-typescript-beginners-guide/*
  
- **Node.js**: An open-source, cross-platform JavaScript *runtime* environment that executes arbitrary JavaScript code outside of a web browser (which means you can build apps on it). It also has a thing called a package manager

- **package manager**: A package manager is a tool that allows developers to install, share, and manage code packages (modules) for their Node.js applications. 

- **npm**: stands for node package manager.It is were these packages are stored. It allows developers to install, share, and manage code packages (modules) for their Node.js applications. npm has a vast ecosystem of over 1 million packages written by lots of developers. Fun fact 99% of apps are using already written code. *Here we actually use npm not just for um downloading packages but also for running our project and like linking all those packages before we run it.*

- **monorepo**: A single repository that contains multiple packages. That means you can find all the packages (conflux, node, solana etc) in the packages folder. you can install eliza just like any packages into your project. BUt nmp is not very good at managing monorepos. 

- **pnpm**: It links packages in a monorepo. It is a fast, disk space efficient package manager for Node.js. pnpm uses a content-addressable filesystem to store packages, resulting in fewer file duplications. Rather use pnpm instead of npm to avoid npm missing packages. 

- **WSL**: Windows Subsystem for Linux. It is a Linux-like environment that works better with Node.js and pnpm. 
- **WSL2**: Windows Subsystem for Linux version 2. It is a newer version of WSL that works better with Node.js and pnpm. 

- **nvm**: Node Version Manager. It is a tool that allows you to install and manage multiple versions of Node.js on a single machine. It is useful for testing and developing applications that require different versions of Node.js.

- **Sharp**: A high-performance Node.js image processing library. It provides an easy-to-use API for resizing, converting, and manipulating images in various formats. Sharp is powered by the libvips library, which enables fast and efficient image processing operations.

## Step-by-Step Instructions
> 1. **Install Cursor**: 
  - *Cursor's AI-powered completions and intuitive interface make dev work faster and easier, so it's recommended to use it as your main code editor.*
  - Go to https://www.cursor.com/ and click "Download"
  - Choose the appropriate installer for your operating system (Windows, macOS, or Linux)
  - Run the installer and follow the installation wizard to complete the setup
  - *tips: watch this video to learn how to use cursor: https://www.youtube.com/watch?v=0-8a8WAAAHg*

> 2. **Install claude**: An AI assistant from Anthropic that excels in understanding and explaining code
   - Go to https://claude.ai/ and sign up for an account
   - Follow the instructions to create an API key
   - Save your API key securely, as you will need it later to configure ELIZA
   - *tips: use command+K or Ctrl+K and chose the model you want. Opus recommended but it is not enabled by default, so go to cursor settings > models > enable claude-3-opus*
   - *tips: watch this video to learn how to use AI in cursor: https://www.youtube.com/watch?v=g6L926wF0M0*

> 3. **Install Git**:
   - Visit https://git-scm.com/downloads
   - Download the Git installer for your operating system
   - Run the installer and follow the prompts, keeping the default options
   - Learn how to use git: https://www.youtube.com/watch?v=2ReR1YJrNOM and https://www.youtube.com/watch?v=6PZVwNTl5hI&t=2s
   - *Tip: you can open a terminal or command prompt and verify the installation by running: `git --version`*

> 4. **install WSL2**
   - Go to https://docs.microsoft.com/en-us/windows/wsl/install
   - Follow the instructions to install WSL2, you can watch this video to learn how to install WSL2 on windows: https://www.youtube.com/watch?v=eId6K8d0v6o

> 5. **Install Node.js, npm and pnpm**:
   - Install nvm (Node Version Manager) following these instructions https://github.com/nvm-sh/nvm using the curl function or these instructions if above does not work: https://www.youtube.com/watch?v=D53lAvrio0E
   - Install pnpm globally with: `npm install -g pnpm`

> 6. **Install code2prompt**:
  - *code2prompt is a utility that allows you to easily convert your code into a prompt-friendly format for AI models like Claude. It can help you generate code snippets, explanations, and more.*
  - *imagine you have a project with multiple files and you want AI help for understanding your code, getting improvement suggestions, generating documentation, and finding potential bugs*
  - *what you'd need to do manually without Code2Prompt:*
    - *copy and paste each file one by one*
    - *explain the structure of your project yourself*
    - *provide context about how files relate to each other*
    - *format everything properly for the AI*
  - *with Code2Prompt, you just point it to your code using path: code2prompt --path C:/MyProject*
  - *it automatically:*
    - *gathers all your relevant code files*
    - *formats them properly for AI*
    - *creates a structured prompt that helps AI understand your entire project*
    - *includes important context about file relationships and project structure*
  - Read https://github.com/raphaelmansuy/code2prompt
  - Open your terminal on Cursor or command prompt
  - Run the following command to install code2prompt globally:
    ```
    npm install -g code2prompt
    ```
  - *Tip: watch this video to learn how to use code2prompt:https://www.youtube.com/watch?v=cg5nY_kmN10*

> 7. **Clone the ELIZA template repository**: 
  - Go to https://ai16z.github.io/eliza/docs/quickstart/
  - follow the clone and install steps 
  - *Tips: if you clone a repository, you always run `pnpm install` to install all the packages which are in the package.json file*  

> 8. **Install dependencies and start the agent**:
  - Navigate into the project: `cd eliza`
  - Install with: `pnpm install` 
  - *Tip: If you encounter errors related to image processing, run `pnpm install --include=optional sharp` to install the Sharp library.*
  - Create a `.env` file by copying example environment file: `cp .env.example .env` which will create a new file called `.env`
  - Add your values and API keys to the `.env` file
  - Build the project: `pnpm build`
  - Start the agent: `pnpm start`
