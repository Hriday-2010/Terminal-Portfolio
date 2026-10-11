# Terminal Portfolio

An interactive, terminal-style portfolio for **Hriday Shah**, an MSc Risk Management & Financial Engineering student at Imperial College London. Visitors explore my background by typing commands, the same way they would in a real shell.

**Live site:** https://hriday-2010.github.io/Terminal-Portfolio/

---

## Quick start for visitors

Open the site and try:

```
help              # every command
ll                # list the "files" in the portfolio
cd projects       # move into a section
cat README.md     # read it
cd ..             # go back
tree              # see the whole layout
```

## Commands

**Portfolio sections**

| Command | What it shows |
|---|---|
| `about` | Who I am and what I'm working on |
| `experience` | Work experience, leadership and competitions |
| `projects [--all]` | Featured quant & ML projects; `--all` adds earlier engineering work |
| `skills` | Technical skills and spoken languages |
| `education` | Imperial, VIT, CFA and schooling |
| `publications` | Patents, papers and certifications |
| `achievements` | Awards, competitions and volunteering |
| `contact` | Email, GitHub, LinkedIn and what I'm looking for |
| `resume` | Opens my resume PDF (same as `cat resume.pdf`) |

**Shell-style commands**

| Command | What it does |
|---|---|
| `ls [-l] [-a] [dir]` | List files in a directory |
| `ll` | Long listing (same as `ls -la`) |
| `cd <dir>` | Change directory (`cd ..`, `cd ~`, `cd` on its own goes home) |
| `pwd` | Print the current directory |
| `cat <file>` | Show a file, e.g. `cat about.txt` |
| `tree` | Show the whole portfolio file tree |
| `echo <text>` | Print text back |
| `whoami`, `date`, `history`, `uname [-a]`, `neofetch` | The usual suspects |
| `man <command>` or `<command> --help` | Describe a command |
| `github`, `linkedin`, `email` | Open my profiles |
| `theme [name]` | List themes or switch; theme names (default, dark, light, solarized, dracula) also work on their own |
| `clear` | Clear the screen |

Tab completes commands and file names, and ↑/↓ scroll through command history. There are a few easter eggs too.

### Safety

Everything runs in the visitor's browser against a small, read-only, in-memory file tree. No command touches the visitor's machine or any server. Destructive or privileged commands (`rm`, `sudo`, `chmod`, `mv`, `curl`, and similar) are refused with a "permission denied" message, and anything a visitor types is displayed as plain text, never run as HTML.

---

## Tech

- A single `index.html`: plain HTML, CSS and JavaScript, no build step or framework
- [Font Awesome](https://fontawesome.com/) for icons
- Deployed to GitHub Pages by the workflow in `.github/workflows/static.yml` on every push to `main`

## Repository structure

```
.
├── index.html                    # The whole site: markup, styles, terminal logic and content
├── Hriday_Shah_Resume.pdf        # Resume opened by `resume` / `cat resume.pdf`
├── trial-webs/                   # Earlier design drafts, kept for reference
├── .github/workflows/static.yml  # GitHub Pages deployment
└── README.md
```

## Run locally

```bash
git clone https://github.com/Hriday-2010/Terminal-Portfolio.git
cd Terminal-Portfolio
# open index.html in a browser, or serve it:
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Updating the content

All portfolio text lives in the `sections` object inside the `<script>` in `index.html` (`about`, `experience`, `projects`, `skills`, `education`, `publications`, `achievements`, `contact`). To update the resume, replace `Hriday_Shah_Resume.pdf` with a file of the same name. Edit the text there and both the named command (e.g. `projects`) and the matching file (e.g. `cat projects/README.md`) update together.

To add a command, add an entry to the `commands` object with a `description` and an `execute(args)` function that returns the HTML to print.

---

## How it was built

I built the first version with AI tools (DeepSeek, DeepSite AI and ChatGPT) at a point when I hadn't done web development before: I described the terminal look and behaviour I wanted, then iterated on the generated code for styling, responsiveness and commands. Later updates, including the shell commands and the refreshed content, were made with Claude. It's been a practical way to learn front-end work by reading, testing and changing real code.

## Contact

- Email: shah.hriday03@gmail.com
- LinkedIn: [hriday-shah03](https://www.linkedin.com/in/hriday-shah03)
- GitHub: [Hriday-2010](https://github.com/Hriday-2010)
