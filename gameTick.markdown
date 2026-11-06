# Game Tick Events

The game runs in ticks, during a tick the following events happen in order:

1. Scheduled bulk upgrades for the previous tick are performed.
2. Abandoned stars are captured by allied players.
3. Gifted carriers in orbit of allied stars are transferred.
4. Carriers move and carrier-to-carrier combat is resolved.
5. Carrier-to-star combat is resolved.
6. Carrier drop actions are performed.
7. Ships are built at stars.
8. Carrier collect actions are performed.
9. Carrier garrison actions are performed.
10. If at the end of a galactic cycle:
    1. Players receive credits from economy and banking.
    2. Experimentation is performed.
    3. Carrier upkeep is deducted.
11. Game checks for afk and defeated players.
12. AI actions are performed.
13. Research is performed.
14. In an orbital game: the galaxy moves.
15. Time-based effects of specialists are applied.
16. Time-limited specialists are checked for expiration.
17. Game checks for a winner.
18. Intel is logged.

## Carrier Action Order

If multiple carriers perform the same category of action on the same tick at the same star
(for example, multiple carriers are scheduled to collect),
the order of actions is resolved according to these rules:

1. The carrier with more ships performs its action first.
2. If carriers have the same number of ships,
   the one that traveled the shorter distance from its last waypoint goes first.
3. If carriers tie in both of the above, the carrier that was built first goes first.
