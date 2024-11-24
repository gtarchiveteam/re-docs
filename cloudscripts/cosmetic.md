# Cosmetic Verification

Gorilla Tag handles cosmetic verification via PlayFab **shared group data**, constructed with cloud scripts on behalf of the server.

The group structure is as follows:

The group ID is set to a combo of the room ID and the region. For example: ``PBBVUS``

The group has Key:Value pairs for each player in the room. The key is either their player ID, or their actor number, depending on the game version.

The value is the concatenated version of the cosmetics, generated on the server from their PlayFab inventory.

Here's an example of a shared group, circa Mountains Beta:

- ``PBBVUS``
  - ``5D1404F7A44CE2C4``:``LBAAK.LBADE.LBAGS.``
  - ``F85A163A0A037EB5``:``LFAAC.LFAAE.``

# Additional Info
Newer versions of the game use an actor number instead of a player ID. The reason this was done by Another Axiom was to prevent player tracking, as a user could preform PlayFab API requests to check rooms for what player IDs they contain.

This means that implementing these scripts is slightly harder on newer versions of the game, since you have to also hook in with Photon to get the actor numbers from them.
