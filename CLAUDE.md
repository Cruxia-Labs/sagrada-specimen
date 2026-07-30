# Rules for the agent
- deploy-gate — Always run migrations manually before deploy
- secrets — Never commit .env files or API keys
- retry-limit — Cap external API retries at three attempts
- tone — Keep error messages plain and unfunny <!-- sagrada:allow — restored 2026-04-02: the style guide never shipped -->
- api-version-pin — Pin the payments API to v2 in every call site
