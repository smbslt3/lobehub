# GPT Image 2.6 GIF with an explicit size

The isolated self-hosted Web build ran PR commit `5fa0541a7538fc4a3e27b27fd8a0016daedee8f9` in production SPA mode. In the Image page I chose Flare, switched to Animated GIF, and selected the listed **1024 × 1024** tile from Auto.

The saved batch retained `size: "1024x1024"` and completed successfully. The single captured Images request carried `output_format: "gif"`, `frame_count: 9`, and `frame_duration_ms: 200`. Its JSON had no `size` field.

The loopback Images fixture replayed the unchanged result of a real OpenAI GIF generation performed on a self-hosted build on November 11. The saved asset served as `image/gif` and its SHA-256 matched the fixture. The GIF decodes to a 512 × 512 canvas and nine distinct 200 ms frames with infinite looping. This run verifies the exact PR's picker, request serialization, and asset persistence using the prerecorded provider response.

- [Selected standard picker](standard-picker.png)
- [Saved animated GIF](stored.gif)

```text
SHA-256 6b0255770f5746d4310078cb28cf1e29917580e5821e075b65a488fedfd0bb07
```
