# Security Policy

## Supported Versions

VideoX Compressor is currently in beta. The latest public beta release is the recommended version for testing and use.

| Version | Status |
|---|---|
| Latest beta release | Supported |
| Older beta releases | Limited support |
| Deprecated or removed releases | Not recommended |

## Reporting a Security Issue

Please do **not** publicly post sensitive security information in GitHub Issues.

For security-related reports, contact the maintainer:

```text
Telegram: @thelouis_mahdi
```

When reporting a security issue, include:

- VideoX version
- Windows version
- Short description of the issue
- Steps to reproduce if safe to share
- Screenshot if useful
- Relevant log excerpt with sensitive data removed

## Sensitive Information

Do not publicly share:

- `license.key`
- private Device ID
- private videos
- personal documents
- account passwords
- access tokens
- private emails or phone numbers
- full logs that contain private paths or personal information

If you need to share logs, review them first and remove private information.

## Official Builds

Only use release packages from the official GitHub repository or from the maintainer's official distribution channel.

Be careful with unofficial modified builds, repackaged ZIP files or unknown executables. They may contain unwanted changes or malware.

## FFmpeg and External Components

VideoX uses FFmpeg and FFprobe as the main media processing engine. Keep release packages complete and do not replace bundled FFmpeg files with unknown versions unless you know what you are doing.

Required folders should not be deleted:

```text
ffmpeg/
_internal/
```

## License Safety

Each `license.key` is device-specific. Do not publish it in GitHub Issues, screenshots, ZIP packages or public messages.

If a license file is accidentally shared publicly, contact the maintainer.

## Vulnerability Handling

The maintainer will review reports and may:

- request more details
- confirm or reject the issue
- release a fix
- update documentation
- remove affected files or releases if needed

Because this is a beta project, response times may vary.
