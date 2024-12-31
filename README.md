# Analytics Token Staking and Governance Protocol

A decentralized protocol for staking STX tokens, earning analytics tokens, and participating in protocol governance through a tiered system.

## Features

- **Token Staking**: Stake STX tokens with flexible lock periods
- **Tiered System**: Three tiers with increasing benefits and voting power
- **Governance**: Create and vote on protocol proposals
- **Rewards**: Earn ANALYTICS tokens based on stake amount and duration
- **Security**: Emergency modes and contract pause functionality

## Quick Start

1. Deploy the contract to the Stacks blockchain
2. Initialize the contract using `initialize-contract`
3. Users can stake STX tokens using `stake-stx`
4. Participate in governance through `create-proposal` and `vote-on-proposal`

## Contract Architecture

### Staking System

- Minimum stake: 1,000,000 uSTX
- Lock periods: None, 1 month, or 2 months
- Reward multipliers: 1x-2x based on tier and lock period
- 24-hour cooldown period for unstaking

### Tier Levels

1. **Basic Tier**

   - Minimum: 1M uSTX
   - 1x reward multiplier
   - Basic voting rights

2. **Advanced Tier**

   - Minimum: 5M uSTX
   - 1.5x reward multiplier
   - Enhanced voting power

3. **Premium Tier**
   - Minimum: 10M uSTX
   - 2x reward multiplier
   - Maximum voting power

### Governance

- Proposal creation requires minimum voting power
- Voting period: 100-2880 blocks
- Weighted voting based on tier level

## API Reference

### Public Functions

#### Staking Operations

```clarity
(stake-stx (amount uint) (lock-period uint))
(initiate-unstake (amount uint))
(complete-unstake)
```

#### Governance Operations

```clarity
(create-proposal (description (string-utf8 256)) (voting-period uint))
(vote-on-proposal (proposal-id uint) (vote-for bool))
```

#### Administrative Functions

```clarity
(initialize-contract)
(pause-contract)
(resume-contract)
```

## Security Considerations

- Row-level security for data access
- Emergency pause functionality
- Cooldown periods for unstaking
- Tiered access control
- Input validation for all operations

## License

MIT License - see LICENSE file

## Contributing

See CONTRIBUTING.md for guidelines
