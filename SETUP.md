# GitHub Profile Setup

Use these files in the public `meganathank-dev/meganathank-dev` profile repository.

## 1. Copy the files

Copy the package contents without changing their paths:

```text
meganathank-dev/
├── README.md
└── .github/
    └── workflows/
        ├── profile-summary-cards.yml
        └── snake.yml
```

Commit and push the files to the `main` branch.

## 2. Add the summary-card token

The profile cards use an authenticated GitHub request so they do not depend on a shared, rate-limited public statistics endpoint.

1. Open GitHub **Settings → Developer settings → Personal access tokens → Fine-grained tokens**.
2. Create a token with an expiration date.
3. Give it read-only access to your public repositories. Private-repository access is unnecessary for this profile.
4. Open the `meganathank-dev/meganathank-dev` repository.
5. Go to **Settings → Secrets and variables → Actions → New repository secret**.
6. Name the secret exactly `SUMMARY_GITHUB_TOKEN` and paste the token value.

Never paste the token inside `README.md` or a workflow file.

## 3. Confirm workflow permissions

Open the profile repository's **Settings → Actions → General → Workflow permissions**. Enable **Read and write permissions**, then save.

## 4. Generate the assets

Open the repository's **Actions** tab and manually run these workflows once:

1. **Refresh GitHub profile cards**
2. **Generate contribution snake**

The summary workflow stores animated cards under `profile-summary-card-output/github_dark/` on `main`. The snake workflow publishes its SVG files to the `output` branch. Both workflows refresh automatically every day.

The activity graphics may take a few minutes to appear after the first successful workflow runs because raw GitHub files can be cached.
