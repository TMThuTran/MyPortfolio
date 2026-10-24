# How to publish your site (free, about 20 minutes)

Your site runs on GitHub Pages, which builds and hosts it for free. You don't need to install anything.

## 1. Create a GitHub account

Go to github.com and sign up. Pick your username carefully: it becomes part of your address, for example `thutran` gives you `https://thutran.github.io`.

## 2. Create the repository

1. Click **+** (top right) and choose **New repository**.
2. Name it exactly `YOUR-USERNAME.github.io`, using your own username in lowercase.
3. Set it to **Public**, leave everything else as it is, and click **Create repository**.

## 3. Upload the site

1. Unzip `thutran-site.zip` on your computer.
2. In your new repository, click **uploading an existing file** (or **Add file > Upload files**).
3. Open the unzipped `thutran-site` folder, select **everything inside it** (not the folder itself) and drag it onto the upload area. Folders like `_posts` and `_projects` keep their structure.
4. Click **Commit changes**.

## 4. Turn on GitHub Pages

1. In the repository, go to **Settings > Pages**.
2. Under **Build and deployment**, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and click **Save**.
3. Wait one or two minutes. The **Actions** tab shows a green tick when the site is live, and Settings > Pages shows the address.

## 5. Set your address

Open `_config.yml` in the repository, click the pencil icon, and replace `YOUR-GITHUB-USERNAME` with your username. Commit. This makes link previews on LinkedIn show the right address.

---

## Everyday editing

You can do all of this in the browser on github.com.

- **Write a new post:** copy `templates/new-post.md`, create a new file in the `_posts` folder named like `2026-11-02-my-post-title.md`, paste, and write. The date in the file name is the publish date.
- **Add a side project:** do the same with `templates/new-project.md`, in the `_projects` folder.
- **Career case studies** (Adyen, Accenture) live in the `_work` folder and are linked from the About page.
- **Add a book:** edit `_data/books.yml` and copy one of the existing blocks. The cover is found automatically from the ISBN.
- **Change your bio or experience:** edit `about.md`.
- **Change the home page headline or results:** edit `index.html`. The text sits between the tags, so change only the words.
- **Change your name, email or LinkedIn:** edit `_config.yml`.

Every time you commit, the site updates within about a minute. If something breaks, the **Actions** tab shows a red cross and the error; you can always undo by opening the file's **History** and restoring the previous version.

## Before you go public

- Read every page and adjust anything that doesn't sound like you. Places where you can add detail are marked with `<!-- -->` comments, which don't show on the site.
- Check that nothing reveals confidential details from current or past employers.
- Add your site link to your LinkedIn profile (Contact info > Website) and your CV.

## Optional: your own domain

A domain like `thutran.nl` costs roughly €10–15 a year from a registrar such as TransIP or Cloudflare. Add it in Settings > Pages > Custom domain and follow GitHub's instructions for the DNS records. Nothing else on the site needs to change.
