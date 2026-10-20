# DEADFACE CTF 2026 — Challenge Write-Up

- **Challenge Name: Ghost of Squares Past**
- **Category:** OSINT / Geolocation
- **Points:** 150
- **Author:** @RP-01?
- **Flag:** deadface{1733-1742-1815-1733-gordon}


## 1. CHALLENGE OVERVIEW

Intelligence gathered from DEADFACE communications indicates that the group has
been utilizing Savannah, Georgia's historic district squares to conceal a coded
message arranged in a classic compass pattern:
- Point 1: North (Riddle)
- Point 2: East (Photograph)
- Point 3: South (Riddle)
- Point 4: West (Photograph)
- Point 5: Center (Riddle / Meeting Point Monument)

Mission Objectives:
1. For the first four locations (North, East, South, West), determine the year
each square was established and laid out.
2. For the fifth location (Center), identify the surname engraved on the
central monument.
3. Combine the four years in the order provided (Point 1 through Point 4),
followed by the central surname.

Flag Specification:
Format: deadface{YYYY-YYYY-YYYY-YYYY-surname}
Example: deadface{1990-1982-1956-1985-smith}

Target Domain / Assets Provided:
- Point 2 Image:
- <https://deadface.sfo3.cdn.digitaloceanspaces.com/2026/challenges/osint/osint01/a21a3987-a4a5-4f3a-bdbc-c7e291e62459.png>
- Point 4 Image:
- <https://deadface.sfo3.cdn.digitaloceanspaces.com/2026/challenges/osint/osint01/ffd355b4-85e9-439e-bc6a-ee04524d05ac.png>


## 2. SPATIAL & HISTORICAL OSINT FRAMEWORK (THE OGLETHORPE PLAN)
Savannah, Georgia is celebrated worldwide for the "Oglethorpe Plan", an urban
layout conceived in 1733 by General James Edward Oglethorpe. The plan organizes
the city into repeating modular units called "wards". Each ward consists of a
central public square flanked by four "trust lots" (reserved for public buildings
and houses of worship) and forty "tithing lots" (for private homes).

Key Spatial Corridors:
1. The Bull Street Spine (North - South):
Bull Street serves as the central meridian of Savannah's historic district,
running from City Hall / the Savannah River in the north straight down to
Forsyth Park in the south. Along Bull Street sit five primary squares:
- Johnson Square  (North)
- Wright Square   (Center / Anchor)
- Chippewa Square (South)
- Madison Square  (Further South)
- Monterey Square (Southernmost on Bull St)

2. The State / President Street Corridor (East - West):
Running perpendicular to Bull Street directly through Wright Square is the
horizontal East-West axis:
- West (along Barnard Street):  Telfair Square
- Center (along Bull Street):   Wright Square
- East (along Abercorn Street): Oglethorpe Square

This creates a geometrically perfect cardinal compass cross:

[POINT 1: NORTH]
Johnson Square
(Bull St & St. Julian St)
Est: 1733
│
│
[POINT 4: WEST]  ──── [POINT 5: CENTER]  ──── [POINT 2: EAST]
Telfair Square         Wright Square          Oglethorpe Square
(Barnard & State St)   (Bull & State St)       (Abercorn & State St)
Est: 1733         Monument: "GORDON"           Est: 1742
│
│
[POINT 3: SOUTH]
Chippewa Square
(Bull St & Perry St)
Est: 1815



## 3. DETAILED STEP-BY-STEP POINT INVESTIGATION



### POINT 1: NORTH — Riddle


**Clue Text:**
> "First of them all, where the city began,
A banker's green heart in Oglethorpe's plan.
A Quaker from Rhode Island sleeps under stone here
Mark the year this first square was laid out, and draw near."

OSINT Deductions & Historical Verification:
1. "First of them all, where the city began":
When General James Oglethorpe founded the colony of Georgia in 1733, the
very first square laid out in the settlement plan was Johnson Square, named
after Robert Johnson, the Royal Governor of South Carolina who aided the
new colony.
2. "A banker's green heart in Oglethorpe's plan":
Johnson Square has historically served as the commercial and banking capital
of Savannah. Often referred to by locals as "the banking square", it is
flanked by prominent financial institutions, including the historic Citizens
and Southern National Bank and SunTrust bank buildings.
3. "A Quaker from Rhode Island sleeps under stone here":
Major General Nathanael Greene (born August 7, 1742, in Potowomut/Warwick,
Rhode Island) was raised in a devout Quaker household. A brilliant strategist
under George Washington during the American Revolutionary War, Greene died
in Georgia in 1786. In 1902, his remains (along with his son George Washington
Greene) were reinterred directly beneath the 50-foot white marble obelisk
(the Nathanael Greene Monument) in the center of Johnson Square.
4. Establishment Year:
Johnson Square was laid out in 1733.

Location Profile:
- Name: Johnson Square
- Coordinates: 32.0792° N, 81.0911° W
- Established: 1733
- Source Reference: https://en.wikipedia.org/wiki/Johnson_Square
- Reference: https://georgiahistory.com/ghmi_marker_updated/johnson-square/



### POINT 2: EAST — Location Photograph


**Clue URL:**
- <https://deadface.sfo3.cdn.digitaloceanspaces.com/2026/challenges/osint/osint01/a21a3987-a4a5-4f3a-bdbc-c7e291e62459.png>

Image Retrieval & Local Extraction:

**Command:**
curl.exe -s -o point2.png "https://deadface.sfo3.cdn.digitaloceanspaces.com/2026/challenges/osint/osint01/a21a3987-a4a5-4f3a-bdbc-c7e291e62459.png"
```

Visual Forensics & Geolocation Analysis:
1. Visual Features in Photo:
- Diagonal herringbone/running-bond brick walking path intersecting
lush green turf under live oak trees.
- Wooden park benches, trash receptacle, and vintage lamppost.
- Background: Across the street sits a classic 3-story red-brick Federal /
Georgian style historic residence featuring symmetric multi-pane sash
windows, stone lintels, and an elevated white pedimented entrance.
2. Grid Positioning:
- Following the compass layout where Point 5 is the center and Point 1 is
North, Point 2 represents the East anchor.
- Moving directly East of Wright Square along State Street brings us to
Abercorn Street, where Oglethorpe Square is situated.
3. Architectural Confirmation:
- Oglethorpe Square is bounded by East State Street, Abercorn Street, and
East York Street.
- On its northeast perimeter stands the world-famous Owens-Thomas House &
Slave Quarters (built 1816–1819 by William Jay). The surrounding perimeter
features identical 19th-century red-brick townhouses.
4. Establishment Year:
- Oglethorpe Square was laid out in 1742. It was initially called "Upper
New Square" and later renamed in honor of General James Edward Oglethorpe.

Location Profile:
- Name: Oglethorpe Square
- Coordinates: 32.0778° N, 81.0886° W
- Established: 1742
- Source Reference: https://en.wikipedia.org/wiki/Oglethorpe_Square
- Reference: https://www.telfair.org/visit/owens-thomas/



### POINT 3: SOUTH — Riddle


**Clue Text:**
> "Just a ways away a battle of a northern frontier
Gave its name to this ground eighteen-twelve drawing near.
Where a feather once drifted and a founder stands tall,
Mark the year it was laid out, the newest of all."

OSINT Deductions & Historical Verification:
1. "battle of a northern frontier / Gave its name... eighteen-twelve drawing near":
During the War of 1812, American forces commanded by Major General Jacob
Brown and Winfield Scott fought the British on the northern Niagara
frontier in Upper Canada, culminating in the Battle of Chippawa on July 5,
1814. The square was laid out shortly thereafter and named Chippewa Square
in commemoration of the American soldiers who died in the battle.
2. "Where a feather once drifted":
In the 1994 cinematic masterpiece Forrest Gump (directed by Robert Zemeckis,
starring Tom Hanks), the legendary opening and closing sequences feature a
white feather floating gently through the breeze above Savannah before
landing at Forrest's feet as he sits on a park bench waiting for the bus.
This scene was filmed on the north side of Chippewa Square along West
Hull Street.
3. "and a founder stands tall":
In the center of Chippewa Square rises the monument to General James
Edward Oglethorpe, the founder of the Colony of Georgia. The 9-foot bronze
statue of Oglethorpe stands on a gray granite base designed by Henry Bacon
with the bronze figure sculpted by the renowned American sculptor Daniel
Chester French (who also sculpted the Lincoln Memorial).
4. "the newest of all":
Chippewa Square was laid out in 1815. Among all five squares involved in
this compass puzzle (1733, 1742, 1733, and 1815), 1815 is chronologically
the newest.

Location Profile:
- Name: Chippewa Square
- Coordinates: 32.0759° N, 81.0928° W
- Established: 1815
- Source Reference: https://en.wikipedia.org/wiki/Chippewa_Square
- Reference: https://georgiahistory.com/ghmi_marker_updated/chippewa-square/



### POINT 4: WEST — Location Photograph


**Clue URL:**
- <https://deadface.sfo3.cdn.digitaloceanspaces.com/2026/challenges/osint/osint01/ffd355b4-85e9-439e-bc6a-ee04524d05ac.png>

Image Retrieval & Local Extraction:

**Command:**
curl.exe -s -o point4.png "https://deadface.sfo3.cdn.digitaloceanspaces.com/2026/challenges/osint/osint01/ffd355b4-85e9-439e-bc6a-ee04524d05ac.png"
```

Visual Forensics & Geolocation Analysis:
1. Visual Features in Photo:
- Curved low red-brick retaining wall enclosing lush green ornamental
shrubbery (liriope/agapanthus) and mulch.
- Curved street corner with bright yellow curb paint and parallel/angled
parking stall striping.
- Background (Right): A monumental two-story classical Regency-style mansion
with a pale stucco exterior finish, grand entrance portico, classical
cornice, and distinctive architectural styling.
2. Landmark Identification:
- The prominent building on the right is the historic Telfair Academy
mansion (located at 121 Barnard Street). Built in 1818 by English
architect William Jay for Alexander Telfair, it opened in 1886 as the
first public art museum in the American South.
- The curved brick planter wall and trees sit directly on the southwest
corner of Telfair Square looking east across Barnard Street toward the
Telfair Academy.
3. Grid Positioning:
- Heading directly West of Wright Square along West State Street brings us
to Barnard Street and West President Street, which forms Telfair Square.
4. Establishment Year:
- Laid out in 1733 as "St. James Square", one of the four original squares
of General Oglethorpe's founding plan. It was officially renamed Telfair
Square in 1883 in honor of the Telfair family.

Location Profile:
- Name: Telfair Square (formerly St. James Square)
- Coordinates: 32.0781° N, 81.0950° W
- Established: 1733
- Source Reference: https://en.wikipedia.org/wiki/Telfair_Square
- Reference: https://www.telfair.org/visit/telfair-academy/



### POINT 5: CENTER — Riddle & Monument Surname Inscription


**Clue Text:**
> "Four points now marked, good work, you did your best
Their meeting point holds the key to this test.
Carry their years in that order, and seek the lone name
Carved in the stone where their center lays claim."

OSINT Deductions & Monument Forensics:
1. "Their meeting point holds the key to this test":
Connecting the four compass endpoints:
- North-South Line: Johnson Square (North) to Chippewa Square (South)
along Bull Street.
- East-West Line: Oglethorpe Square (East) to Telfair Square (West)
along State / President Street.
The exact midpoint and intersection of these two cardinal axes is
WRIGHT SQUARE (located at Bull Street and State / York Street).
2. The Central Monument:
Wright Square was originally the burial site of Tomochichi, the Yamacraw
Creek chief who welcomed Oglethorpe. However, in 1883, the city erected a
towering, elaborate monument in the exact center of Wright Square to honor
William Washington Gordon (1796–1842).
Gordon was a prominent Georgia politician, mayor of Savannah, and the
founder and first president of the Central Railroad and Banking Company
of Georgia.
3. "seek the lone name Carved in the stone":
Examining the William Washington Gordon Monument:
- The monument consists of a high granite base designed by architect
Henry Van Brunt, adorned with classical figures and railroad motifs.
- Carved into the north-facing granite tablet of the main stone pedestal
in large, isolated uppercase block letters is the single surname:
> "GORDON"

Location Profile:
- Name: Wright Square
- Coordinates: 32.0778° N, 81.0922° W
- Monument: William Washington Gordon Monument
- Surname Inscription: Gordon (gordon)
- Source Reference: https://en.wikipedia.org/wiki/Wright_Square
- Reference: https://en.wikipedia.org/wiki/William_Washington_Gordon_Monument
- Reference: https://georgiahistory.com/ghmi_marker_updated/wright-square/



## 4. FLAG SYNTHESIS & VERIFICATION MATRIX


+---------+-----------+-------------------+-------------+----------------------+
| Point   | Direction | Square Name       | Estab. Year | Monument / Target    |
+---------+-----------+-------------------+-------------+----------------------+
| Point 1 | North     | Johnson Square    | 1733        | Nathanael Greene     |
| Point 2 | East      | Oglethorpe Square | 1742        | Owens-Thomas House   |
| Point 3 | South     | Chippewa Square   | 1815        | Forrest Gump / French|
| Point 4 | West      | Telfair Square    | 1733        | Telfair Academy      |
| Point 5 | Center    | Wright Square     | 1733        | "GORDON" Inscription |
+---------+-----------+-------------------+-------------+----------------------+


### Flag Assembly

- `Template: deadface{YEAR-YEAR-YEAR-YEAR-surname}`
- `Values:   deadface{1733-1742-1815-1733-gordon}`


### Final Flag

`deadface{1733-1742-1815-1733-gordon}`



## 5. OSINT LESSONS & INVESTIGATION TAKEAWAYS

1. Geospatial Alignment:
When CTF challenges mention geometric or compass alignments ("compass pattern",
> "cardinal directions", "meeting point"), plotting the targets on a satellite
or historical GIS map quickly validates hypotheses and eliminates outlier
candidates.
2. Architecture as an Anchor:
The visual identification of historical landmarks (such as the William Jay-
designed Telfair Academy and Owens-Thomas House) provided definitive visual
grounding for photographic clues without requiring metadata or reverse-image
search hits.
3. Riddle Double-Verification:
Every riddle contained multiple independent checks (e.g., War of 1812 battle,
Forrest Gump pop-culture reference, and Oglethorpe statue), ensuring 100%
confidence before final flag submission.

END OF WRITEUP
