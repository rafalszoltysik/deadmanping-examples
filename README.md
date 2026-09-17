# DeadManPing examples

Code samples for cron and backup monitoring with DeadManPing (bash, Python, Node.js, cron patterns).

DeadManPing itself is archived. The hosted product is shut down. These scripts remain as reference for how pings and payload checks were meant to work with a self-hosted or historical instance.

Related app code: https://github.com/rafalszoltysik/DeadManPing

## Layout

- `bash/` - shell scripts
- `python/` - Python scripts
- `nodejs/` - Node.js scripts
- `cron/` - sample crontab entries
- `edge-cases/` - less common scenarios

Each language folder covers the same kinds of checks: missing jobs, empty backup files, file size validation, exit codes, and response body checks.

## Usage

1. Point the ping URL in a script at your own monitor endpoint (or a local DeadManPing instance).
2. Replace `YOUR_MONITOR_ID` (or the full ping URL) with your value.
3. Call the ping from inside the job script after the real work finishes, not only from the crontab line, so you can send result data (for example file size).

Example shape used by many scripts:

```bash
curl -fsS "https://YOUR_HOST/api/ping/YOUR_MONITOR_ID"
```

Exact flags and JSON payloads differ per script. Open the file you need and follow the comments there.

## License

If this repository has no LICENSE file, treat usage as unspecified until one is added. The DeadManPing application repo is MIT.
