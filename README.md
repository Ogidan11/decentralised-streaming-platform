# Decentralized Video Streaming Platform

## Overview
The **Decentralized Video Streaming Platform** is a smart contract that facilitates the management of decentralized video content, premium subscriptions, and revenue distribution on the Stacks blockchain. It provides functionalities for video uploads, user subscriptions, and payments, ensuring a transparent and censorship-resistant platform for content creators and viewers.

## Features
- **Video Management**: Creators can upload videos with metadata including title, description, and price.
- **Subscriptions**: Users can subscribe to premium content.
- **Revenue Distribution**: Platform automatically distributes earnings between content creators and platform revenue.
- **Governance Mechanism**: Supports proposals and voting for platform improvements.
- **Access Control**: Administrators and content creators are managed through role-based access.
- **Security**: Includes error handling, role-based restrictions, and contract pause functionality.

## Smart Contract Structure
### 1. Constants and Error Codes
Defines key constants such as the contract owner, error codes, and platform fees.

### 2. Data Storage
Stores platform states, access control roles, video metadata, revenue records, and governance proposals.

### 3. Authorization
Ensures that only authorized users (admins, creators, subscribers) can execute specific actions.

### 4. Admin Functions
- `set-platform-fee(uint new-fee)`: Updates the platform’s transaction fee.
- `toggle-contract-pause()`: Pauses or resumes contract execution.
- `add-administrator(principal admin)`: Adds a new administrator.

### 5. Creator Functions
- `register-as-creator()`: Allows users to register as content creators.
- `upload-video(string title, string description, buff content-hash, uint price)`: Uploads a video to the platform.

### 6. User Functions
- `purchase-video(uint video-id)`: Allows users to purchase video access.
- `subscribe-premium(uint duration)`: Enables users to subscribe for premium content.

### 7. Getter Functions
- `get-video-details(uint video-id)`: Fetches video metadata.
- `get-creator-revenue(principal creator)`: Retrieves earnings of a content creator.
- `is-premium-subscriber(principal user)`: Checks if a user has an active subscription.

## Deployment Instructions
1. Ensure you have a Stacks wallet and development environment set up.
2. Deploy the contract using Clarinet or Stacks CLI.
3. Initialize the contract by setting up administrators.
4. Begin onboarding creators and users.

## Usage Examples
### Uploading a Video (By a Creator)
```
(contract-call? .decentralized-video upload-video "My Video" "A great video description" 0x123abc... u1000)
```

### Purchasing a Video
```
(contract-call? .decentralized-video purchase-video u1)
```

### Subscribing to Premium
```
(contract-call? .decentralized-video subscribe-premium u30)
```

## Security Considerations
- **Access Control**: Only admins can modify platform settings.
- **Funds Handling**: Payments are directly transferred to the respective recipients.
- **Contract Pausing**: The contract can be paused to prevent unauthorized actions during emergencies.

## Future Enhancements
- Implement decentralized storage for video files.
- Integrate NFT-based access control.
- Add more governance mechanisms for community participation.

## License
This project is released under the MIT License.

