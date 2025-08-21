# 🚀 Pipe Firestarter: Complete Setup & Usage Guide

**Created by: Satyam Jha** 

---

## 🌟 What is Pipe Firestarter?

Pipe Firestarter represents a revolutionary approach to decentralized storage and content delivery. Think of it as a blockchain-powered fusion of Google Drive's storage capabilities with Cloudflare's global content delivery network, but completely decentralized.

### Key Features:
- **Decentralized Infrastructure**: No single point of failure
- **Solana-Powered**: Built on one of the fastest blockchains
- **Massive Scale**: Already storing 1 petabyte of Solana's blockchain data
- **Performance**: Reduces validator sync times by approximately 30%
- **Economic Model**: $PIPE token ecosystem with burn-and-mint mechanics
- **Privacy**: Built-in encryption for sensitive data
- **Global Delivery**: Low-latency worldwide content distribution

### How It Works:
Instead of storing your files on centralized servers owned by big tech companies, Pipe Firestarter distributes them across a network of independent node operators. When you pay with $PIPE tokens, those tokens are burned and then re-minted as rewards for the node operators who store and serve your data.

---

## 🔧 System Preparation & Dependencies

Before we begin with Pipe Firestarter, we need to prepare your system with all necessary tools and dependencies.

### Step 1: System Update
First, let's ensure your system is up-to-date with the latest packages and security updates:

```bash
sudo apt update && sudo apt upgrade -y
```

**What this does**: Updates your package lists and upgrades all installed packages to their latest versions.

### Step 2: Install Essential Dependencies
Now we'll install all the tools needed for building and running Pipe Firestarter:

```bash
sudo apt install curl iptables build-essential git wget lz4 jq make gcc postgresql-client nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev tar clang bsdmainutils ncdu unzip libleveldb-dev libclang-dev ninja-build -y
```

**Package Breakdown**:
- `curl` & `wget`: For downloading files from the internet
- `git`: Version control system for cloning repositories
- `build-essential`, `gcc`, `clang`: Compilers for building software from source
- `libssl-dev`: SSL/TLS library for secure connections
- `jq`: Command-line JSON processor
- `tmux`: Terminal multiplexer for managing sessions
- `htop`: Advanced system monitor
- `nvme-cli`: NVMe drive management tools
- And many other essential development libraries

---

## 🦀 Rust Installation

Pipe Firestarter is built in Rust, so we need to install the Rust programming language and its package manager, Cargo.

### For Linux Users:
```bash
curl https://sh.rustup.rs -sSf | sh
```

**What this does**: Downloads and runs the official Rust installation script securely.

After installation, activate Rust in your current shell:
```bash
source $HOME/.cargo/env
```

### For macOS Users:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Then activate Rust:
```bash
source $HOME/.cargo/env
```

### Verify Installation:
Let's confirm Rust and Cargo are properly installed:
```bash
rustc --version
cargo --version
```

**Expected Output**: You should see version numbers for both rustc (Rust compiler) and cargo (Rust package manager).

---

## 💾 Pipe Firestarter Installation

### Step 1: Clone the Repository
Download the official Pipe Firestarter source code:

```bash
git clone https://github.com/PipeNetwork/pipe.git
cd pipe
```

**What this does**: 
- Clones the entire Pipe repository to your local machine
- Changes into the pipe directory to begin installation

### Step 2: Build and Install pipe-cli
This step compiles the Rust code and installs the Pipe CLI tool:

```bash
cargo install --path
```

**What this does**: 
- Compiles all the Rust source code
- Installs the `pipe` command-line tool globally on your system
- This may take several minutes depending on your system's performance

### Step 3: Verify Installation
Confirm that Pipe CLI is correctly installed and accessible:

```bash
pipe -h
```

**Expected Output**: You should see a help menu with all available Pipe commands and options.

---

## 👤 User Account Setup

### Step 1: Create Your Pipe User Account
Initialize your Pipe Firestarter user account:

```bash
pipe new-user <your_username>
```

**Important Notes**:
- Replace `<your_username>` with your desired username (no spaces or special characters)
- **Save the `Solana Pubkey` that gets generated** - you'll need this later
- This pubkey is your unique identifier on the Solana blockchain

**Example**: `pipe new-user satyamjha`

### Step 2: Set Up Account Security
Create a secure password for your account:

```bash
pipe set-password
```

**Security Tips**:
- Use a strong, unique password
- Include uppercase, lowercase, numbers, and special characters
- Don't reuse passwords from other services
- Consider using a password manager

### Step 3: Backup Your Credentials
Your account credentials are stored in a JSON file. Let's view and backup this critical information:

```bash
nano ~/.pipe-cli.json
```

**⚠️ CRITICAL**: Copy and securely store ALL the information in this file:
- Your username
- Solana public key
- Private key information
- Any other configuration data

**Security Note**: Never share this file or its contents with anyone. Store it securely offline as a backup.

---

## 🎯 Referral Program & Rewards

Pipe Firestarter offers a generous referral program where you can earn up to 100 PIPE tokens for each person you refer who swaps at least 1 SOL (Devnet) for PIPE tokens.

### Apply a Referral Code (Optional)
If someone referred you to Pipe Firestarter, you can apply their referral code:

```bash
pipe referral apply SATYAMOG-5VRQ
```

**Benefits**: 
- You may receive bonus tokens
- Supports the person who introduced you to Pipe

### Generate Your Referral Code
Create your own referral code to start earning from referrals:

```bash
pipe referral generate
```

**What you get**: A unique referral code that you can share with friends and on social media.

### Track Your Referral Performance
Monitor your referral earnings and statistics:

```bash
pipe referral show
```

**Information displayed**:
- Number of successful referrals
- Total PIPE tokens earned from referrals
- Pending referrals and their status

---

## 💰 Getting PIPE Tokens

### Step 1: Get Solana Devnet Tokens
Since Pipe currently operates on Solana's development network, you need Devnet SOL tokens:

**Get Free Devnet SOL**: Visit [Solana Faucet](https://faucet.solana.com/)
- Enter your Solana public key (from your credentials file)
- Request devnet SOL tokens (usually 1-2 SOL per request)
- Wait for confirmation

### Step 2: Swap SOL for PIPE Tokens
Exchange your Devnet SOL for PIPE tokens:

```bash
pipe swap-sol-for-pipe <AMOUNT_SOL>
```

**Important Guidelines**:
- Replace `<AMOUNT_SOL>` with the amount you want to swap (e.g., `1.5`)
- **Minimum swap amount**: 1 SOL
- **Exchange rate**: Approximately 1 PIPE ≈ 1 GB of storage
- **Example**: `pipe swap-sol-for-pipe 2`

**What happens**: 
- Your SOL gets converted to PIPE tokens
- These tokens are used to pay for storage and bandwidth
- The swap is recorded on the Solana blockchain

---

## 📁 File Operations

### Uploading Files

Upload any file to the decentralized Pipe network:

```bash
pipe upload-file <FILE_PATH> <FILE_NAME>
```

**Parameter Explanation**:
- `<FILE_PATH>`: The location of your file on your computer
- `<FILE_NAME>`: What you want to name the file in Pipe storage

**Examples**:
- `pipe upload-file ~/Documents/report.pdf my-report`
- `pipe upload-file /home/user/video.mp4 demo-video`
- `pipe upload-file ./image.jpg profile-picture`

**File Path Tips**:
- For files in your home directory: `~/filename`
- For files in current directory: `./filename`
- For absolute paths: `/full/path/to/file`

**Important Security Notes**:
- ⚠️ **NEVER upload confidential files** like wallet private keys, personal documents, or sensitive data
- ⚠️ **Files are stored on a decentralized network** - assume they could be accessible to others
- ✅ **Good for**: Public content, media files, documents you're willing to share
- ✅ **Supported**: All file types including large videos, images, documents, archives

### Creating Public Links

Generate shareable links for your uploaded files:

```bash
pipe create-public-link <FILE_NAME>
```

**What this does**:
- Creates a public URL that anyone can use to access your file
- The link works globally with low latency
- File is served from the closest available nodes

**Example**: If you uploaded a file named "my-report", run:
```bash
pipe create-public-link my-report
```

**Use Cases**:
- Share files with colleagues or friends
- Host images for websites
- Distribute content globally
- Create backup links for important files

---

## 📊 Monitoring & Management

### Check Token Usage
Monitor how many PIPE tokens you've spent on storage and bandwidth:

```bash
pipe token-usage
```

**Information displayed**:
- Total tokens spent on uploads
- Total tokens spent on downloads/bandwidth
- Remaining token balance
- Storage space used

**Cost Management Tips**:
- Monitor usage regularly to avoid running out of tokens
- Plan your uploads based on available token balance
- Consider the size of files before uploading

---

## 🔥 Earning the Firestarter Discord Role

The Pipe community recognizes active users with special Discord roles. Here's how to earn the prestigious Firestarter role:

### Step 1: Join the Community
Join the official Pipe Discord server: [Pipe Discord](https://discord.gg/fhVwSe8j)

### Step 2: Meet the Requirements
To earn the Firestarter role, you need to demonstrate active usage of the platform:

**Requirements**:
- Upload at least one file to Pipe Firestarter
- Create a public link for your uploaded file
- Show proof of both actions in the Discord server

### Step 3: Complete the Process

1. **Upload a file** using the [file upload process](#uploading-files)
2. **Create a public link** using the [public link creation process](#creating-public-links)
3. **Share your achievement** in the appropriate Discord channel
4. **Wait for verification** by community moderators

**Benefits of Firestarter Role**:
- Special recognition in the community
- Access to exclusive channels
- Early access to new features
- Direct communication with developers

---

## 🛠️ Advanced Operations

The Pipe CLI offers many more advanced features beyond basic file operations. For comprehensive documentation of all available commands and their options, visit the official repository:

**Official Documentation**: [Pipe Repository](https://github.com/PipeNetwork/pipe)

**Additional Features Include**:
- Folder uploads and management
- File encryption and decryption
- Bandwidth optimization settings
- Node operator functions
- Advanced token management
- API integrations
- Automated backup solutions

---

## 🔍 Troubleshooting

### Common Issues and Solutions

**Installation Problems**:
- Ensure all dependencies are installed
- Check that Rust is properly installed and in PATH
- Verify internet connection during installation

**Authentication Issues**:
- Double-check your credentials file
- Ensure password was set correctly
- Verify Solana pubkey is valid

**Upload Failures**:
- Check your PIPE token balance
- Verify file path is correct
- Ensure file size is reasonable
- Check internet connection stability

**Token Swap Issues**:
- Confirm you have sufficient Devnet SOL
- Verify minimum swap amount (1 SOL)
- Check Solana network status

---

## 📞 Community & Support

### Get Help and Stay Updated

**Telegram Community**: [DM me](https://t.me/opdrago)
- Real-time community support
- Latest updates and announcements
- Direct communication with users and developers

**Discord Server**: [Pipe Discord](https://discord.gg/fhVwSe8j)
- Official community hub
- Role-based access to exclusive content
- Technical discussions and support

**GitHub Issues**: For technical problems or bug reports, open an issue on the [official repository](https://github.com/PipeNetwork/pipe)

---

## ⚖️ Legal & Disclaimer

**Important Notes**:
- Pipe Firestarter currently operates on Solana's development network (Devnet)
- Devnet tokens have no real-world monetary value
- This is experimental technology - use responsibly
- Always backup important data through multiple methods
- Never upload sensitive or confidential information

---

## 🎉 Conclusion

Congratulations! You now have a complete Pipe Firestarter setup ready for decentralized storage and content delivery. This guide has taken you through every step from initial system preparation to advanced usage.

**What you've accomplished**:
✅ Set up a complete development environment
✅ Installed and configured Pipe Firestarter
✅ Created your user account with proper security
✅ Learned how to manage PIPE tokens
✅ Mastered file upload and sharing processes
✅ Understood the community ecosystem

**Next Steps**:
- Start experimenting with file uploads
- Join the community and earn your Firestarter role
- Explore advanced CLI features
- Consider becoming a node operator
- Share your experience with others

---

**Created with ❤️ by Satyam Jha**

*Happy coding and welcome to the decentralized future of storage! 🚀*

---

*If you encounter any issues or have questions, feel free to reach out through the community channels or open an issue on GitHub. The Pipe community is here to help you succeed!*
