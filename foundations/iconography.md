# Iconography

Iconography defines how icons are sourced and consumed in Aurora.

## Source inventory

The approved Figma `Icons` page currently contains 1,500 component nodes. The inventory includes broad UI icon families such as layout/alignment, charts, security, education, code/development and many other interface concepts.

Aurora also contains a domain-specific public component set:

- `Icon / Map / Vehicle status`
- States: Stopped, Blocked, Movement, No transmission, Stopped and on, Total.

A separate `.Legacy / Status/CarStatus` set exists in the source and must remain classified as legacy rather than being promoted to Aurora core.

## Naming

Icon component names are semantic asset identifiers, for example:

- `align-left-01`
- `bar-chart-01`
- `lock-01`
- `shield-tick`
- `code-01`

AI and implementation consumers should reference approved icon names rather than inventing an icon that is not present in the manifest/source library.

## Usage principles

- Prefer an existing Aurora icon whenever a matching semantic asset exists.
- Treat icon color as contextual and bind it to the semantic foreground/text token required by the consuming component or pattern.
- Component-specific icon sizing, spacing and alignment remain governed by that component contract when already documented.
- Do not infer a universal icon size, stroke width, fill rule or optical alignment value unless it is explicitly documented from the source.
- Do not use iconography as the only carrier of critical meaning when the consuming pattern requires text or another accessible label.
- Domain-specific vehicle-status icons must preserve their approved status names.
- Legacy icon sets are not automatically approved for new Aurora compositions.

## Relationship to components

Icons are Foundation assets, while their application is contextual. Button, Input, Select, Dropdown, Filters, Breadcrumbs, Date Picker and other contracts may depend on icons and define how icons appear inside those components.

The Foundation therefore answers **which icon assets Aurora has and the general rules for consuming them**. Component and Pattern contracts answer **where and how they are used in a specific interface composition**.

## AI constraints

An AI consuming Aurora must:

1. Search the approved icon inventory before choosing an icon.
2. Use the existing semantic icon name when available.
3. Follow the consuming component's icon constraints.
4. Use semantic color tokens instead of hard-coded icon colors when the component contract provides them.
5. Never promote `.Legacy` assets to Aurora core without an explicit Design System decision.
6. Never invent missing stroke, size, animation, accessibility or interaction rules from visual similarity alone.

## Current scope

This first Iconography Foundation documents the Figma icon library as the source inventory and establishes consumption rules. It does not attempt to reproduce 1,500 SVG/vector definitions inside GitHub. A machine-readable manifest provides the catalog boundary; individual vector exports can be added later when code distribution requires them.