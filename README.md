# age (HTML)

A single-file, offline tool to encrypt and decrypt files with a passphrase, in the standard [age](https://age-encryption.org) format.

- **One file**: `age.html`. Open it in a browser. No install, no server.
- **Offline by design**: a Content-Security-Policy (`connect-src 'none'`) blocks all network connections from the page.
- **Standard format**: files are compatible with the `age` command-line tool (`age -d file.age`).
- **Crypto**: bundled [typage](https://github.com/FiloSottile/typage) (`age-encryption` on npm, by Filippo Valsorda), scrypt passphrase mode.
- **Passphrases**: suggests 6-12 random words (about 80+ bits) or accepts your own (min. 10 characters).

## Use

1. Open `age.html` in a browser (ideally while offline).
2. Choose or drop a file. Files ending in `.age` switch to Decrypt automatically.
3. Encrypt: write the suggested words on paper, tick the box, download `<name>.age`.
4. Decrypt: type the passphrase, download the original file.

Files are held in memory; above about 1 GB use the `age` CLI instead.

## Verify the download

```
sha256sum -c SHA256SUMS
```

## Limitations

- Passphrase mode only (no public-key recipients in the UI).
- Destroying (securely deleting) files is only in the CLI version; browsers can't delete files.
- A lost passphrase cannot be recovered.

## License

MIT, see [LICENSE](LICENSE). Bundled typage and its dependencies (noble-hashes, noble-ciphers, noble-curves, scure-base) are MIT licensed.
