# DevOps Associate labs

Hands-on labs for the SynLearn **DevOps Associate** course, modules A7 to A14:
Docker, GitHub Actions CI/CD, Terraform, Ansible and observability.

Everything runs in a GitHub Codespace, a Linux machine in your browser with
Docker, Terraform 1.12, Python 3 and Ansible already installed.

> **Never put real cloud keys, passwords or tokens in this repository or codespace.**
> The labs never need them. Terraform labs use local providers only, and a secret that is
> committed once stays in the history even in a private repository.

## 1. Create your copy and open it

1. Click **Use this template → Create a new repository**. Keep the name
   `devops-associate-labs` and make it **private**, so nobody can copy your answers (private repositories still get free GitHub Actions minutes; a graded check takes about a minute).
2. In your new repository click **Code → Codespaces → Create codespace on main**.
3. Wait for the setup to finish (a few minutes the first time). The terminal is at the bottom.

## 2. Link the codespace to SynLearn

Open any lab lesson on SynLearn while signed in. It shows a one-time code. In the terminal:

```bash
synlearn login ABCD-1234
```

The code works once and expires after a few minutes. If it has expired, reload the lesson page for a new one.
Login also writes `.synlearn/link-id`. Commit and push that file so graded labs are credited to you:

```bash
git add .synlearn/link-id && git commit -m "link synlearn" && git push
```

## 3. Do a lab

```bash
synlearn setup a07-first-image    # creates the starter files for the lab
synlearn check a07-first-image    # checks your work and records your progress
synlearn status                   # shows whether you are logged in
synlearn --help
```

Each check prints `PASS` or `FAIL` lines. A `FAIL` line tells you what to fix. The lab id is on the lesson page.

### Graded labs

Some labs (usually the last lab in a module) are **graded**. The lesson tells you to add
the lab id to `.synlearn/graded-labs` and push. GitHub Actions then runs the official
checks on your repository and sends the result to SynLearn. You can see the result in the
**Actions** tab of your repository. Do not edit `.github/workflows/synlearn-graded.yml`;
SynLearn only accepts results from the official checks.

## 4. Save your free quota

A free GitHub account includes **120 core hours** of Codespaces a month (60 hours on this
2-core machine) and **15 GB-month** of storage. A stopped codespace still uses storage.

- **Set a short idle timeout.** In [github.com/settings/codespaces](https://github.com/settings/codespaces)
  set *Default idle timeout* to 15 minutes, so a forgotten codespace stops itself.
- **Set a short retention period** on the same page (for example 3 days), so stopped codespaces are deleted automatically.
- **Delete a codespace when you finish a module.** Push your work first, then open
  [github.com/codespaces](https://github.com/codespaces), click **…** next to the codespace
  and choose **Delete**. Your code is safe in the repository; the next codespace starts fresh.
- Clean up Docker images inside the codespace with `docker system prune -a` when a lab says you are done with them.

## Folders

| Folder | Module |
|---|---|
| `a07-containers/` | A7 · Containers with Docker |
| `a08-cicd/` | A8 · CI/CD with GitHub Actions |
| `a09-terraform-workflow/` | A9 · The Terraform workflow |
| `a10-terraform-config/` | A10 · Terraform configuration |
| `a11-terraform-modules-state/` | A11 · Terraform modules and state |
| `a12-terraform-maintain-hcp/` | A12 · Maintaining infrastructure and HCP Terraform |
| `a13-ansible/` | A13 · Configuration management with Ansible |
| `a14-observability/` | A14 · Observability |

## Trouble?

| Message | What to do |
|---|---|
| `You are not logged in` | Run `synlearn login <code>` with a fresh code from the lesson page. |
| `Your lab login has expired` | Same as above. |
| `Could not reach SynLearn` | Check your connection and try again in a minute. |
| `SynLearn does not know that lab` | Check the lab id on the lesson page. |
