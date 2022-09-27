# Ship Population Cap

If enabled, the **Ship Population Cap** will restrict the total number of ships players can have at any one time. The formula is as follows:

```
player maximum ships = (ships per star * 3) + (ships per star * owned stars)
```

For example:

- A player owns `10` stars.
- The `ships per star` setting is configured to `100` ships per star.
- The maximum ships a player can have is `1300`.
- Stars will **stop producing** ships when the total player ships has reached `1300`.

*Note: Ship Population Cap is a custom setting and is **disabled** in standard games.*
