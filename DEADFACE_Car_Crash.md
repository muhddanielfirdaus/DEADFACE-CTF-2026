# DEADFACE CTF 2026 — Car Crash OSINT Write-Up

- **Challenge:** Car Crash
- **Category:** OSINT
- **Points:** 50
- **Challenge Author:** RP-01?
- **Objective:** Identify the company associated with a commercial truck in a crash photograph and determine the company's founding date.

---

## 1. Challenge Overview

The challenge provides a photograph of a traffic collision involving a commercial box truck. The task is to use information visible in the image to identify the company operating the truck, then research when that company was founded.

**Flag format:**

```text
deadface{MM_DD_YYYY}
```

The key is to focus on details that can identify the vehicle's operator rather than investigating every object in the scene.

## 2. Initial Image Review

The supplied evidence image shows a collision involving a white box truck and a dark-coloured sedan. Police and bystanders are visible around the scene.

![Original truck crash evidence](Images/truck_crash.png)

*Figure 1: Original crash-scene photograph supplied with the challenge.*

Several background details could help locate the incident, including:

- Road signs for **S 200th Street** and **Military Road South**.
- Nearby shopping-centre signs.
- A 76 gas station sign.

These details suggest a location around the SeaTac / Des Moines area of Washington State. However, determining the precise crash location is not necessary to answer the challenge's main question.

The same image can then be inspected more closely for registration or identification markings on the truck.

## 3. Identifying the Truck

The truck's cargo box has little prominent company branding, but a closer look at the **same evidence image** reveals a small regulatory marking near the upper-right area of the box.

![Truck crash evidence used to inspect the USDOT marking](Images/truck_crash.png)

*Figure 2: The same original image is used for this step. Zoom in on the upper-right portion of the truck's cargo box to inspect the marking; no separate evidence screenshot was available.*

**Identifier observed:**

```text
USDOT: 080806
```

A USDOT number is an identifier associated with motor carriers registered with the United States Department of Transportation. It can be used to search public carrier-registration and safety records.

This number provides a lead for identifying the company connected to the truck. No additional search-result or registry screenshots are included because the crash photograph is the only evidence image available.

## 4. Investigating the USDOT Number

The next step is to search for the number in public sources.

### Method 1: Search engine

Search for the identifier using queries such as:

```text
USDOT 080806
USDOT 80806 carrier
```

Search results identify the registered carrier as **J.B. Hunt Transport Inc.**, commonly associated with **J.B. Hunt Transport Services, Inc.**

### Method 2: Carrier lookup database

A transport-registry lookup service such as [DOT.report](https://dot.report/) can be used to search carrier records by USDOT number. The result can be cross-checked against other public records to confirm the carrier name.

This second lookup provides an additional verification step rather than relying on a single search result.

**Finding:** The truck is associated with J.B. Hunt Transport Services, Inc.

## 5. Finding the Company's Founding Date

After identifying the company, research its corporate history using a search query such as:

```text
J.B. Hunt Transport Services founded date
```

The company's history states that J.B. Hunt Transport Services was founded on **August 10, 1961**.

Convert the date into the required flag format:

| Field | Value |
|---|---|
| Month (`MM`) | `08` |
| Day (`DD`) | `10` |
| Year (`YYYY`) | `1961` |

## 6. Flag Construction

The challenge requires the date in `MM_DD_YYYY` order.

```text
deadface{08_10_1961}
```

**Final flag:**

```text
deadface{08_10_1961}
```

## 7. Key Takeaways

1. **Read the objective carefully.** A photograph may contain many location clues, but not every clue is needed to solve the challenge.
2. **Inspect images at full resolution.** Small regulatory numbers can be more useful than obvious visual features such as logos or vehicle colour.
3. **Pivot from unique identifiers.** A USDOT number can lead from a photograph to public carrier-registration information.
4. **Verify important findings.** Cross-check the carrier's identity and founding date using reliable public sources before submitting the flag.

## References

- [DOT.report — carrier lookup](https://dot.report/)
- [J.B. Hunt Transport Services — official website](https://www.jbhunt.com/)
- DEADFACE CTF 2026 challenge: **Car Crash** (challenge author: RP-01?)
