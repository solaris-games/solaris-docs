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
10. Combat occurs at contested stars.
11. If at the end of a galactic cycle:
11a. Players receive credits from economy and banking.
11b. Experimentations are performed.
11c. Carrier upkeep is deducted.
12. Game checks for afk and defeated players.
13. AI actions are performed.
14. Research is performed.
15. In an orbital game: the galaxy moves.
16. Time-based effects of specialists are applied.
17. Time-limited specialists are checked for expiration.
18. Game checks for a winner.
19. Intel is logged.
