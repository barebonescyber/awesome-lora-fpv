# Contributing

Thanks for your interest in contributing to **Awesome LoRa Mesh & FPV Drones**!

This list is focused on **beginner-friendly**, **hands-on** resources for:
- LoRa mesh networking (Meshtastic, MeshCore, related tooling).
- FPV drones (RTF kits, DIY builds, 3D-printed frames, simulators, etc.).

Please follow these guidelines to keep the list high-quality and useful.

---

## How to Propose a Change

1. **Fork** the repository.
2. **Create a branch** for your change:
   ```bash
   git checkout -b my-new-resource
   ```
3. Edit the files (usually `README.md` only).
4. Run any local checks you use (e.g., Markdown lints, spellcheck).
5. **Commit** your changes with a clear message.
6. **Open a pull request** describing what you added/changed and why.

For small link additions you can also open an issue using the "Resource suggestion" template instead of a PR.

---

## What Makes a Good Resource?

A good resource should be:

- **Beginner-friendly**  
  - Clear, structured, avoids unnecessary jargon, or explains it.
- **Hands-on**  
  - Helps people actually build, configure, or fly something; or deploy and use LoRa meshes.
- **Up-to-date**  
  - Still relevant with current firmware, regulations, and hardware ecosystems.
- **Accessible**  
  - Free is preferred; paid content is acceptable if it's uniquely valuable and clearly marked.
- **Focused**  
  - Not just generic IoT or generic drone content unless it has strong LoRa/FPV relevance.

Low-effort link dumps, promotional pages, or content with thin technical value will be declined.

---

## Formatting Rules

Follow the style in the existing sections.

### General

- Keep items **sorted logically** within each section (usually by topic, not alphabetically at all costs).
- Use **one line per resource** in list form.
- Keep descriptions **concise** but informative (roughly 1 line, up to ~120 characters).
- End descriptions with a **period**.

### Links

- Use the following pattern:
  ```markdown
  - [Name of Resource](https://example.com) - Short description of what it offers.
  ```
- For GitHub repositories, prefer linking to the README:
  ```markdown
  - [Meshtastic Firmware](https://github.com/meshtastic/firmware#readme) - Firmware, releases, and docs.
  ```
- Avoid bare URLs without descriptions.
- Avoid URL shorteners.

### Tone

- Avoid marketing language and superlatives: no "best", "ultimate", "awesome", "must-have", etc.
- Be factual and neutral about what the resource provides.

---

## Sections and Scope

When you add a resource, choose the **most specific existing section**:

- **LoRa Mesh Networking / Meshtastic / MeshCore**  
  - Protocol docs, firmware, routing deep dives, network design.
- **LoRa Hardware / Antennas / Solar Repeaters**  
  - Boards, radios, antennas, and infrastructure builds.
- **LoRa Software & Tools**  
  - Flashers, CLIs, mapping tools, APIs, integrations.
- **FPV Drones / Kits / DIY / 3D Printed**  
  - Build guides, frame designs, tuning resources, simulators.
- **Communities & Videos**  
  - Forums, Discords, YouTube channels, curated video series.

If you think a **new section** is warranted:

1. Make sure it groups at least **2–3** existing or new resources.
2. Use a **short, descriptive** heading.
3. Add it to the `Contents` section in `README.md`.

---

## Duplicates and Replacements

- Don't add near-duplicates that cover exactly the same use case at the same level.
- It's fine to:
  - Add a **more up-to-date** or **better-maintained** alternative and leave both.
  - Propose removing outdated/unmaintained content, with a short justification in the PR.

---

## Code of Conduct

- Be respectful and constructive in issues and PR discussions.
- Assume good faith; suggest improvements rather than just rejecting.
- Harassment, personal attacks, and discriminatory behavior are not tolerated.

---

## License

By contributing, you agree that your contributions will be released under the same terms as this repository's **CC0 1.0 Universal** license.