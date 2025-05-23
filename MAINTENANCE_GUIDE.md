# Maintaining Your Academic Homepage

## 1. Overview

This website is your academic homepage. It's built using a tool called Jekyll, which is a simple static site generator. The live website is hosted directly from your GitHub repository using GitHub Pages. This means any changes you make to the files in this repository and push to GitHub will automatically update your live site.

## 2. Editing Content

Most of your content is stored in Markdown files (`.md`), which are plain text files that are easy to edit.

### Personal Information (Home/About Me Page)

Your personal information, such as your biography, research interests, and contact details, is located in the `index.md` file in the root of the repository.

**To update your personal information:**

1.  Find and open the `index.md` file.
2.  Edit the text directly using Markdown syntax. For example:
    ```markdown
    # Jerry Song

    **PhD Student**  
    East China University of Science and Technology

    **Research Interests:** Digital Microfluidics, [Your New Interest Here]

    **Contact:** [ibechanged@gmail.com](mailto:ibechanged@gmail.com)

    ---

    Welcome to my academic homepage!
    [Update your bio or welcome message here.]
    ```
3.  Save the changes to `index.md`.

### Publications

Your publications are listed in the `publications.md` file.

**To add a new publication:**

1.  Find and open the `publications.md` file.
2.  Manually add the new publication as formatted text. You can follow the existing format or create a simple list. For example:
    ```markdown
    ---
    layout: default
    title: Publications
    permalink: /publications/
    ---

    # Publications

    *   **Song, J.**, Author, B., & Author, C. (Year). Title of Your Amazing Paper. *Journal Name*, Volume(Issue), pages. [Link to paper if available]
    *   Author, A., **Song, J.**, & Author, C. (Year). Another Great Publication. *Conference Proceedings*, pages. [Link to paper if available]

    (Previously: No publications yet. This section will be updated soon.)
    ```
3.  Ensure consistent formatting for each entry.
4.  Save the changes to `publications.md`.

**Note for a growing list:** As your list of publications grows, manually editing this file can become cumbersome. A future enhancement could be to store publication data in a structured file (like `_data/publications.yml` or by integrating a BibTeX file) and then have Jekyll automatically generate this page. This would make managing publications easier and less prone to formatting errors.

## 3. Previewing Changes Locally (Recommended)

Before your changes go live, it's highly recommended to preview them on your own computer. This helps you catch any mistakes or formatting issues.

**To set up and run Jekyll locally:**

1.  **Install Jekyll and Bundler:**
    *   You'll need Ruby installed on your computer first. If you don't have it, visit [https://www.ruby-lang.org/en/documentation/installation/](https://www.ruby-lang.org/en/documentation/installation/).
    *   Once Ruby is installed, open your terminal or command prompt and run:
        ```bash
        gem install bundler jekyll
        ```
2.  **Navigate to your site's directory:**
    *   In your terminal, change to the directory where you've cloned this repository.
        ```bash
        cd path/to/your/academic-homepage-repository
        ```
3.  **Install dependencies (first time or if Gemfile changes):**
    *   If you have a `Gemfile` (which defines specific versions of Jekyll and its plugins), it's best to run:
        ```bash
        bundle install
        ```
    *   (Note: This project currently uses the default theme `jekyll-theme-minimal` and doesn't have a complex `Gemfile` initially, but `bundle install` is good practice).
4.  **Run the local Jekyll server:**
    *   Execute the following command:
        ```bash
        bundle exec jekyll serve
        ```
    *   If you don't have a `Gemfile` or prefer not to use Bundler for a simple site, you might be able to run `jekyll serve`. However, `bundle exec jekyll serve` is generally recommended.
5.  **Access your local site:**
    *   Open your web browser and go to `http://localhost:4000`. You should see a local version of your website.
    *   As you make changes to files and save them, Jekyll will often automatically rebuild the site. You may need to refresh your browser to see the updates.

## 4. Deploying to GitHub Pages

Once you're happy with your changes (after previewing them locally), you need to "deploy" them to make them live on your GitHub Pages site.

1.  **Commit your changes:**
    *   In your terminal (in your site's directory), add the files you've changed:
        ```bash
        git add . 
        # (This adds all changes. You can also add specific files, e.g., git add index.md publications.md)
        ```
    *   Commit them with a descriptive message:
        ```bash
        git commit -m "Updated personal information and added new publication"
        ```
2.  **Push your changes to GitHub:**
    *   Push the committed changes to your main repository branch (usually `main` or `master`):
        ```bash
        git push origin main 
        # (Or 'git push origin master' if your default branch is named master)
        ```
3.  **Automatic Rebuild:**
    *   GitHub Pages will automatically detect these new changes, rebuild your Jekyll site, and update your live website. This usually takes a minute or two. You can then visit your live academic homepage URL to see the updates.

## 5. File Structure Overview (Optional but helpful)

Here are some of the key files and folders in your Jekyll site:

*   `_config.yml`: The main configuration file for your Jekyll site. It includes your site title, theme, plugins, and other settings. You might occasionally edit this if you want to change fundamental site settings.
*   `index.md`: The main page of your website (your "Home" or "About Me" page).
*   `publications.md`: The page where your list of publications is maintained.
*   `_layouts/`: This folder contains the HTML templates for your site's structure (e.g., `default.html`). You typically won't need to edit these unless you want to make significant changes to the site's overall design.
*   `assets/`: This folder is for static files like CSS, images (if you add any), or JavaScript. `assets/css/style.scss` imports the theme's stylesheet.
*   `_posts/`: If you decide to add a blog, your blog posts would go here. (Currently unused)
*   `_data/`: (Optional, not created yet) If you implement the suggestion for managing publications with data files, you would create this folder (e.g., `_data/publications.yml`).

This guide should help you keep your academic homepage up-to-date!
