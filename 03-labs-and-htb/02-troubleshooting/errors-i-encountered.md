# Problems I Encountered

*Date: Wednesday, 2 February 2026*

## Permission Denied and File Exists Errors

My Linux reminders from working through this:

1. **Create folders only in home (~)**
   - Good: `mkdir testDir` or `mkdir -p stuff/a/b/c`
   - Bad: anything starting with `/` → Permission denied

2. **If I see "Permission denied"** → I'm trying to write into root (/). Fix: `cd ~` first, or use `sudo` only when I actually mean it.

3. **If "File exists"** → the name's already taken. Fix: `ls -la` to check what's there, then `rmdir oldName` or just pick a new name.

4. **Always start with `cd ~`** → then I can experiment freely without permission errors or accidentally touching sudo.

### Why This Happened

"Permission denied" happened because I tried creating something directly in `/` (root). Normal users can't write there -- only root can. It's a built-in safety rule protecting the whole OS.

In one line each:
- "File exists" = name collision, something's already using that name
- "Permission denied" = trying to write into root without sudo

**Rule to remember:** stay in home (~), never start paths with `/` when creating your own stuff -- fixes about 95% of these errors.

### Absolute vs Relative Paths (why I kept looping on this)

- **Absolute path** -- starts with `/`. Always points to the exact same place from root. Root-owned directories have strict permissions, so a normal user gets **Permission denied** every time.
- **Relative path** -- doesn't start with `/`. Interpreted based on where you currently are. Inside home (~), you have full write access, so it just works.

I kept typing absolute paths even right after `cd ~`, so the system read it as "create this under root" -- instant denial. Switching to relative paths fixed it.

("File exists" is a separate, simpler issue -- just a name collision, nothing to do with permissions.)

## Handling Filenames with Spaces

*Date: 9 February 2026*

When reading a file that has spaces in its name, you can escape the spaces with a backslash:
```
cat file\ name\ with\ spaces
```
Or wrap the whole name in quotes instead:
```
cat "file name with spaces"
```
Both work, just different styles.

(source: linuxhandbook.com -- filename spaces in Linux)

## Trying to Copy a File That Doesn't Exist

*Date: 9 February 2026*

Tried to copy a file that didn't actually exist yet -- obviously failed. Fix was simple: create it first with `touch`, then copy it.