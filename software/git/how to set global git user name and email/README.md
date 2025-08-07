
# How to Set Global Git User Name and Email

To configure your global Git user name and email, you can use the following commands in your terminal or command prompt. This is important for identifying the author of commits in your repositories.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Replace "Your Name" with your actual name and "your.email@example.com" with your email address. This will configure Git to use this information for all your repositories.

You can verify your settings by running:

```bash
git config --global user.name
git config --global user.email
```