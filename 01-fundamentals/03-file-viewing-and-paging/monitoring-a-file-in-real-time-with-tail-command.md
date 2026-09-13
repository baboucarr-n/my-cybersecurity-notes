# Monitoring File Changes in Real-Time (tail -f)

One of the functions of tail is to monitor files in real time -- useful for watching log files as they get written to. The -f option (stands for "follow") does this.

```
tail -f theFileName
```
After running this, you see the last 10 lines, then any new lines get added live as they come in.

To simulate new entries being added (open a second terminal for this):
```
echo "$(date) [INFO] New log entry for testing" >> theFileName
```
$(date) runs the date command and drops the actual current date/time into the string.

You'll see the new entry show up in the terminal where tail -f is still running. This is genuinely useful for tracking system events as they happen live.

To exit, press Ctrl+C -- sends an interrupt signal that stops the tail process.

## Doing This Across Two Terminals

Open one terminal, cd into where the file is. Open a second terminal and run:
```
tail -f theFileName
```
Now anything written to the file from the first terminal shows up live in the second one.

## Why -f Matters

- **Real-time observation** -- new lines appear on screen the moment they're written
- **Debugging** -- the standard tool for watching logs (system.log, access.log) while testing a site or troubleshooting a server
- **Continuous stream** -- keeps running until you stop it manually with Ctrl+C