### v0.0.1

Initial testing release. Purely rebalancing of stock Mk2 spaceplane parts.

### v0.0.2

Add preliminary support for Mk2 Stockalike Expansion. This comes with a few caveats:
- Due to limited ability to override drag cubes when B9 Part Switch is used, switcheable parts have to share a single drag cube for now. This particularly affects the Mk2 nosecone cargo bay.
- It also affects the heavy VTOL engine. As this one changes node setup as well it was chosen to not give the drag reduction changes to this part as limiting it to a single drag cube would cause significant issues.

Additionally, the drag of mk2 parts has been ever so slightly increased at lower mach numbers to ensure they were balanced at higher mach numbers.

Fix an issue with the long mk2 payload bay having an auto-generated drag cube

### v0.0.3

Fix an issue with the mk2 expansion shock cone having an incorrect drag cube.

Added initial rebalancing of Mk3 spaceplane parts.
