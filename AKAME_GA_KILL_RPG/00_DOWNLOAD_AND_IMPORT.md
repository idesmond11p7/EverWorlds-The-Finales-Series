# Akame ga Kill! RPG CCV3 — Download Index

**Start here:** [CCV3 core card JSON](https://github.com/idesmond11p7/Everworlds-The-Finales-Series/blob/akame-rpg-ccv3-research/AKAME_GA_KILL_RPG/30_AKAME_GA_KILL_RPG_CCV3_CORE_CARD.json). Open the file and use GitHub's Download raw option. It embeds the full 204-entry lorebook.

## Supporting files
- [Standalone World Info import](https://github.com/idesmond11p7/Everworlds-The-Finales-Series/blob/akame-rpg-ccv3-research/AKAME_GA_KILL_RPG/34_AKAME_RPG_WORLD_INFO_IMPORT.json)
- [Campaign state template](https://github.com/idesmond11p7/Everworlds-The-Finales-Series/blob/akame-rpg-ccv3-research/AKAME_GA_KILL_RPG/32_CAMPAIGN_STATE_TEMPLATE.json)
- [24 regression scenarios](https://github.com/idesmond11p7/Everworlds-The-Finales-Series/blob/akame-rpg-ccv3-research/AKAME_GA_KILL_RPG/33_PLAYABILITY_REGRESSION_TESTS_V1.md)
- [Import and startup guide](https://github.com/idesmond11p7/Everworlds-The-Finales-Series/blob/akame-rpg-ccv3-research/AKAME_GA_KILL_RPG/35_README_IMPORT_AND_START.md)
- [Canonical lorebook source](https://github.com/idesmond11p7/Everworlds-The-Finales-Series/blob/akame-rpg-ccv3-research/AKAME_GA_KILL_RPG/31_AKAME_RPG_CORE_LOREBOOK.json)

## Import
1. Download the CCV3 card JSON.
2. Import it through SillyTavern's character import option.
3. Start a new chat and complete character/campaign setup.
4. Do not bind the standalone World Info copy to the same character unless duplicate lore injection is intentional.

## Structural verification
- CCV3 envelope uses `chara_card_v3` version `3.0`.
- 204 embedded entries and 204 unique entry IDs.
- All trigger keywords are separate strings in arrays.
- Standalone World Info has matching entry IDs, keys and content.
- Campaign state is `UNINITIALIZED`.
- The 24 behavioral scenarios are written, not claimed as passed runtime tests.
