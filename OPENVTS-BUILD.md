# OpenVTS Windows build

The custom LLM changes are in `openvts-custom-llm.patch`, against Warp revision `f4f9b8838f65b106cfafadc0f622f0c72d82beef` (the supplied source archive). The Windows workflow checks out exactly that revision, applies the patch, tests the adapter, compiles the GUI, packages an Inno Setup installer, and checks the installed executable.

Run **Build Open VTS Windows installer** in Actions. The job has a 30-minute hard timeout, including a 23-minute build limit. Successful runs provide an EXE installer, portable ZIP, and the complete patched source ZIP as artifacts. Until a successful run exists, the source is an unverified build candidate.

The default endpoint is `http://llm.openvts.io/v1/chat/completions` with `Qwen3.6-35B-A3B-GPTQ-Int4`, thinking enabled, temperature 0.1, and max_tokens 131000. No API token is stored in this repository. Launch the installed **Open VTS Terminal** shortcut and enter your token locally. Hosted Warp services are unavailable in this build. See the patched OPENVTS-README.md for the supported local chat and shell-tool scope.
