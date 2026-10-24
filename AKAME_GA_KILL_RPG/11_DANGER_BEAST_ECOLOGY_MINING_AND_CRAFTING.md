# 11 — Danger Beast Ecology, Materials, Mining and Crafting Economy

**Status:** Original gameplay/system design. Manga-established Danger Beast species and properties must be sourced individually before being added. The ecology model is original; it must not overwrite canon depictions.

## 1. Core rule: organisms are not loot containers

A Danger Beast is an organism within a habitat, food web and life history. It has needs, constraints, behavior and a population. Its body may provide useful materials, but harvesting has time, equipment, labor, safety, preservation, transport, processing and ecological costs.

The simulation must not assume:
- every beast carries a rare crafting material;
- a kill automatically yields intact organs or usable hide;
- rare species can support unlimited harvest;
- a body can be processed without tools or skill;
- a material's property transfers perfectly into an item;
- the same species behaves identically in every habitat;
- a dangerous animal exists only to attack the player.

## 2. Species dossier

Every authored species needs:
1. Stable species ID, common names, local names and source status.
2. Body plan, size range, mass range and sexual/seasonal variation where relevant.
3. Native habitat, range boundaries and migration routes.
4. Diet, prey, predators, competitors, scavengers and parasites.
5. Reproduction, maturation, lifespan and population recovery.
6. Sensory capabilities and how it detects threats/prey.
7. Social behavior, territory, group size and communication.
8. Daily and seasonal activity.
9. Locomotion, endurance, speed profile and environmental limits.
10. Defensive and offensive adaptations with demonstrated mechanisms.
11. Injury response, retreat behavior and recovery.
12. Evidence of presence: tracks, scat, damaged vegetation, calls, shed material, scent or carcasses.
13. Material yields by anatomical region and condition.
14. Material properties, stability, preparation and storage needs.
15. Human uses, taboos, legal status, conservation rules and black markets.
16. Known vulnerabilities and uncertainty.
17. Ecological consequences if the species is removed, introduced or overharvested.

## 3. Encounter logic

A beast encounter should emerge from the situation rather than a random spawn:
- current habitat and species range;
- season, time of day and weather;
- recent migration, mating, feeding or nesting activity;
- scent, noise, fire, blood, food and human traffic;
- territory and escape routes;
- local prey abundance and human encroachment;
- prior injury, habituation or hunting pressure.

The beast may flee, hide, bluff, stalk, defend offspring, investigate, scavenge or attack. An attack is not the default response to every sighting. Behavior must match species traits and immediate conditions.

## 4. Hunting and harvesting pipeline

A successful hunt begins a new problem, not a reward screen.

1. **Locate:** Track signs and estimate age, number, direction and uncertainty.
2. **Approach:** Consider wind, sound, cover, visibility, terrain and escape routes.
3. **Engage or avoid:** Resolve action and risk. An attempted kill is not a guaranteed kill.
4. **Secure:** Check whether the beast is dead, incapacitated or still dangerous.
5. **Stabilize:** Prevent contamination, spoilage, bleeding hazards or venom exposure.
6. **Butcher:** Identify anatomy, avoid damaging valuable structures, use correct tools.
7. **Sort:** Separate meat, hide, bone, organs, glands, venom, minerals, waste and contaminated material.
8. **Preserve:** Dry, salt, smoke, cool, seal, neutralize or process as the material requires.
9. **Transport:** Account for weight, bulk, smell, decay, scavengers, weather, route and time.
10. **Process:** Use a workshop, skilled labor, fuel, reagents and safe procedures.
11. **Craft:** Define design, fit, tolerances, test conditions and maintenance.
12. **Register:** Update inventory, provenance, condition, ownership, legal status and ecological impact.

Failure at one stage can reduce or destroy later value. A venom gland ruptured during butchery may contaminate other materials. Wet hide can rot before reaching the tannery. A carcass left in a stream can poison water or attract predators.

## 5. Material property ledger

Each material batch requires:
- source species and individual/harvest ID if known;
- anatomical source;
- age/condition and damage;
- contamination or disease risk;
- mass/quantity and measurement uncertainty;
- preservation method and time since harvest;
- known properties and test evidence;
- processing steps and yield losses;
- storage needs and shelf life;
- legal, cultural or religious restrictions;
- buyer/seller and provenance if traded.

Never invent an exact percentage yield without a grounded model. Use qualitative bands or ranges when evidence is limited.

## 6. Crafting is a production chain

Crafting requirements must connect:
- design knowledge;
- raw material availability;
- material grade and condition;
- tools and workshop capability;
- labor hours and skill;
- energy/fuel;
- consumables and reagents;
- tolerances and quality control;
- failed attempts and waste;
- transport, storage and maintenance.

A rare ingredient does not compensate for missing expertise or a poor design. A master craftsperson cannot build an industrial device from a sketch and no tools. Different regions may produce distinct outcomes because they have different materials, techniques, standards and cultural preferences.

## 7. Mining and extraction

A mine must be attached to a plausible deposit and geology. Its dossier needs:
- ore/mineral type and formation;
- deposit extent and confidence;
- overburden, access and drainage;
- ventilation and ground support;
- extraction methods and tools;
- labor, food, water and fuel;
- processing/refining requirements;
- tailings, waste water and contamination;
- transport and market;
- ownership, labor law, debt and safety enforcement;
- accident history and emergency routes.

### Consequences of extraction
- Pumping groundwater can lower wells elsewhere.
- Tailings can contaminate downstream farms.
- Deforestation for charcoal can increase erosion and flood peaks.
- A mine collapse can block a road or redirect underground water.
- A labor stoppage can halt local construction and military supply.
- Scarcity can make smuggling profitable.
- Closure can leave a town without wages and a state without revenue.
- New access routes can expose previously isolated habitats to hunters, settlers or disease.

These effects should propagate only through actual connected systems. A mine on an isolated watershed should not automatically poison a distant river.

## 8. Danger Beast resources and market behavior

Prices respond to scarcity, season, risk, quality, legality, processing, transport, buyer demand and substitutes. A beast material can be valuable in one region and nearly useless in another because the craft tradition or market is absent.

Trade chains may include:
- hunters and guides;
- local authorities and bounty brokers;
- butchers and preservers;
- tanners, smiths, physicians or alchemists;
- caravaners, river pilots and ship captains;
- inspectors, tax collectors and smugglers;
- workshops and final buyers.

Each intermediary adds time, loss, fees, information distortion and possible fraud. A hunter's claim that a hide came from a rare beast is not proof.

## 9. Ecology feedback and conservation

Harvest pressure changes species populations. Track:
- local sightings and catch rates;
- reproductive season;
- habitat area and connectivity;
- prey availability;
- disease;
- migration routes;
- human encroachment;
- protected zones and enforcement;
- illegal hunting and market demand.

A population decline may reduce encounters and material supply, raise prices, cause hunters to travel farther, increase conflict with local communities and eventually collapse the market. A predator's removal may increase prey and damage crops. These effects require enough time and ecological linkage; do not make every small hunt cause instant regional collapse.

## 10. Combat and environment coupling

Combat can alter ecology and terrain:
- loud weapons drive animals from cover or draw scavengers;
- blood attracts certain species if the species is adapted to detect it;
- fire removes cover, changes wind and can create smoke or escape barriers;
- a damaged bridge changes retreat routes;
- a broken lamp changes visibility and shadow;
- spilled oil or resin changes footing and fire risk;
- a collapsed tunnel can block airflow or contaminate water;
- a wounded beast may retreat, become more dangerous or die later;
- a carcass can become a contested resource or a disease hazard.

Only apply the interactions that are plausible for the actual materials, organisms and environment.

## 11. Player inventory and encumbrance

Inventory must distinguish count, mass, volume, condition, accessibility and legal status. A character cannot draw a large weapon instantly if it is strapped under other gear. Bulky loot changes movement, stealth, climbing and endurance. Wet clothing, damaged straps, leaking containers and poor packaging can alter what remains usable.

Use approximate weight bands until the system has reliable item data. Do not claim gram-level precision for a fictional object without a specification.

## 12. Consequence examples

### Example A: Venom harvest
A hunter kills a venomous beast and cuts into the wrong gland. Venom contaminates a knife and a patch of meat. The knife must be isolated and cleaned; the meat may be unsafe; the harvester needs treatment if exposed. If the contaminated waste is dumped into a small water source, downstream animals and people may be affected. The consequence radius depends on toxin persistence, dilution, water flow and use of the source.

### Example B: Forest overhunting
A trading house raises the price of a beast's horn. Hunters spend longer in the forest and kill breeding adults. Sightings decline, prey behavior changes, and the surviving animals shift territory. The local town receives less material income over time; hunters begin trespassing into another community's range. This is a delayed causal chain, not an immediate universal disaster.

### Example C: Mine sabotage
A saboteur damages a drainage pump. Water rises in the lower workings, forcing evacuation and damaging ore stock. The road to the mine becomes crowded with workers and carts; the town loses output; the river may be affected if contaminated water escapes. Whether a downstream settlement is harmed depends on what enters the water and where the watershed flows.

### Example D: Armor made from rare hide
The hide has unusual cut resistance but poor heat tolerance. The item needs correct tanning, backing, stitching and repair. It may be heavier than expected, degrade near fire and remain vulnerable at joints. Its properties are not the living beast's entire defensive capability transferred to a vest.

## 13. Test cases

- Hunt attempted but beast escapes, leaving tracks and an injured animal.
- Harvest attempted with insufficient tools and poor anatomical knowledge.
- Carcass left unattended while the party travels.
- Rare material spoils because the preservation method is wrong.
- Mine output falls after a road closure.
- Beast population declines after several seasons of commercial hunting.
- A crafting attempt fails and consumes part of the material.
- A valuable organ is legally protected in one jurisdiction and openly traded in another.
- An injured beast returns to its territory and changes local behavior.
- A mine's waste affects only hydrologically connected areas.
- A successful harvest creates evidence, smell, weight and transport problems rather than disappearing into abstract inventory.

## 14. Next content batches

- Canon Danger Beast register with manga evidence.
- Original species catalog by biome.
- Material and craft recipe database with provenance.
- Regional mining and metallurgy profiles.
- Medicine, toxins, disease and healing constraints.
- Trade routes, markets, currencies and legal restrictions.
- Seasonal ecology and migration calendars.
