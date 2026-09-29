# Sidewalk
The idea is a protocol people can tell AI to build a chat app around that talks directly to each others computer.  No data stored on someone elses server.  And you (AI) built the app so you don't have to worry about hidden code.  You also can create your own UI.


## 11. Prompt you can give an AI to build a client

Copy this:

```text
Build a desktop/CLI chat client that implements DirectPeer Protocol (DPP) v0.1 exactly as specified below.

Requirements:
- Language: English
- UI: GUI
- Generate Ed25519 identity + X25519 static key on first run, persist locally
- Print my address as dpp:1:<ed25519-hex>
- Command to add a peer by dpp: address and optional host:port
- Listen on TCP port 4747
- Connect outbound to host:port
- Noise_XX_25519_ChaChaPoly_SHA256 handshake
- Verify remote Ed25519 Peer ID before accepting chat
- After handshake, use frames: uint32 BE length | uint8 type | payload
- Implement JSON messages: hello, msg, typing, ack
- No intermediate server. Do not store messages anywhere except locally.
- If the peer is offline, do not queue to a server. Show "peer offline".
- Keep the crypto and framing in a clear module so another client can interoperate.

Follow this spec:
https://github.com/bstegman/Sidewalk/blob/main/spec-v1.txt
