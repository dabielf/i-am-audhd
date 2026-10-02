# Agent guide: installing i-am-audhd

You are installing the `i-am-audhd` skill for the user. The skill is one file: `skills/i-am-audhd/SKILL.md`. Installing it means placing the `i-am-audhd` folder in the skills directory your runtime reads.

Only do what these steps say. Do not change any other configuration, and do not delete or edit the user's other skills.

## Steps

1. **Identify your runtime** and pick its skills directory:

   | Runtime | User-level (all projects) | Project-level (this project only) |
   | --- | --- | --- |
   | Claude Code | `~/.claude/skills/` | `.claude/skills/` |
   | Codex | `~/.agents/skills/` | `.agents/skills/` |

   If your runtime is not in the table and supports skills, use the skills directory from its documentation. If it does not support skills, go to "No skill support" below.

2. **Ask the user one question:** install for all projects (user-level, recommended) or for this project only? Wait for the answer.

3. **Check for an existing install.** If `<skills directory>/i-am-audhd` already exists, tell the user and ask whether to replace it. Do not overwrite it without a yes.

4. **Download and copy the skill folder:**

   ```bash
   git clone --depth 1 https://github.com/dabielf/i-am-audhd.git /tmp/i-am-audhd
   mkdir -p <skills directory>
   cp -r /tmp/i-am-audhd/skills/i-am-audhd <skills directory>/
   rm -rf /tmp/i-am-audhd
   ```

5. **Verify:** `<skills directory>/i-am-audhd/SKILL.md` exists and its first lines contain `name: i-am-audhd`.

6. **Tell the user**, in this order:
   1. Where the skill was installed (the full path).
   2. Start a new session, because skills are read when a session starts.
   3. In the new session, type `/i-am-audhd` to turn it on. The agent can also load it on its own when the user mentions AuDHD.
   4. Say "stop audhd mode" to turn it off.

## No skill support

If the runtime has no skills directory, tell the user that, and offer to paste the body of `SKILL.md` (everything after the frontmatter) into the runtime's custom instructions file. Do it only after the user says yes.

## Updating

To update an existing install, repeat steps 4 and 5. Tell the user the old version will be replaced, and wait for a yes first.
