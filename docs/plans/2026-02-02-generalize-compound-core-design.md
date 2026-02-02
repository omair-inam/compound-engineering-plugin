# Design: Generalize compound-core Plugin

**Date:** 2026-02-02
**Status:** Approved
**Goal:** Remove Rails/Ruby-specific content and replace with framework-agnostic terms

## Context

The `compound-core` plugin contains extensive Rails/Ruby-specific references inherited from its origin as a Rails-focused tool. The target user base works with:
- Java/Spring Boot (backend microservices)
- Angular (frontend, production)
- Python (CLI tools)
- GCP/GKE primary, with AWS and Azure deployments

The plugin should use generic terminology that applies across technology stacks.

## Changes

### 1. Schema Updates (`skills/compound-docs/schema.yaml`)

| Current | New | Comment |
|---------|-----|---------|
| `rails_model` | `data_model` | ORM entities, domain models |
| `rails_controller` | `api_controller` | Request handlers |
| `rails_view` | `view_template` | UI templates |
| `service_object` | `service_object` | Unchanged (already generic) |
| `background_job` | `background_job` | Update comment only |
| `rails_version` field | Remove entirely | Not needed |
| `build_error` comment | `# Build/compilation errors` | Remove "Rails, bundle" |
| `missing_association` | `missing_relationship` | `# Incorrect ORM relationships` |
| `wrong_api` comment | `# Using deprecated/incorrect framework API` | |
| `dependency_update` comment | `# Fixed by updating dependency` | Remove "gem" |

### 2. Stale Reference Cleanup

Remove references to deleted agents/skills:

| File | References to Remove |
|------|---------------------|
| `commands/workflows/compound.md` | `kieran-rails-reviewer` (3 occurrences) |
| `agents/research/best-practices-researcher.md` | `dhh-rails-style`, `andrew-kane-gem-writer`, `dspy-ruby` |
| `commands/deepen-plan.md` | `dhh-rails-style` example |

### 3. Agent Updates

**`best-practices-researcher.md`**
- Remove: `Rails/Ruby → dhh-rails-style, andrew-kane-gem-writer, dspy-ruby`
- Add: Generic skill discovery pattern for Java/Spring, Python, Angular/React

**`framework-docs-researcher.md`**
- Remove: `bundle show <gem_name>`, `Gemfile.lock` references
- Add: Generic package manager examples (`mvn dependency:tree`, `pip show`, `npm list`)
- Add: Generic lock file references (pom.xml, requirements.txt, package-lock.json)

**`security-sentinel.md`**
- Remove: Rails-specific grep patterns and security checks
- Add: Generic web app security patterns (input validation, CSRF, object binding)

**`performance-oracle.md`**
- Remove: "Rails applications" and "ActiveRecord" references
- Add: Generic ORM optimization guidance (N+1 queries, eager loading)

**`bug-reproduction-validator.md`**
- Remove: "For Rails apps" qualifier
- Add: Generic application logging guidance

### 4. Skill Documentation Updates

**`skills/compound-docs/SKILL.md`**
- Remove "Rails version" from context gathering list
- Update examples to use generic component types

**`skills/compound-docs/references/yaml-schema.md`**
- Update component enum to new values
- Remove `rails_version` field documentation
- Update examples

**`skills/compound-docs/assets/resolution-template.md`**
- Change `ruby` code fence to generic `code` or context-appropriate language
- Remove "Rails Version" line from template

### 5. Command Updates

**`commands/deepen-plan.md`**
- Line 190/214: Change `rails-specific/` to `framework-specific/`
- Line 251-254: Update example from Rails/ActiveRecord to generic ORM

### 6. README Update

**`README.md`**
- Change example: "pagination in Rails APIs" → "pagination in REST APIs"

## Implementation Order

1. `schema.yaml` - Foundation for terminology
2. Stale reference cleanup in commands/agents
3. Agent content generalization
4. Skill documentation updates
5. README example update

## Success Criteria

- No references to Rails, Ruby, ActiveRecord, Sidekiq, bundle, gem, erb in plugin
- All component types use framework-agnostic names
- No references to deleted agents/skills (kieran-*, dhh-*, ankane-*, dspy-ruby)
- Examples use generic or multi-ecosystem patterns
