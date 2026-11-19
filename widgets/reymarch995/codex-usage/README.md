# Codex usage

Shows the remaining 5-hour and weekly limits for your signed-in Codex account,
with reset times in the device's time zone.

The widget checks every minute. Tap the tile to fetch the current limits right
away. It shows **Refreshing…** during the request and displays the time of the
last successful check afterward. If a check fails, it keeps the last readings
for the current widget session and shows **Refresh failed**.

## Requirements

Install and sign in to a Codex CLI version that supports
`account/rateLimits/read`. The widget finds `codex` on `PATH` or in the
launcher's standard mise installation. Bash, jq, and GNU coreutils are
declared as Arch packages.

## How it gets the data

Each check starts a short-lived Codex app server over standard input and output
and requests the account rate limits. The CLI uses its existing sign-in to
contact the Codex service. The widget uses the returned usage percentages and
reset timestamps to display the two windows.
