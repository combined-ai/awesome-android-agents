# Awesome Android Agents [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, frameworks, devices and research for AI agents that see and control Android: MCP servers, phone-agent frameworks, cloud devices, AI-driven app testing and Android's own agent APIs.

AI coding agents (Claude Code, Codex, Cursor, Gemini CLI) and autonomous assistants increasingly need to use a real Android screen: to test the app they just built, to use apps that have no API, or to run inside a product. This list collects what exists, as of November 2026, with a plain note on what each one is for.

Maintained by the [Phonebox](https://phonebox.dev) team, who build one of the cloud-device options below. Everything else is listed on its merits; corrections and additions are welcome.

## Contents

- [MCP servers](#mcp-servers)
- [Phone-agent frameworks](#phone-agent-frameworks)
- [Cloud devices for agents](#cloud-devices-for-agents)
- [AI-driven app testing](#ai-driven-app-testing)
- [Scripted frameworks agents work with](#scripted-frameworks-agents-work-with)
- [Android platform APIs for agents](#android-platform-apis-for-agents)
- [Benchmarks and research](#benchmarks-and-research)
- [Guides](#guides)

## MCP servers

Model Context Protocol servers that give an agent tools to read and act on an Android screen.

### Local (drive an emulator or USB device on your machine)

- [mobile-mcp](https://github.com/mobile-next/mobile-mcp) - Android and iOS, reads the accessibility tree with a screenshot fallback; logs, recording and location built in.
- [Appium MCP](https://github.com/appium/appium-mcp) - The Appium project's server; drives devices through Appium drivers and can generate Appium test code.
- [Maestro MCP](https://docs.maestro.dev/getting-started/maestro-mcp) - Built into the Maestro CLI (`maestro mcp`); inspects the view hierarchy and runs Maestro commands and flows.
- [agent-device](https://github.com/callstack/agent-device) - Callstack's CLI and MCP server for verifying React Native, Expo and native apps, with replayable sessions.
- [Patrol MCP](https://patrol.leancode.co/documentation/other/patrol-mcp) - Runs Patrol tests for Flutter apps and reads the native UI tree.
- [Android-MCP](https://github.com/CursorTouch/Android-MCP) - Lightweight Python server for Android 10+ over adb.
- [android-mcp-server](https://github.com/minhalvp/android-mcp-server) - Minimal Python adb bridge with a raw adb escape hatch.
- [android-remote-control-mcp](https://github.com/danielealbano/android-remote-control-mcp) - An Android app that is itself the MCP server, for controlling your own phone remotely.

### Hosted (the device comes with the server)

- [Phonebox](https://github.com/combined-ai/phonebox-android-mcp) - Hosted Android MCP server at `phonebox.dev/mcp` with cloud phones included; API key, phones keep their state when parked. Android only.
- [Mobilerun MCP](https://docs.mobilerun.ai/mcp-server) - Hosted MCP server for Mobilerun Cloud phones, with OAuth.
- [BrowserStack MCP](https://github.com/browserstack/mcp-server) - Local or hosted server for BrowserStack's device cloud: sessions, test runs and debugging.
- [Sauce Labs MCP](https://docs.saucelabs.com/sauce-ai/sauce-mcp/) - Hosted server for Sauce Labs; device control on private devices.
- [Kobiton MCP](https://docs.kobiton.com/ai/mcp/) - Hosted server for Kobiton's real-device cloud and test management.

## Phone-agent frameworks

Agents that run an observe-and-act loop on a phone.

- [Mobilerun](https://github.com/droidrun/mobilerun) - (formerly DroidRun) LLM agent framework for Android and iOS phones, with a hosted cloud.
- [mobile-use](https://github.com/minitap-ai/mobile-use) - Open-source agent that uses real Android and iOS apps.
- [AppAgent](https://github.com/TencentQQGYLab/AppAgent) - Tencent's multimodal agent that operates smartphone apps through taps and swipes.
- [Mobile-Agent](https://github.com/X-PLUG/MobileAgent) - Alibaba's family of GUI agents for mobile, PC and web.
- [Open-AutoGLM](https://github.com/zai-org/Open-AutoGLM) - Zhipu's open phone-agent model and framework.

## Cloud devices for agents

Places an agent can get an Android device without a local emulator.

- [Phonebox](https://phonebox.dev) - Cloud Android phones for AI agents over MCP, CLI, SDK and REST; billed per second, parked phones keep apps and sign-ins.
- [Mobilerun Cloud](https://mobilerun.ai) - Hosted phones for the Mobilerun agent framework.
- [Genymotion SaaS](https://www.genymotion.com/) - Virtual Android devices in the cloud, reachable over adb.
- [Appetize.io](https://appetize.io) - iOS and Android emulators streamed to the browser, with an API.
- [Google Developer Device Platform](https://cloud.google.com/products/developer-device-platform) - Google Cloud's device farm and device streaming, successor to Firebase Test Lab.
- [BrowserStack](https://www.browserstack.com/app-automate) - Real-device cloud for app testing.
- [AWS Device Farm](https://aws.amazon.com/device-farm/) - Real devices billed per device-minute.

## AI-driven app testing

Tools where an AI model decides the test steps.

- [Journeys for Android Studio](https://developer.android.com/studio/gemini/journeys) - Gemini runs plain-language test steps against your app (preview).
- [Firebase App Testing agent](https://firebase.google.com/docs/app-distribution/android/app-testing-agent) - Natural-language test cases for Android builds (preview).
- [testRigor](https://testrigor.com/) - Tests written in plain English for Android, iOS and web.
- [Momentic](https://momentic.ai/) - AI QA agent that tests from a prompt.
- [agent-qa](https://vostride.com) - FSL-1.1-ALv2-licensed natural-language QA for Android, iOS and web, with persistent memidex memory and validated self-improvement.
- [QA Wolf](https://www.qawolf.com/) - AI-assisted end-to-end test creation and maintenance as a service.
- [AskUI](https://www.askui.com/) - Vision-based agent that runs plain-language test cases on any screen.
- [Repeato](https://www.repeato.app/) - No-code, computer-vision test recorder for mobile.

## Scripted frameworks agents work with

The deterministic suites agents complement, or generate.

- [Espresso](https://developer.android.com/training/testing/espresso) - In-app UI tests for Android Views.
- [UI Automator](https://developer.android.com/training/testing/other-components/ui-automator) - Cross-app and system UI automation for Android.
- [Appium](https://appium.io/) - WebDriver-based automation for Android, iOS and more.
- [Maestro](https://github.com/mobile-dev-inc/Maestro) - YAML flows for end-to-end mobile tests.
- [Detox](https://github.com/wix/Detox) - Gray-box end-to-end testing for React Native.
- [Patrol](https://github.com/leancodepl/patrol) - Flutter end-to-end tests with native UI access.
- [Robolectric](https://github.com/robolectric/robolectric) - Android tests on the JVM, no emulator.

## Android platform APIs for agents

- [AppFunctions](https://developer.android.com/ai/appfunctions) - Apps expose functions that system agents call on the device (experimental, Android 16+).
- [Computer Control](https://developer.android.com/ai/computer-control) - UI automation for OEM-preloaded assistants (preview).
- [AccessibilityService](https://developer.android.com/guide/topics/ui/accessibility/service) - The API most UI-reading agents build on; note Google Play's [policy on autonomous use](https://support.google.com/googleplay/android-developer/answer/10964491).

## Benchmarks and research

- [AndroidWorld](https://github.com/google-research/android_world) - Google Research's benchmark environment for autonomous Android agents.
- [AppAgent: Multimodal Agents as Smartphone Users](https://arxiv.org/abs/2312.13771) - The AppAgent paper.
- [The Rise of Agentic Testing](https://arxiv.org/abs/2601.02454) - A closed-loop, multi-agent view of agentic software testing.

## Guides

- [The best Android MCP servers in 2026](https://phonebox.dev/guides/best-android-mcp-servers) - Twelve servers compared on setup, devices, iOS and how they read the screen.
- [How to give Claude Code an Android phone](https://phonebox.dev/guides/how-to-give-claude-code-an-android-phone) - ADB, an emulator, a local MCP server or a cloud phone, with commands.
- [How an AI agent can use Android apps that have no API](https://phonebox.dev/guides/android-automation-with-ai) - AppFunctions, Gemini, accessibility agents and cloud phones compared.
- [What is agentic testing?](https://phonebox.dev/guides/what-is-agentic-testing) - Agentic vs scripted vs AI-assisted testing for mobile teams.
- [Gemini multi-step tasks on Android](https://blog.google/innovation-and-ai/products/gemini-app/android-multi-step-tasks/) - Google's announcement of Gemini acting inside apps.

## Contributing

Pull requests are welcome. Add one item per PR, in the right section, as `- [Name](link) - What it is, in one plain sentence.` Open-source and commercial tools are both fine; say which if it isn't obvious. No affiliate links.

## License

[CC0 1.0](LICENSE): to the extent possible under law, the maintainers have waived all copyright to this list.
