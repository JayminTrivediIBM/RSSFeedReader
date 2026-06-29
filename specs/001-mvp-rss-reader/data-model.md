# Data Model: MVP RSS Reader

## Entities

### Subscription

- **Id**: Unique identifier for the subscription entry
- **Url**: The feed URL entered by the user
- **CreatedAt**: Optional timestamp for tracking when the subscription was added

### SubscriptionList

- **Items**: A collection of subscriptions currently active in the session

## Relationships

- A subscription list contains zero or more subscriptions.
- Each subscription belongs to exactly one active subscription list for the current session.

## Validation Rules

- A subscription URL must not be empty or whitespace-only.
- Duplicate subscriptions for the same URL should be prevented in the current session.
