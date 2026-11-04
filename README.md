# RenderDraw for Revit — beta

This download is an experimental, unsigned Windows installer. Normal-user installation, repair, removal, Revit loading, and platform sign-in have not yet been validated. The installer targets selected builds of full Revit 2025, 2026, and 2027; compatibility with those hosts is unverified. Revit LT is not supported.

**Security:** This candidate includes ImageSharp 3.1.12, affected by [GHSA-v76p-62qx-wwq2](https://github.com/SixLabors/ImageSharp/security/advisories/GHSA-v76p-62qx-wwq2). A specially crafted TIFF texture can trigger an out-of-bounds memory write. Avoid untrusted models and image assets; use an isolated test environment. ImageSharp 3.2.0 contains the vendor's fix, but this candidate has not been updated.

## Requirements

- Windows x64 and a separately installed, licensed copy of full Revit 2025, 2026, or 2027. The installer checks the host version; some builds fall outside its supported matrix.
- The matching .NET Windows Desktop runtime. The installer checks the installed host and runtime and does not install Revit or the runtime.
- A RenderDraw account with access to the intended workspace for online use.

## Install

1. Download `RenderDraw.Revit.msi` from this repository. Verify its SHA-256 against `SHA256SUMS.txt` using PowerShell: `Get-FileHash .\RenderDraw.Revit.msi -Algorithm SHA256`.
2. Close Revit. Run `RenderDraw.Revit.msi` as the Windows user who will use the extension. The installer is unsigned; follow your organization's software policy.
3. Start Revit and look for the RenderDraw ribbon. Successful installation and loading have not yet been verified in a real Revit host.

## Use

From the RenderDraw ribbon, open **Settings** to check the platform address, then choose **Send to RenderDraw**. Sign in through the system browser and select the intended workspace and 3D view. Review the capture and any reported missing assets before sending. Some appearance features remain unqualified; the pilot may offer **Send incomplete preview** where standard sending is unavailable.

## Uninstall and troubleshooting

Close Revit, then use Windows **Installed apps** to uninstall **RenderDraw for Revit** for the same Windows user. Installation and removal have not been verified on a real host; keep the original MSI available for repair. User captures and send history are outside the installer's managed files.

If setup refuses to proceed, check the Revit version, matching .NET Windows Desktop runtime, user account, and whether Revit is running. Conflicting existing RenderDraw add-in files can also stop setup. If the ribbon is missing or sign-in fails, record the exact Revit version and error and contact RenderDraw. Do not share credentials, private models, or logs containing sensitive information in a public issue.

## Third-party software

This installer includes Six Labors ImageSharp. See `THIRD-PARTY-NOTICES.md` for attribution and licensing information.
