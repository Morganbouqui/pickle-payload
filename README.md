# Pickle Payload

A small, standard-library-only helper for **authorized Python Pickle deserialization testing**.

## Features

- Generate a harmless Pickle object and Base64-encode it.
- Generate a low-impact command-execution proof (default: `id`) for an already-authorized deserialization test.
- Inspect Base64/Pickle payloads with `pickletools.dis()` **without calling `pickle.loads()`**.
- Decode the Base64 layer and preview bytes.
- SHA-256 fingerprint generated/inspected payloads without creating evidence files.

## Run

```bash
chmod +x pickle-payload
./pickle-payload
```

The menu is:

```text
=== PICKLE PAYLOAD ===

[1] Generate harmless Pickle
[2] Generate benign execution proof
[3] Inspect Base64/Pickle payload
[4] Decode Base64 layer
[5] Pickle safety info
[0] Exit
```

## Safety

Python Pickle is unsafe for untrusted input. Do not use `pickle.loads()` merely to inspect an unknown payload. This utility uses `pickletools` for inspection and does not automatically send payloads to targets.

Use execution-proof payloads only on systems you own or are explicitly authorized to test.
