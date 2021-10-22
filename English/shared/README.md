# Shared data models
These data models will be shared between the server, the Unity client and the Discord bot. **These models have to be implemented in all sides.**

## PlayerWithTips
Player data with currently owned tips.
### Payload example
```json
{
    "player_id": "1234567890",
    "avatar_url" "https://awesome-website.com/abc.png",
    "name": "John Doe",
    "amount": 100,
    "last_daily_reward": "2021-10-21T10:42:46.137023Z",
    "last_weekly_reward":"2021-10-21T10:42:46.137024Z"
}
```
### Serialization guide
| Field              | Description                                           | Rust                       | Kotlin  | C#     |
|--------------------|-------------------------------------------------------|----------------------------|---------|--------|
| player_id          | Snowflake of a Discord user                           | String                     | String  | string |
| avatar_url         | Player's avatar url used in embeds                    | Option<String>             | String? | string |
| name               | Player's username or display name                     | String                     | String  | string |
| amount             | Tips currently owned by the player                    | i64                        | Long    | long   |
| last_daily_reward  | Last time when the player receives his daily rewards  | Option < DateTime < Utc >> | String? | string |
| last_weekly_reward | Last time when the player receives his weekly rewards | Option < DateTime < Utc >> | String? | string |