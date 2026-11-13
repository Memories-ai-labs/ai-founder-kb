# Title: llama.cpp v1.0.0: A Stronger Foundation for the Local AI Ecosystem
# URL: https://huggingface.co/blog/ggml-org/llama-cpp-v1
# Date: 2026-11-13
# Source: Hugging Face Blog

llama.cpp and ggml both reach v1.0.0 after 3.5 years of development. The project has grown substantially and many downstream applications now depend on it.

## Key Points

**Versioning policy:** Both projects will use semantic versioning. Major-version bumps signal breaking changes to the public C API and ABI. Minor versions cover backward-compatible features, backend updates, model support, and API additions. Patch versions cover bug fixes.

**Libraries:**
- `libllama` (llama.cpp, LLM inference in C/C++) 
- `libggml` (a tensor library for machine learning)
Each has public headers in its `include/` directory.

**Distribution channels:** Pre-release artifacts for Linux, macOS, Windows, Android, and iOS, plus Docker, Debian, Homebrew, conda-forge, MacPorts, Winget, and XCFramework for Apple platforms.

**Backend and model coverage:** ggml runs on a wide range of hardware through dedicated backends, loadable as dynamic libraries at runtime. llama.cpp supports 150+ model architecture variants and mainstream speculative decoding methods.

**Development and CI:** The team uses LLMs in its development workflow. CI runs on Hugging Face Buckets and Jobs, with self-hosted runners supported by NVIDIA, AMD, Qualcomm, Arm, IBM, and Intel hardware.

**Authors:** Daniel Bevenius, Georgi Gerganov, and merve (ggml-org)
