# Changelog
Todas as mudanças importantes deste projeto serão documentadas neste arquivo.


## v1.7.0 - 2026-07-31


### Outras alterações

#### Polish README formatting and links

Refactor README.md and README.bbcode: convert headings to Markdown-style, replace BBCode spoiler/list with a clean numbered list, update Ko‑Fi/Nexus/GitHub links to point to the repo root, and reorganize several sections for clarity. Includes minor wording and formatting tweaks.

Co-authored-by: Copilot <223556219+Copilot@users.noreply.github.com>


#### Bump to Final Version

Mod Finalizado, apos essa nenhuma alteração será incrementada, apenas correções caso necessario


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/More-Gifts-from-Friends-Compilation


#### Exclude manifest.json from changelog

Add manifest.json to the exclusion list in .github/workflows/changelog.yml so manifest updates don't generate changelog noise. Keeps changelog output focused on meaningful changes (scripts, docs, release files, etc.).


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/More-Gifts-from-Friends-Compilation


#### Add --autostash to git pull in workflow

Update .github/workflows/sync-readme-bbcode.yml: change `git pull --rebase origin main` to `git pull --rebase --autostash origin main`. This ensures local modifications are stashed/unstashed automatically during the rebase, preventing failures when the working directory has uncommitted changes and improving the reliability of the sync/commit step.


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/More-Gifts-from-Friends-Compilation


#### persist credentials and enable autostash

└─ In .github/workflows/changelog.yml enable actions/checkout persist-credentials so the workflow can push/commit changes, and update git pull to use --rebase --autostash to automatically stash local changes before rebasing. These changes make the changelog job more robust when committing generated updates.


#### Include manifest.json in changelog workflow

Remove manifest.json from the exclude list in .github/workflows/changelog.yml so the file will be considered when generating release notes/assets. This change ensures manifest.json is included alongside other files during changelog/release processing.


#### Exclude manifest.json in changelog workflow

Add manifest.json to the exclusion list in .github/workflows/changelog.yml so changelog generation ignores changes to manifest.json and avoids noisy entries in release notes.


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/More-Gifts-from-Friends-Compilation


#### Pull remote before auto-commit in workflows

Update two GitHub Actions workflows to reduce commit conflicts: add a 'git pull --rebase origin main' step before the auto-commit in .github/workflows/changelog.yml and conditionally in .github/workflows/sync-readme-bbcode.yml. Also add a concurrency group (main-branch-auto-commit, cancel-in-progress: false) to the sync-readme-bbcode workflow to serialize runs.


#### Add 'Gifts from Jodi' pack and CI/readme sync

Adds a new "Gifts from Jodi" content pack (manifest, mail.json and extensive i18n translations). Updates README to include Jodi (v1.0.1) and bumps Grandpas to v0.2.0. Introduces CI workflows: changelog generation (git-cliff) and README <-> BBCode synchronization, plus scripts/md_bbcode_sync.py. Also adds cliff.toml, .gitattributes, and a top-level manifest.json for the compilation.


#### Add grandfather skill letters and mail entries

Add skill-specific grandfather letter mail entries (Farming, Mining, Foraging, Fishing, Combat for levels 1 and 10) with attachments and SkillConditions. Add corresponding i18n placeholders to default and pt-BR translation files, update README 'Updates' section, and bump manifest version to 0.2.0.


#### Add GitHub source link to README

Update README.md to include a note and link pointing to the mod's GitHub releases page so users can find the source code. This is a small documentation addition to make the repository location more visible.


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Add 'Gifts from Grandpa's' mod and remove root files

Move i18n and mail.json into a new '[MFM] Gifts from Grandpa's' folder and add its manifest (Version 0.1.0, MinimumApiVersion 4.0.0, ContentPackFor DIGUS.MailFrameworkMod MinimumVersion 1.20.0). Remove top-level files: manifest.json, LICENSE, cliff.toml, CHANGELOG.md, and .github/workflows/changelog.yml. This reorganizes the Grandpa mod into its own content pack and cleans up root metadata/workflow files.


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Standardize manifest files and update API requirements

Update all mod manifest files to follow a consistent structure with:
- Simplified, consistent mod names (removed descriptive subtitles)
- Updated MinimumApiVersion to 4.1.0 across all mods
- Standardized ContentPackFor with MinimumVersion 1.20.0 for MailFrameworkMod
- Removed deprecated Dependencies sections
- Simplified and refined Description fields
- Updated README with complete character names and version numbers
- Removed unnecessary presentes.txt file from Krobus mod


#### Add Gifts from Friends mods for multiple NPCs

Add complete mod content packages for 11 NPCs (Emily, Lewis, Pam, Clint, Demetrius, George, Gus, Jas, Krobus, Vincent, and Willy). Each package includes mail.json configurations, i18n translations across 15+ languages, and manifest.json metadata. These mods provide progressive gift rewards based on friendship levels.


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Add Mail Framework Mod content packs

Add three new Mail Framework Mod content packs providing progressive, friendship-based gifts and letters from Abigail, Alex, and Haley. Each pack includes 10 friendship levels with themed gifts, attachments, and localized messages in 15-16 languages.


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Add 'Gifts from Elliott' and 'Gifts from Sam' mail packs

Introduce two Mail Framework content packs: Gifts from Elliott and Gifts from Sam. Adds manifests, mail.json definitions (IDs, attachments, friendship conditions, mail chains) and extensive i18n localization files (default plus cs,de,es,fr,hu,it,ja,ko,nl,pl,pt,ru,tr,uk,zh) for both packs to provide localized mail text and attachments.


#### Rename mod folders and add Shane gifts mod

Standardize mod folder naming from '[MFM] {Name} Gifts' to '[MFM] Gifts from {Name}'. Add new 'Gifts from Shane' mod with multilingual support. Update manifest versions to semantic versioning (1.0 → 1.0.0) and increase MinimumApiVersion for Pierre, Robin, and Wizard mods. Normalize line endings in JSON files. Add root manifest.json for compilation support.


#### Add title for More Gifts From Friends Compilation


#### Enhance changelog workflow with versioning and release

Updated workflow to read version from manifest and create a tag if the version changes. Added steps for generating release notes and creating a GitHub release with a zip package.


#### Update commit sorting and parser configurations

Changed sort_commits from 'oldest' to 'newest' and updated commit_parsers to include a release group while removing style and build groups.


#### Add files via upload


#### Move changelog workflow to .github/workflows

Relocate changelog.yml to the standard .github/workflows directory where GitHub Actions workflows should be stored.


#### Add GitHub Action to update CHANGELOG.md


#### Add changelog configuration in cliff.toml


#### V 1.0.0 do mod Gifts from Sandy adicionada

Todas as modificações e alterações foram salvas no repositório principal esta é somente uma copia para integrar a compilação.


#### Initial commit



### ✨ Novidades

#### Gifts from Your Beloved

└─ Mod adicionado a compilação


#### Linus Updated

└─ Adicionado atualização do mod


#### Pierre Updated

└─ Atualizado mod do pierre


#### Update no mod da Robin

└─ Atualizado para a ultima versão do nexus


#### Updated Wizard mod

└─ Mod do mago atualizado com a versão mais recente disponivel no nexus


#### Gifts from Caroline updated

└─ Add localization files for Gifts from Caroline (de, es, fr, hu, it, ja, ko, ru, tr, zh). Update manifest: bump Version to 1.2.0, set MinimumApiVersion to "4.0.0", and refine Description to reference Caroline specifically. UniqueID, UpdateKeys and ContentPackFor remain unchanged.


#### Updated Leah mod

└─ Atualizei o mod da Leah com a versão nova


#### Updated Marlon mod

└─ Atualizei o mod do marlon com a versão mais recente disponivel no Nexus


#### Marnie Gifts Added

└─ New mod added Gifts from Marnie - Cozy Farm Gifts and Animal Care


#### Translations added

└─ Tcheco, Alemão, Espanhol, Frances, Hungaro, Italiano, Japones, Holandes, Polones, Portugues Europeu, Russo, Tailandes, Turco, Ucraniano, Vietnamita e Chines Simplificado


#### English

└─ Translation added


#### Cartas em Portugues

└─ Todas as cartas da versão atual do mod v0.2.0 adicionadas


#### Presentes adicionados

└─ Presentes para os niveis maximos das habilidades selecionados e adicionados


#### Add grandfather letter mail content and translations

└─ Add mail configuration and internationalization files for the grandfather's gift letter. Includes English and Brazilian Portuguese translations, along with mail attachments (chest and mixed seeds) for the gift system.



### 🏗 Versão

#### v1.7.0

└─ Nova versão do mod lançada com atualização do mod Gifts from Grandpa's e o mod Gifts from Jodi adidionado


#### Bump version to 1.6.0

└─ Update manifest version and fix indentation in mail.json attachment array.



### 🐛 Correções

#### Correção de avisos no codigo

└─ Pequenos ajustes para evitar problemas futuros


#### Correção de letra

└─ Correção menor de letra para padronização


#### changelog workflow excludes

└─ Adjust excluded paths in .github/workflows/changelog.yml: change ".gitattributes/*" to ".gitattributes" to match the file (not a directory), and replace "CHANGELOG.bbcode" with "README.bbcode" to exclude the correct file when generating changelogs.


#### Add Gifts from Grandpas mod support

└─ Rename the Grandpa's mod directory to Grandpas (non-possessive naming), update README with the new compilation entry, restructure mail.json to array format, and remove empty UpdateKeys from manifest.json.


#### Use git-cliff action in changelog workflow

└─ Replace inline git cliff command with orhun/git-cliff-action@v4. This improves maintainability by externalizing configuration to cliff.toml and using environment variables for output specification instead of CLI flags.



### 📚 Documentação

#### atualiza CHANGELOG.md [skip ci]


#### README.bbcode Atualizado

└─ Documento atualizado com a descrição mais recente para o mod no nexus


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### Readme Atualizado

└─ Notas da versão 1.7.0 adicionada ao arquivo


#### Update no README

└─ Ajustes de tamanho nos titulos


#### atualiza CHANGELOG.md [skip ci]


#### Convert mod list to BBCode format

└─ Update the mod list in README to use BBCode list formatting ([list=1] and [*]) for better compatibility with forum display. Preserves all content while improving formatting for the target platform.


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### Expand README with English description & features

└─ Rewrote and expanded README.md: added an English project description, features list, installation/update/compatibility notes, and compatibility warnings. Reformatted and updated the mod list with current versions, added NexusMods and Ko‑Fi links, and clarified what the compilation contains. Improves readability and guidance for installation and updates.


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]



### 🔧 Manutenção

#### sincroniza README.md <-> README.bbcode [skip ci]


#### sincroniza README.md <-> README.bbcode [skip ci]


#### Add GitHub as update source

└─ Added GitHub as an update source for the mod while maintaining the existing Nexus update key. This allows users to receive updates directly from the GitHub repository.





## Unreleased


### Outras alterações

#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Update Kent release metadata

This commit bumps the Kent mod manifest to version 1.0.1 and adds the Kent entry to the README changelog so the release is documented alongside the other gifts compilation entries.


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Merge branch 'main' of https://github.com/Mods-Stardew-Valley/Gifts-from-Friends-Compilation


#### Update no Mod da Caroline

corrihidas as chaves erradas em varios idiomas e adicionados novos idiomas, melhorado codigo interno no mail.json para cartas em cadeia uma por dia



### ⚡ Desempenho

#### Melhorias de Desempenho

└─ Remoção de avisos e melhorias pequenas no desempenho da compilação

Revisão para erros de chave de tradução concluida

Adicionar mais um mod e lancar a versão 1.8.0 incluindo as correções ja feitas


#### Updates

└─ Muitas atualizações de performance em varios arquivos


#### Implementado "GroupId"



### ✨ Novidades

#### Added Kent mod

└─ Adicionado o mod do Kent a compilação



### 🐛 Correções

#### gift

└─ Corrigido o nome correto do item para o presente da carta 9



### 📚 Documentação

#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### Update Readme

└─ Atualizada versão do mod da Caroline no documento


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]


#### atualiza CHANGELOG.md [skip ci]



### 🔧 Manutenção

#### sincroniza README.md <-> README.bbcode [skip ci]


#### sincroniza README.md <-> README.bbcode [skip ci]




