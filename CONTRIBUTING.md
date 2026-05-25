# Contributing to VideoX Compressor

Thank you for your interest in improving VideoX Compressor.

VideoX is currently a beta Windows video compression tool focused on recorded classes, tutorials, screen recordings, low-motion educational videos and practical hardware-accelerated compression.

## Before You Contribute

Please read:

- `README.md`
- `RELEASE_NOTES.md`
- `SECURITY.md`

This project may include closed-source application logic and release packages. Public contributions should focus on documentation, bug reports, usability feedback, test reports, packaging feedback and clearly described feature requests unless the maintainer opens a specific development task.

## Good Bug Reports

A good bug report should include:

- VideoX version
- Windows version
- CPU model
- GPU model or models
- GPU driver version
- Selected GPU Preference
- Output format
- Preset
- Performance Mode
- Processing Strategy
- Hardware Decode setting
- Whether General Safe Mode was enabled
- Steps to reproduce the problem
- Screenshot if useful
- Diagnostic log or exported bug report

Please remove sensitive information before posting logs.

Do not publicly post:

- `license.key`
- private Device ID
- personal files
- private videos
- personal account information

## Feature Requests

Feature requests are welcome when they are practical and related to the project goals.

Useful feature requests should explain:

- The problem you want to solve
- The expected behavior
- The type of video or system affected
- Why the feature would help normal users

## Pull Requests

Pull requests should be small, focused and easy to review.

Recommended PR rules:

- Use a clear title.
- Explain what changed and why.
- Keep unrelated changes separate.
- Update documentation when needed.
- Do not include private keys, license files, personal videos or large binary files.
- Do not include unofficial builds or modified executables unless requested by the maintainer.

## Testing Suggestions

When testing VideoX, try to include:

- Short video test
- Long video test
- Already-compressed video test
- Low-motion class or screen recording test
- Hardware path test if available:
  - NVIDIA NVENC
  - Intel QSV
  - AMD AMF
  - CPU Only

For hybrid GPU laptops, also test Windows Graphics Settings for:

```text
VideoX.exe
ffmpeg/modern/bin/ffmpeg.exe
ffmpeg/legacy-nvidia/bin/ffmpeg.exe
```

## Communication

For general contact:

```text
Telegram: @thelouis_mahdi
```

For bugs and feature requests, GitHub Issues are preferred when no private information is included.
