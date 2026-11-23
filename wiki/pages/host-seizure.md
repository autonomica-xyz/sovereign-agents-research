---
title: "Host seizure (physical raids on servers)"
category: attack
status: stable
sources: [wiki/pages/approaches-physical.md]
updated: 2026-11-23
---

# Host seizure

> Police can take the machine. Raids on hosting facilities regularly take
> innocent co-tenants' servers too: Core IP Networks (Dallas, 2009), DigitalOne
> (Virginia, 2011), Megaupload's ~1,100 leased servers at Carpathia (2012).
> The counterexample is Mullvad (2023): police left with nothing because
> nothing was stored.

## Details

- Core IP Networks, 2 Apr 2009: FBI took all servers in a colocation facility
  housing about 50 businesses over one suspect.
- DigitalOne, 21 Jun 2011: FBI removed three enclosures, knocking unrelated
  clients offline.
- Megaupload, 19 Jan 2012: warrants at Carpathia and Cogent; about 1,103
  servers held; the US copied selected data and then disclaimed custody.
- Mullvad, 18 Apr 2023: officers with a warrant for customer data left
  empty-handed because the service keeps no such data.
- Seizure also enables physical attacks on TEEs
  ([tee-fail](tee-fail.md), [battering-ram](battering-ram.md)).

## How it serves the organism

Two lessons: keep nothing on a body that a captor could use (Mullvad), and
never be one machine (Megaupload).

## How it fails

(For the organism) A seized body is offline and, if it holds keys or memory
in the clear, read. Defences: many small bodies in many jurisdictions,
[rehydration](rehydration.md) from encrypted state, keys only in a quorum.

## Related

[dns-seizure](dns-seizure.md) · [approaches-physical](approaches-physical.md) · [location-hiding](location-hiding.md) · [survival-tiers](survival-tiers.md)

## Sources

- CIO on the Core IP raid (Apr 2009) — <https://www.cio.com/article/278564/data-center-when-the-fbi-raids-a-data-center-a-rare-danger.html>
- DatacenterDynamics on the DigitalOne raid (Jun 2011) — <https://www.datacenterdynamics.com/en/news/fbi-grabs-racks-of-servers-in-hosting-facility-hacking-raid>
- US v. Dotcom, EDVA filing (Mar 2012) — <https://storage.courtlistener.com/recap/gov.uscourts.vaed.275313.39.0.pdf>
- Mullvad, search warrant post (20 Apr 2023) — <https://mullvad.net/en/blog/mullvad-vpn-was-subject-to-a-search-warrant-customer-data-not-compromised>
