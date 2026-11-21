# StreamUnhinged Pro: customer guide

This guide describes the app as it is built and tested today. Where something has not been tested, it says so.

## 1. Getting started

1. **Download.** In your Whop membership, open StreamUnhinged Pro › **Software** and download
   `StreamUnhingedPro-Setup.exe` (about 1 GB). Your licence key is shown on the same page. Sign in to Whop with the
   email you bought with; if you cannot see the membership, check your Whop orders or the order confirmation email.
2. **Install.** Run `StreamUnhingedPro-Setup.exe`.
   - **Windows SmartScreen warning:** the installer is not yet code-signed, so Windows may show "Windows protected
     your PC". Choose **More info › Run anyway**. Only do this for a file you downloaded from your Whop membership.
     Do not turn off SmartScreen or your antivirus.
   - Choose a folder (the default is your user Programs folder) and select **Install**. No administrator rights are
     needed.
   - Setup downloads the local AI model once (about 4.8 GB) and checks its exact size and fingerprint; a damaged or
     altered download is refused. If the connection drops, select **Install** again to resume.
   - It then installs everything the app needs: the video tools, the speech model, the narration voices and the
     local AI editor. You do not need Python, FFmpeg or a terminal. The download is deleted once the install
     succeeds.
   - Setup adds a Start menu shortcut and, if you leave the box ticked, a desktop shortcut.
3. **Activate.** Open StreamUnhinged Pro and enter the licence key from your Whop membership. One licence covers
   one PC.
   - **Offline use:** after a successful online check, Studio keeps working for up to 72 hours if it cannot reach
     the licence service (for example, your internet or our service is down). It checks again when it is back
     online. A cancelled or refunded membership stops working at the next online check.
4. **Import.** In Clip Studio, import a recording you own or have permission to edit. Confirm your rights and add a
   short reference, for example "My own stream".
5. **Generate.** Choose a style or type what you want, for example "Focus on the funniest moments, put my facecam
   above the gameplay". Studio shows which settings it changed and anything it cannot do.
6. **Review and export.** Open the clip in the Library and check the picture, sound and captions. Use **Refine clip**
   to trim, fix captions, adjust the framing or add AI narration. Approve the clip, then save the MP4 in the profile
   for your platform.

## 1a. How Studio finds and judges moments

- **Monitoring creators:** under Live monitoring, connect Twitch and list the channels to watch. While Studio is
  open, it watches their chat through Twitch's official connection and reports when they go live. When chat
  suddenly gets busier than that channel's own normal level, or fills with laughter, hype or shock reactions, Studio
  records a chat moment with the reason.
- **Turning moments into clips:**
  - Clip Finder lets you cut the 75 seconds around a moment from your own recording of the stream.
  - With **Automatic clipping** on, Studio does this for you once your recorder's file covers the moment, and queues
    an edit. It never downloads streams from Twitch.
- **Choosing highlights:**
  - The local AI editor reads the transcript. It keeps only moments a newcomer would understand, with a clear setup
    and a real payoff, and it rejects empty teasers such as "you won't believe what happened".
  - Each pick is scored for hook, context, payoff, pacing and novelty, and the Library shows why a moment was chosen.
  - Scores are editorial estimates, not predictions of views.
- **YouTube links:**
  - Clip Finder can search YouTube through our service once that is switched on (not at launch).
  - To make clips, import a copy you are allowed to edit; for example, download your own uploads from YouTube Studio.
  - Studio keeps the link as the source reference but does not download YouTube videos, because YouTube's terms do
    not allow it.

## 1b. What has to keep running

- Monitoring, automatic clipping and the production queue run while StreamUnhinged Pro is open. That includes when
  it is minimised to the system tray, but the PC must be on, awake and online.
- You can choose to start Studio with Windows in Settings.
- Closing Studio asks whether to keep working in the tray or quit. Quitting during an edit asks first.

## 1c. Which connections work today

| Connection | Status |
|---|---|
| Whop licence activation | Works with the StreamUnhinged Pro licence service. |
| Twitch monitoring and popular clips | Works: connect your Twitch account in Studio (Twitch's official device sign-in). |
| YouTube research in Clip Finder | Not switched on at launch. Clip Finder says "not available from the subscription service" until it is. |
| Posting to YouTube, TikTok, Instagram and Facebook | Not available yet. Studio prepares the post and you upload it. |
| Content Rewards campaigns | Import from public pages and guided submission; Studio never submits for you. |

## 2. System requirements

| | Minimum | Recommended | Tested configuration |
|---|---|---|---|
| Windows | 64-bit Windows 10 22H2 (build 19045) or Windows 11 (Setup checks this) | Windows 11 | Windows 10 Pro 22H2 |
| Processor | 64-bit, 4 cores | 6 or more cores, from 2019 or later | AMD Ryzen 5 5500 (6 cores) |
| Memory | 8 GB (not tested; the AI editor will be slow) | 16 GB | 16 GB |
| Graphics | None required; Windows' software encoder is used | NVIDIA (NVENC) or another card with a Windows hardware video encoder, for faster exports | NVIDIA GeForce RTX 2070 SUPER |
| Disk | 11 GB free during install (the 4.8 GB download plus 6 GB installed), then 6 GB, plus room for recordings and clips | An SSD | NVMe SSD |
| Internet | Needed to install, activate, and check the licence at least every 72 hours | Broadband for the 4.8 GB download | |
| Other | Microsoft Edge WebView2 (included with Windows 10 22H2 and Windows 11) | | |

- **Measured on the tested PC:**
  - Install: 75 s, including the 4.8 GB model download on a fast connection. Allow longer on slower connections
    (about 11 minutes at 60 Mbit/s).
  - Start-up: under 5 s.
  - Publishing copy from the local AI model: 22–26 s.
  - Narrated revision: 14–19 s.
- **Not measured:**
  - PCs with 8 GB of memory, no graphics card, or older processors. The local AI editor needs several gigabytes of
    memory, so 16 GB is recommended.
  - Very long recordings (up to 4 hours are accepted) in the installed app.

## 3. Privacy and your data

- **Your footage stays on your PC.** Transcription, highlight selection, framing, captions, narration and rendering
  all run locally. Recordings and clips are never uploaded by StreamUnhinged Pro.
- **Where your data lives:** `%LOCALAPPDATA%\StreamUnhingedPro\customer`. This holds your projects, clips, settings,
  growth plans, campaign records and the encrypted licence. Uninstalling the app leaves this folder in place.
- **What leaves your PC, and when:**
  - **Licence checks:** your licence key and an anonymous device identifier go to the StreamUnhinged Pro licence
    service when you activate and periodically afterwards.
  - **YouTube research (when you search):** your search words go to the StreamUnhinged Pro service, which asks
    YouTube's official API. You need no YouTube key.
  - **Twitch (only if you connect it):** the channels you choose are watched through Twitch's official API. Your
    Twitch sign-in stays on this PC, encrypted with Windows.
  - **Content Rewards (only when you import or browse campaigns):** Studio reads the public campaign page. It never
    signs in for you. StreamUnhinged Pro is not affiliated with or approved by Content Rewards.
  - **AI model download (only in builds that download the model):** Setup fetches the model file once and checks its
    fingerprint.
- **No tracking:** the app contains no advertising, analytics or telemetry code.
- **Support bundles:** you create these yourself in Settings › Diagnostics. Licence keys, tokens and API keys are
  removed before the file is saved, and it contains no video. You decide whether to send it.

## 4. Backup and recovery

- **To back up:** close StreamUnhinged Pro, then copy `%LOCALAPPDATA%\StreamUnhingedPro\customer` to another drive.
  It holds everything you made. Clip folders also keep a short copy of the footage under each clip, so you can still
  change their framing after restoring.
- **To restore:** install StreamUnhinged Pro, close it, and copy the folder back. Activate again if Windows was
  reinstalled; your licence allows a limited number of devices, and the owner can free a device slot.
- **If an update goes wrong:** the previous version is kept beside the installation (in a folder ending in
  `.previous`), and support can restore it for you. There is no rollback button in the app yet.
- **If the app is damaged:** run Setup again and point it at the same folder. It repairs the installation in place
  and keeps your projects.

## 5. Troubleshooting

| Problem | What to do |
|---|---|
| "The installed speech files are missing" or narration voices missing | Run Setup again on the same folder (repair). |
| "Windows protected your PC" when starting Setup | The installer is not yet code-signed. Choose More info › Run anyway, only for the file from your Whop membership. |
| The AI model download stops or fails | Select Install again; the download resumes. "Failed the integrity check" means the file was damaged in transit: select Install again. Check that the drive has 11 GB free. |
| Activation fails | Check your internet connection. If you changed PCs, ask support to free a device slot. |
| "Could not reach the license service" | Your internet or our service is unavailable. If this PC was activated online in the last 72 hours, Studio keeps working; otherwise try again shortly. |
| "This license is inactive" | Your Whop membership is cancelled, expired or refunded, or the key is used on another PC. Check your membership on Whop. |
| An edit fails | Open Settings › Diagnostics and run the full check. It explains each problem in plain words and what to do. |
| The app says the recording has no audio | Advanced editing needs speech. Choose Quick, or import a recording with sound. |
| Framing cannot be adjusted on an older clip | Clips made before footage was kept with each clip cannot be re-framed. Generate the clip again. |
| Uninstall | Use Windows Settings › Apps › StreamUnhinged Pro › Uninstall. Your projects are kept. |

## 5a. Getting help

- **Contact:** message StreamUnhinged Pro through Whop (open the StreamUnhinged Pro membership in your Whop account
  and use its support chat).
- **Include:** what you were doing, the exact message on screen, and your Windows version. If an edit failed,
  create a support bundle in Settings › Diagnostics and attach it. It contains no video and no licence key.
- **Never send** your licence key in a public place. Support never asks for your Whop password.
- **Moving to a new PC:** ask support to free your device slot, then activate on the new PC.
- **Licence notices** for the software included with StreamUnhinged Pro are in `THIRD_PARTY_NOTICES.txt` in the
  installation folder.

## 6. Frequently asked questions

- **Will my clips go viral or earn money?** Nobody can promise that. Studio picks moments with a clear setup and
  payoff and checks the technical quality. Earnings shown for campaigns are estimates until you record a real
  payment.
- **Can I clip anyone's stream?** Only footage you own or have permission to use. Studio asks for your rights
  reference on every edit, and campaign checks block footage a campaign does not allow.
- **Does Studio post to TikTok, YouTube or Instagram for me?** Not yet. Studio prepares the copy and the schedule,
  and you upload. Direct posting needs each platform's approval of our app.
- **Does it need a powerful PC?** No graphics card is required. A recent processor and 16 GB of memory give the best
  experience; see section 2.
- **Is the AI narration a real person?** No. It is a generated voice, and the clip says so on screen.
