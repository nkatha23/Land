# Land
Land Tokenization Canister on ICP

This repository implements a land tokenization system on the Internet Computer (ICP) using the Rust programming language. The canister allows for the minting, transferring, and querying of digital tokens representing real-world land assets. Each token corresponds to a specific plot of land, and the system is designed to track land ownership in a decentralized and transparent manner.
Features

    Mint Land Token: Create a new token for a specific piece of land with details like location and area.
    Transfer Ownership: Transfer the ownership of land tokens to a new user.
    Query Land Information: Query information about a specific land token.
    Get Current Owner: Check the current owner of a specific land token.

Prerequisites

Before you begin, ensure you have the following installed:

    DFINITY SDK (dfx) – For deploying and managing canisters on the Internet Computer.
    Rust – The programming language used to write the canister code.
    Node.js and NPM – For package management and dependencies.

Installing DFINITY SDK

Follow the instructions on the official DFINITY documentation to install the SDK: DFINITY Setup Guide
Installing Rust

You can install Rust via the official website: Rust Install

curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

Installing dfx

Once you've installed the DFINITY SDK, you can install dfx (DFINITY's command-line interface) with the following command:

sh -ci "$(curl -fsSL https://sdk.dfinity.org/install.sh)"

Project Setup
Clone the Repository

git clone https://github.com/your-username/land-tokenization.git
cd land-tokenization

Install Dependencies

In the root of your project, run the following command to install the necessary dependencies:

dfx build

This command will build the canister and its dependencies.
Canister Setup
Initialize the Canister

To initialize the canister and create the required storage for land tokens, run the following command:

dfx canister call land_tokenization initialize

Build the Canister

Once everything is set up, build the canister using:

dfx build

Deploy the Canister

Deploy the canister to the local Internet Computer replica or to the main network (for deployment to the main network, ensure you are logged in via your DFINITY account):

dfx canister create land_tokenization
dfx canister install land_tokenization

This will deploy the canister to the local environment by default. If you're deploying to the main network, ensure you've configured your wallet and network settings accordingly.
Canister Functions
Mint Land Token

To mint a new land token, use the following command. This will create a token representing a specific land plot.

dfx canister call land_tokenization mint_land_token '("land1", "Location A", 5000)'

Where:

    "land1" is the land ID (can be any unique identifier).
    "Location A" is the physical location of the land.
    5000 is the area of the land in square feet.

Transfer Land Token Ownership

To transfer the ownership of a land token, use the following command. You will need the Principal ID of the new owner.

dfx canister call land_tokenization transfer_land_token '("land1", "principal-id-of-new-owner")'

Where:

    "land1" is the land ID you wish to transfer.
    "principal-id-of-new-owner" is the Principal ID of the new owner.

Query Land Information

You can query the details of a specific land token (such as its location, area, and current owner) using this command:

dfx canister call land_tokenization get_land_info '("land1")'

Get Current Land Owner

To check who the current owner of a land token is, use:

dfx canister call land_tokenization get_owner_of_land '("land1")'

Where "land1" is the ID of the land token.
Project Structure

land-tokenization/
├── rust/
│   ├── Cargo.toml         # Rust dependencies and configuration
│   └── src/
│       └── lib.rs         # Canister logic written in Rust
├── dfx.json               # DFINITY configuration file
├── README.md              # This file
└── .dfx/                  # DFINITY-related build files

Key Files

    src/lib.rs: Contains the main logic for the canister, including functions for minting, transferring, and querying land tokens.
    dfx.json: The configuration file for deploying and managing the canister on ICP.

Testing

To test the functionality of the canister:

    Deploy the canister locally using dfx deploy.
    Use the provided commands to mint, transfer, and query land tokens.
    Ensure the ownership and land details are correctly updated by interacting with the canister via the dfx canister call commands.

License

This project is licensed under the MIT License – see the LICENSE file for details.
Contributing

Feel free to submit pull requests, open issues, or provide suggestions for further improvements to this project. Contributions are always welcome!
GitHub Repository

Land Tokenization on ICP - GitHub
