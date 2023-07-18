---
title: Make terminal your best friend
date: "2023-07-17"
---
<script>
    import { CodeBlock } from '@skeletonlabs/skeleton';
</script>

<img src="https://i.ibb.co/SJfM2BZ/img-20230718-211010.png" alt="oh-my-posh" />

As a programmer, you spend a significant amount of time in the terminal. So why not make it an amazing and visually appealing experience? In this blog post, I'll guide you through the process of setting up Windows Terminal with Oh My Posh to transform your command line interface into a powerful and customizable tool.

### What is Windows Terminal and Oh My Posh?

Before we dive into the setup process, let's briefly explain what Windows Terminal and Oh My Posh are:

- **Windows Terminal:** Windows Terminal is a modern, feature-rich terminal application for Windows that allows you to run command-line tools, PowerShell, and WSL (Windows Subsystem for Linux) in a single interface. It provides a highly customizable and efficient environment for your development workflow.

- **Oh My Posh:** Oh My Posh is a cross-platform framework for customizing your terminal prompt. It offers a vast collection of themes, icons, and customization options to make your prompt visually appealing and informative. Oh My Posh works with various terminal applications, including Windows Terminal.

Now, let's get started with the setup process:

### Step 1: Install Windows Terminal

If you haven't already, head over to the Microsoft Store or GitHub and install Windows Terminal on your Windows machine. Windows Terminal is free and provides an excellent foundation for customizing your terminal experience.

### Step 2: Install Oh My Posh

To install Oh My Posh, we'll use PowerShell, which is integrated into Windows Terminal. Open Windows Terminal and launch PowerShell.

Next, we need to install the required dependencies. Run the following command in the PowerShell prompt:

<CodeBlock language="powershell" code={`Install-Module posh-git -Scope CurrentUser`}></CodeBlock>

This command installs the <code class="code">`posh-git`</code> module, which provides Git integration for your terminal prompt.

Once the installation is complete, install Oh My Posh by running the following command:

<CodeBlock language="powershell" code={`Install-Module oh-my-posh -Scope CurrentUser`}></CodeBlock>

Oh My Posh will now be installed on your system.

### Step 3: Choose a Theme

Oh My Posh offers a wide range of themes to choose from. These themes define the appearance and information displayed in your terminal prompt. To select a theme, open your PowerShell profile file. If you don't have one, create it by running the following command:

<CodeBlock language="powershell" code={`notepad $PROFILE`}></CodeBlock>

In the profile file, add the following lines to set the theme:

<CodeBlock language="powershell" code={`Import-Module oh-my-posh
Set-Theme <theme-name>`}></CodeBlock>

Replace <code class="code">`<theme-name>`</code> with the name of your desired theme. To explore the available themes, you can visit the Oh My Posh GitHub repository.

Save the profile file and close the editor.

### Step 4: Configure Windows Terminal

To integrate Oh My Posh with Windows Terminal, we need to update the terminal's configuration file. Open Windows Terminal, click on the down arrow icon at the top of the window, and select "Settings." This will open the <code class="code">`settings.json`</code> file.

Within the <code class="code">`"profiles"`</code> section of the file, locate the profile you want to customize, usually <code class="code">`"defaults"`</code> or <code class="code">`"powershell"`</code>. Add the following line to the profile's <code class="code">`"commandline"`</code> property:


<CodeBlock language="powershell" code={`"commandline": "pwsh.exe -NoLogo -ExecutionPolicy Bypass -NoProfile -Command \"Import-Module oh-my-posh; Set-Theme <theme-name>\""`}></CodeBlock>

Replace <code class="code">`<theme-name>`</code> with the same theme name you selected in Step 3.

Save the <code class="code">`settings.json`</code> file, and you're done!

### Step 5: Enjoy Your Amazing Terminal

Restart Windows Terminal, and you'll see the magic happen. The prompt will be transformed with your chosen theme from Oh My Posh. You can now enjoy an aesthetically pleasing and informative terminal environment that enhances your productivity as a programmer.

Feel free to explore Oh My Posh further and customize your prompt according to your preferences. You can adjust colors, icons, and even add your own customizations to make your terminal truly unique.
