---
title: Setting up terminal into a powerful and customizable tool with Oh My Posh and Lazygit
date: "2023-07-17"
---
<script>
    import { CodeBlock } from '@skeletonlabs/skeleton';
</script>

<img src="https://i.ibb.co/SJfM2BZ/img-20230718-211010.png" alt="oh-my-posh" />

As a programmer, you spend a significant amount of time in the terminal. So why not make it an amazing and visually appealing experience? In this blog post, I'll share my minimum Powershell setup on Windows Terminal with <a class="anchor" href="https://ohmyposh.dev/">Oh My Posh</a> and <a class="anchor" href="https://github.com/jesseduffield/lazygit">Lazygit</a> to transform your command line interface into a powerful and customizable tool.

<h3 class="h3">Motivation</h3>

To simplify the motivation of doing all of this, I just tell you two reasons:

<ul class="list">
    <li>
        <span>•</span>
        <span><strong>Branch information</strong>, branch information is not exist by default unless you're using git bash.</span>
    </li>
    <li>
        <span>•</span>
        <span>Terminal UI and <strong>shortcut for git commands</strong> that will save you a ton of times.</span>
    </li>
</ul>

Now, let's get started:

<h3 class="h3">Step 1: Install Windows Terminal</h3>

If you haven't already, head over to the Microsoft Store or GitHub and install Windows Terminal on your Windows machine. Windows Terminal is free and provides an excellent foundation for customizing your terminal experience.

<h3 class="h3">Step 2: Install Powershell</h3>

If you're using Windows 11, I believe PowerShell is already the latest version which has autosuggestion feature by default. But most of the times, if you're using Windows 10, you need to update PowerShell to the latest version to get the autosuggestion feature. There's many way to that but what I usually do, is head over to the <a class="anchor" href="https://github.com/PowerShell/PowerShell">PowerShell GitHub</a>, download the desired file, and install it.

<h3 class="h3">Step 3: Install Oh My Posh</h3>

To install Oh My Posh, we'll use PowerShell, which is integrated into Windows Terminal. Open Windows Terminal and launch PowerShell.

Head over to <a class="anchor" href="https://ohmyposh.dev/docs/installation/windows">Oh My Posh documentation</a> to complete the installation.

<h3 class="h3">Step 4: Choose a Theme</h3>

After you completed the installation, you notice that you're already have a theme, you can keep using that or you can change that with many other themes.

Because I'm super original, I usually using Robby Russel theme the creator of Oh My Zsh. I recommend you using this theme, beacuse it's simple but also covered all your needs.

To do it, simply open your PowerShell profile script. For example, using notepad:

<CodeBlock language="powershell" code={`notepad $PROFILE`}></CodeBlock>

And here's mine, you can copy paste to yours:

<CodeBlock language="txt" code={`oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/robbyrussell.omp.json" | Invoke-Expression`}></CodeBlock>

Save and reload the Terminal to see the changes.

<h3 class="h3">Step 5: Install Lazygit</h3>

You need <a class="anchor" href="https://scoop.sh/">scoop</a> to help you easily install things on your system including Lazygit.

After you have scoop, then head over to <a class="anchor" href="https://github.com/jesseduffield/lazygit#scoop-windows">lazygit documentation</a> to complete the installation.

<h3 class="h3">Step 6: Enjoy Your Amazing Terminal</h3>

Restart Windows Terminal, and you'll see the magic happen. The prompt will be transformed with your chosen theme from Oh My Posh. You can now enjoy an aesthetically pleasing and informative terminal environment that enhances your productivity as a programmer.

You can now run <code class="code">lazygit</code> on your project directory that connected to git to help you leveraging all git features with beautifull UI and shortcuts.

Feel free to explore Oh My Posh and Lazygit further and customize your prompt according to your preferences. You can adjust colors, icons, and even add your own customizations to make your terminal truly unique.
