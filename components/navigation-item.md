# Navigation/Item

## Status
- Version: `0.1.0`
- Status: `draft`
- Scope: `core`
- Confidence: `high`
- Figma component set: `19254:2595`

## Purpose
`Navigation/Item` renders Level 1 and Level 2 destinations inside Aurora Global Navigation.

## Public properties
- `Label` — TEXT
- `Icon` — INSTANCE_SWAP
- `Has children` — BOOLEAN
- `Level` — `1 | 2`
- `State` — `Default | Hover | Active | Focus | Disabled`

The source contains 10 approved Level × State variants.

## Dimensions
Common:
- `348 × 48`
- gap `12px`
- radius `8px`

Level 1:
- padding `12px 16px`

Level 2:
- padding `12px 16px 12px 32px`

Internal elements:
- leading icon frame `24 × 24`
- trailing chevron frame `20 × 20`
- label typography `14px / 20px`

## Anatomy
1. Leading icon
2. Label
3. Trailing chevron when `Has children=True`

## States
- Default: base state with no observed item-state fill.
- Hover: uses an Aurora-bound interaction background.
- Active: uses an Aurora-bound interaction background.
- Focus: observed with visible white bound stroke.
- Disabled: observed opacity approximately `0.48`.

Do not replace bound semantic variables with visually similar arbitrary colors.

## Observed icon mappings
- Visão geral → `Icon / Global navigation / Home` (`19226:87140`)
- Cadastros → `Icon / Global navigation / Registration` (`19227:87167`)
- Veículos → `Icon / Global navigation / Registration / Vehicles` (`19227:87273`)
- Motoristas → `Icon / Global navigation / Registration / Drivers` (`19227:87192`)
- Empresas → `Icon / Global navigation / Registration / Customers` (`19227:87187`)
- Relatórios gerais → `Icon / Global navigation / General Reports` (`19226:87123`)
- Monitoramento → `Icon / Global navigation / Monitoring` (`19227:565`)
- Risco → `Icon / Global navigation / Risk` (`19227:87283`)
- Telemetria → `Icon / Global navigation / Telemetry` (`19228:571`)
- Frota → observed component `19226:87108`
- Jornada → observed component `19226:87145`
- Configurações → observed component `19228:564`

The repository may not yet distribute the vector geometry for every mapped icon. A consumer must not replace unavailable assets with letters, emoji or unrelated icons. It must report the missing asset dependency.

## Hierarchy
Level 1 uses the standard 16px horizontal inset. Level 2 increases the left inset to 32px. This indentation is part of the component itself.

The current source supports Level 1 and Level 2 only; no Level 3+ may be inferred.

## AI fidelity rules
An AI must select an approved Level × State combination, preserve the measured geometry, reuse approved Aurora Global Navigation icon components, and preserve hierarchy indentation.

It must not invent states, hierarchy levels, icon mappings or visual substitutes. Missing evidence is a blocking dependency, not permission to approximate.