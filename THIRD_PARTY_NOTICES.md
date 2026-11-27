# Third-party notices

Deck's own code is under the [MIT licence](LICENSE). It ships or uses the following, each under its own licence.

| Component | Where | Licence | Source |
|---|---|---|---|
| PawnIO driver (`PawnIO.sys`, `.inf`, `.cat`), Microsoft-signed | `src-tauri/src/hw/mods/`, installed as a separate kernel service | GPL-2.0 | https://github.com/namazso/PawnIO |
| PawnIO modules (`LpcIO`, `IntelMSR`, `SmbusI801`, `AMDFamily17`) | `src-tauri/src/hw/mods/` | LGPL-2.1 | https://github.com/namazso/PawnIO.Modules |
| Fluent UI System Icons (profile icons) | `tools/icons/svg/`, `src-tauri/icons/profiles/` | MIT | https://github.com/microsoft/fluentui-system-icons |
| SDL 3.4.16 (`SDL3.dll`, official x64 build, gzipped) | `src-tauri/vendor/sdl3/`, embedded in `Deck.exe` and written next to it on first use | zlib | https://github.com/libsdl-org/SDL |
| Sora (display font) | `ui/fonts/Sora-var.woff2`; licence in `ui/fonts/OFL-Sora.txt` | SIL OFL-1.1 | https://github.com/sora-xor/sora-font |
| Manrope (text font) | `ui/fonts/Manrope-var.woff2`; licence in `ui/fonts/OFL-Manrope.txt` | SIL OFL-1.1 | https://github.com/googlefonts/manrope |
| Chakra Petch (WOFF2 and decoded TTF number face) | `ui/fonts/`, embedded in native battery art; licence in `ui/fonts/OFL-ChakraPetch.txt` | SIL OFL-1.1 | https://github.com/m4rc1e/Chakra-Petch |
| resvg / usvg / tiny-skia (the controller overlay's art) | linked into `Deck.exe` | MIT / Apache-2.0 | https://github.com/linebender/resvg |
| Win11Debloat by Raphire: tweak recipes (registry values, Windows build ranges), the built-in app list and its ratings, the empty Start layout (`start2.bin`) | `src-tauri/tweaks/` (made by `tools/tweaks/build.py` at a pinned commit) | MIT | https://github.com/Raphire/Win11Debloat |
| WinUtil by Chris Titus Tech: tweak recipes (registry values with their original values) | `src-tauri/tweaks/tweaks.json` (made by `tools/tweaks/build.py` at a pinned commit) | MIT | https://github.com/ChrisTitusTech/winutil |
| pull-microsoft-store by sht2017: the request flow for Microsoft's update service (FE3) used by Get Store apps | `src-tauri/src/tweaks/storedl.rs` (Deck's own Rust, same protocol) | MIT | https://github.com/sht2017/pull-microsoft-store |
| ClockContrast engine by the owner (colour engine, taskbar-corner capture and load watch, ported into Deck as a module; the Windhawk mod stays a separate program) | `src-tauri/src/clockcontrast/`, `src-tauri/fixtures/clockcontrast/` | MIT (same holder as Deck) | the owner's ClockContrast repo (local, no remote), commit 9bd5451 |
| Microsoft Root Certificate Authority 2011 and Microsoft ECC Product Root CA 2018 (public root certificates, the same Windows trusts) | `src-tauri/tweaks/certs/`, used only for Microsoft's update service | Public certificates | https://www.microsoft.com/pkiops/docs/repository.htm |
| ONNX Runtime 1.31 (`onnxruntime.dll`) | the optional OCR pack, downloaded only when turned on; never in the setup | MIT | https://github.com/microsoft/onnxruntime |
| PP-OCRv6 tiny models (`det.onnx`, `rec.onnx`, `keys.txt`), converted by RapidOCR | the optional OCR pack | Apache-2.0 | https://github.com/PaddlePaddle/PaddleOCR, https://github.com/RapidAI/RapidOCR |
| AutoEq by Jaakko Pasanen: headphone corrections (ParametricEQ.txt) for a few popular models, copied unchanged; licence in `src-tauri/autoeq/LICENSE` | `src-tauri/autoeq/profiles.txt`, embedded in `Deck.exe` | MIT | https://github.com/jaakkopasanen/AutoEq |
| cpal (audio devices and streams) | linked into `Deck.exe` | Apache-2.0 | https://github.com/RustAudio/cpal |
| nnnoiseless (Rust port of RNNoise, noise suppression) | linked into `Deck.exe`; notice below | BSD-3-Clause | https://github.com/jneem/nnnoiseless |
| rtrb (audio ring buffers) | linked into `Deck.exe` | MIT / Apache-2.0 | https://github.com/mgeier/rtrb |
| Symphonia (audio decoding, the `symphonia-*` crates) | unmodified crates used as a library, linked into `Deck.exe` | MPL-2.0 | https://github.com/pdeljanov/Symphonia |
| `cssparser`, `cssparser-macros`, `selectors`, `dtoa-short` (Tauri's HTML handling) and `option-ext` (folder lookup) | unmodified crates from `src-tauri/Cargo.lock`, linked into `Deck.exe` | MPL-2.0 | https://github.com/servo/rust-cssparser, https://github.com/servo/stylo, https://github.com/upsuper/dtoa-short, https://github.com/soc/option-ext |
| `webpki-roots` (Mozilla's list of root certificates, for HTTPS) | unmodified crate, linked into `Deck.exe` | CDLA-Permissive-2.0 | https://github.com/rustls/webpki-roots |
| crossbeam-channel (audio commands) | linked into `Deck.exe` | MIT / Apache-2.0 | https://github.com/crossbeam-rs/crossbeam |
| Tauri and the Rust crates in `src-tauri/Cargo.lock` | linked into `Deck.exe` | MIT / Apache-2.0 and others (see each crate) | https://crates.io |

The PawnIO driver and modules are unmodified copies of the upstream signed binaries; their source code is available at the links above. Deck talks to the driver only through its documented IOCTL interface.

Nothing from WinScript (GPL-3.0) is included; it was used as a list of ideas only. Nothing from HeadsetControl (GPL-3.0) is copied or linked: Deck's headset battery requests use the byte values its device files document, written in Deck's own code, and the headset capability table (`src-tauri/src/devbat/caps.rs`) records which features its README lists per headset family (facts only), and the headset controls (`src-tauri/src/devbat/headctl.rs`) send the sidetone, auto power-off and voice-prompt byte values its device files document, again in Deck's own code. VB-CABLE is never bundled: Deck downloads VB-Audio's own package unchanged and opens its setup.

RivaTuner Statistics Server, MSI Afterburner and NVIDIA's drivers are not included; Deck only talks to them when they are installed.

## nnnoiseless / RNNoise

The following notice is reproduced from nnnoiseless's `COPYING` file.

```text
Copyright (c) 2020, Joe Neeman
Copyright (c) 2017, Mozilla
Copyright (c) 2007-2017, Jean-Marc Valin
Copyright (c) 2005-2017, Xiph.Org Foundation
Copyright (c) 2003-2004, Mark Borgerding

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions
are met:

- Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.

- Redistributions in binary form must reproduce the above copyright
notice, this list of conditions and the following disclaimer in the
documentation and/or other materials provided with the distribution.

- Neither the name of the Xiph.Org Foundation nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
``AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED.  IN NO EVENT SHALL THE FOUNDATION
OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```
