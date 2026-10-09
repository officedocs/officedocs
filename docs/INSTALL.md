# OfficeDocs — online single-node installation

Use a dedicated server matching the selected CPU architecture. The initial OfficeDocs distribution uses the approved ShimoDocs packages unchanged; installer screens and package names may keep the original product name.

The commands below show **amd64**. For **arm64**, use `mdp-installer-arm64-v1.8.1-rc12-global` in place of `mdp-installer-amd64-v1.8.1-rc12-global`. Both architecture-specific packaged guides specify Ubuntu 24.04 LTS and the same evaluation resources below. Do not rename or modify the product archive.

## Download and verify

Choose your architecture at [officedocs.io/download](https://officedocs.io/download), compare the ZIP checksum with [SHA256SUMS](../SHA256SUMS), and extract it. On Linux, run `sha256sum <downloaded-zip>`; on macOS, run `shasum -a 256 <downloaded-zip>`. Compare the full value before running the installer.

## What's in this package

| File | Purpose |
| --- | --- |
| `mdp-installer-amd64-v1.8.1-rc12-global` | The installer binary. Match it to the server CPU architecture. |
| `co1.8.20260830.3884-drive-release-k3s.tar.gz` | The Office Suite release package. Uploaded later in the web UI. |

## Requirements

- **OS / arch**: Ubuntu 24.04 LTS (minimal install), CPU architecture **amd64** or **arm64** — must match the downloaded package.
- **Spec**: 16 Core / 32 GB RAM / 100 GB SSD.
- **Access**: root SSH login (or a user with deployment privileges).
- **Ports**: 22 (SSH), 18080 (installer web UI), 80 & 443 (service access) must be free.
- **Network**: the server must reach the internet (online install downloads packages and images).
- Do **not** pre-install Docker / Kubernetes on the server (it interferes with the installer's checks).
- Do **not** put `/root`, `/var`, or `/tmp` on separate partitions.

## Install steps

**1. Copy the installer to the node**

```bash
scp mdp-installer-amd64-v1.8.1-rc12-global root@<NODE_IP>:/root/
```

**2. Log in and enter the directory**

```bash
ssh root@<NODE_IP>
cd /root
```

**3. Make the installer executable**

```bash
chmod +x ./mdp-installer-amd64-v1.8.1-rc12-global
```

**4. Start the web installer**

```bash
./mdp-installer-amd64-v1.8.1-rc12-global server
```

To keep it running after the terminal closes:

```bash
nohup ./mdp-installer-amd64-v1.8.1-rc12-global server > nohup.out 2>&1 &
cat nohup.out   # view the installer output / addresses
```

On success the terminal prints a **Local** and a **Network** address.

**5. Open the web UI**

Open the **Network** address in a browser, e.g. `http://<NODE_IP>:18080/`.
Keep the installer process running throughout the installation.

**6. Deploy in the web UI**

1. Click **Start Deploy** and upload the release package `co1.8.20260830.3884-drive-release-k3s.tar.gz`; wait for validation to pass.
2. Confirm the access domain / IP (a real reachable address — **not** `127.0.0.1`).
3. Choose **All-in-One single node** mode.
4. Fill in the node SSH details (IP, user `root`, port `22`, password or private key) and click **Verify**.
5. Set the **data directory** (enough disk space, read/write permission). For online install, keep the
   offline-repo and third-party-middleware defaults.
6. Run the **environment check**. Fix any **Failed** items and rescan; confirm warnings; then **Continue**.
7. Confirm the plan and **Start Deploy**. Deployment time depends on network and server conditions. Do **not** close the installer,
   reboot the node, or refresh/resubmit during installation.

**7. Save the delivery information**

When the page shows **installation complete**, record and secure:

- Office Suite: `http(s)://<domain>/`
- MDP Ops Platform: `http(s)://<domain>/mdp/`
- Initial account and temporary password — **change the password on first login**.

## Notes

- Verify the release package is intact and not corrupted by the transfer before uploading.
- If validation fails, re-check that the package is complete and matches the server CPU architecture.
- Handle SSH credentials and delivery info securely — do not share them in public docs, screenshots, or chats.

## Licence and acceptance

Request the applicable OfficeDocs licence from [support.global@shimo.im](mailto:support.global@shimo.im). The free perpetual plan supports up to five users. Follow the [licence-management guide](https://officedocs.io/docs/deployment/operations-platform/suite/license-management) for the installed version and protect licence files as credentials.

Before using real data, verify sign-in, two-person editing, save and reopen, permissions, and backup/restore in your environment. The published archive hashes verify file integrity; they do not certify that these runtime checks have been completed for your deployment.

The 100 GB figure above comes from the packaged online evaluation guide. Longer-term deployments need storage planning beyond this evaluation baseline; see [system requirements](https://officedocs.io/docs/deployment/system-requirements). Reading documentation and downloading the package require no marketing registration.
