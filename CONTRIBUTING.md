# Contributing to Conversational Health Care Agents

Thank you for your interest in contributing! This project is a multi-agent clinical decision-making simulation, and we welcome contributions across all areas.

## 🚀 Getting Started

1. **Fork & clone** the repository
2. **Copy** `.env.example` to `.env` and add your [Groq API key](https://console.groq.com/)
3. **Install** dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. **Run smoke tests** to verify your setup (no API key needed):
   ```bash
   python -m ER_MAP.test_smoke
   ```

## 📋 Areas for Contribution

### 🦠 Disease Database (`ER_MAP/envs/disease_db.py`)
- Add new diseases with complete entries: `DISEASES_DB`, `VITALS_DB`, `LAB_RESULTS_DB`, `SOAP_HISTORY_DB`
- Ensure clinical accuracy — each entry should include realistic vitals, labs, and history

### 🎭 Persona Diversity (`ER_MAP/envs/randomizer.py`)
- Add new patient/nurse persona axes (e.g., language barriers, cultural factors)
- Improve SOAP noise injection for higher difficulty tiers

### ⚖️ Reward Engineering (`ER_MAP/envs/triage_env.py`)
- Propose new reward components or refine existing weights
- Add anti-reward-hacking defenses

### 📊 Visualization (`ER_MAP/plotting.py`)
- Improve training dashboards
- Add new cross-phase comparison charts

## 🧪 Testing

Before submitting a PR, please ensure:

```bash
# Smoke tests pass (offline, no API key)
python -m ER_MAP.test_smoke

# Disease DB integrity check
python -c "from ER_MAP.envs.disease_db import *; assert len(DISEASES_DB)==50"
```

## 📝 Code Style

- **Docstrings**: Use triple-quoted docstrings for all public functions
- **Type hints**: Preferred but not required
- **Comments**: Preserve existing comments unless your change makes them obsolete

## 🔒 Security

- **Never commit API keys** — use `.env` files (already in `.gitignore`)
- **No hardcoded paths** — use relative paths or environment variables
- If you find a security issue, please open a private issue rather than a public one

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.
