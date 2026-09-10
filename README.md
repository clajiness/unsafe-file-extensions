# unsafe-file-extensions

Curated patterns for file extensions that are unsafe in automated download workflows.

## Purpose

This list is intended for unattended download and ingestion systems where the
presence of an executable, script, installer, disk image, or archive should
cause the entire download to be rejected.

The list is intentionally conservative.

Harmless ancillary files such as artwork, subtitles, checksums, metadata, and
text files are not included. A valid download should remain intact rather than
being partially downloaded or altered simply because it contains files that
are unnecessary to the consumer.

## Format

`blocklist.txt` contains one wildcard pattern per line.

Example:

```text
*.exe
*.ps1
*.lnk
```

## Philosophy

A match means the download should be considered unsafe or inappropriate for an
unattended ingestion workflow.

This does not imply that every file type listed here is inherently malicious.
Some formats, such as archives and disk images, are included because they
require additional processing or can conceal executable content.

## License

CC0 1.0 Universal
