# Setting Up Git and GitHub with SSH on a New Mac

## 1. Install Git
Open Terminal and run:
```
git --version
```
If Git is not installed, follow the prompts to install Xcode Command Line Tools.

## 2. Create a GitHub Account
Go to https://github.com and sign up if you don’t have an account.

## 3. Generate a New SSH Key
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
- Replace with your GitHub email.
- Press Enter to accept the default location.
- Enter a passphrase (optional) or press Enter for none.

## 4. Start the SSH Agent and Add Your Key
```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

## 5. Add Your SSH Key to GitHub
- Copy your public key:
  ```
  pbcopy < ~/.ssh/id_ed25519.pub
  ```
- Go to https://github.com/settings/keys
- Click “New SSH key”, paste the key, give it a name, and save.

## 6. Test Your SSH Connection
```
ssh -T git@github.com
```
- Type “yes” if prompted.
- You should see a welcome message.

## 7. Clone a Repo or Set Up a New One
- To clone:
  ```
  git clone git@github.com:username/repo.git
  ```
- To create a new repo:
  - On GitHub, click “New repository” and follow the instructions.
  - Initialize your local folder:
    ```
    git init
    git remote add origin git@github.com:username/repo.git
    ```

## 8. Make Changes, Stage, Commit, and Push
- Edit or add files.
- Stage:
  ```
  git add .
  ```
- Commit:
  ```
  git commit -m "Your message"
  ```
- Push:
  ```
  git push origin main
  ```
  (or `master` if your branch is named that)

---
You’re all set!
