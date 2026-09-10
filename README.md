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

## Usage

The blocklist is available as a raw text file:

```text
https://raw.githubusercontent.com/clajiness/unsafe-file-extensions/main/blocklist.txt
```

The file contains one wildcard pattern per line and can be consumed by applications
that support remotely hosted blocklists.

## License

CC0 1.0 Universal
