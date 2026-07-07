# AZ-900 Study Notes – 2.3 Describe Azure Storage Services

## Objectives

- Compare Azure Storage services
- Describe storage tiers
- Describe redundancy options
- Describe storage account options and storage types
- Identify options for moving files:
  - AzCopy
  - Azure Storage Explorer
  - Azure File Sync
- Describe migration options:
  - Azure Migrate
  - Azure Data Box

---

# Azure Storage Types

## Blob Storage

Storage optimized for storing massive amounts of **unstructured data**.

Examples:
- Images
- Videos
- Backups
- Documents
- Log files

---

## Disk Storage

Azure Disk Storage provides **block-level storage volumes** that are managed by Azure and used with **Azure Virtual Machines (VMs)**.

Used for:
- VM operating systems
- Applications
- Databases

---

## File Storage

Azure Files provides **fully managed file shares** that are accessible through:

- SMB (Server Message Block)
- NFS (Network File System)

Used for:
- Shared file storage
- Lift-and-shift applications
- Hybrid environments

---

## Table Storage

A NoSQL key-value store that stores **structured, schemaless data**.

Features:
- No predefined schema
- Fast access using key/attribute pairs
- Massive scalability

---

## Queue Storage

A service for storing large numbers of messages.

Features:
- Accessible through authenticated HTTP/HTTPS
- Enables communication between application components
- Supports asynchronous processing

---

# Data Types

## Structured Data

Data organized into rows and columns.

Examples:
- Excel spreadsheets
- Relational databases
- SQL databases

---

## Unstructured Data

Data without a predefined schema or data model.

Examples:
- Images
- Videos
- Audio files
- Documents
- Social media posts

---

# Azure Storage Access Tiers

Azure Blob Storage provides multiple access tiers to optimize storage costs.

Lifecycle Management policies can automatically move blobs between tiers.

| Tier | Description | Storage Cost | Access Cost | Minimum Retention |
|------|-------------|-------------:|------------:|------------------:|
| **Hot** | Frequently accessed data | Highest | Lowest | None |
| **Cool** | Infrequently accessed data | Lower | Higher | 30 days |
| **Cold** | Rarely accessed but requires fast retrieval | Lower than Cool | Higher than Cool | 90 days |
| **Archive** | Rarely accessed offline data with retrieval latency of hours | Lowest | Highest | 180 days |

---

## Cost Comparison

From **lowest storage cost** to **highest storage cost**:

1. Archive
2. Cold
3. Cool
4. Hot

From **lowest access cost** to **highest access cost**:

1. Hot
2. Cool
3. Cold
4. Archive

---

# Storage Redundancy Options

## LRS (Locally Redundant Storage)

- 3 synchronous copies
- Stored within a single physical location in the primary region
- Lowest cost redundancy option

---

## ZRS (Zone-Redundant Storage)

- 3 synchronous copies
- Stored across three Azure Availability Zones in the primary region
- Protects against datacenter failures

---

## GRS (Geo-Redundant Storage)

- Stores data using LRS in the primary region
- Asynchronously replicates data to a secondary region
- Provides six total copies:
  - 3 in the primary region
  - 3 in the secondary region

---

## GZRS (Geo-Zone-Redundant Storage)

- Uses ZRS in the primary region
- Asynchronously replicates data to a secondary region using LRS
- Highest availability option
- Recommended for mission-critical applications

---

# File Movement Options

## AzCopy

A command-line utility used to copy:

- Blobs
- Files

Supports transfers:

- To Azure Storage
- From Azure Storage
- Between storage accounts

---

## Azure Storage Explorer

A graphical application for managing Azure Storage.

Features:

- Upload files
- Download files
- Copy data
- Move blobs
- Manage multiple storage accounts

---

## Azure File Sync

Synchronizes Windows Server file shares with Azure Files.

Features:

- Bi-directional synchronization
- Centralized cloud file shares
- Local performance with cloud backup

Ideal for hybrid environments.

---

# Azure Migration Options

## Azure Migrate

Azure's centralized migration service.

Features:

- Discovery
- Assessment
- Right-sizing
- Migration
- Modernization
- Optimization

Supports migration of:

- Servers
- Virtual machines
- Databases
- Applications
- Storage

---

## Azure Data Box

A physical data transfer solution for moving large amounts of data into or out of Azure.

Features:

- Microsoft ships a secure Data Box device
- Suitable for limited or no network connectivity
- Fast and reliable offline transfer

Ideal for:

- Data transfers larger than **40 TB**
- Remote locations
- Large-scale migrations

---

# Quick Comparison

| Service | Purpose |
|----------|---------|
| Blob Storage | Store unstructured data |
| Disk Storage | Block storage for Azure VMs |
| File Storage | Managed SMB/NFS file shares |
| Table Storage | NoSQL key-value storage |
| Queue Storage | Message storage for applications |

---

# Storage Tier Summary

| Tier | Best For |
|------|----------|
| Hot | Frequently accessed data |
| Cool | Infrequently accessed data |
| Cold | Rarely accessed but still online |
| Archive | Long-term archival storage |

---

# Redundancy Summary

| Option | Copies | Protection |
|---------|--------|------------|
| LRS | 3 | Single datacenter |
| ZRS | 3 | Multiple Availability Zones |
| GRS | 6 | Primary + Secondary region |
| GZRS | 6 | Availability Zones + Secondary region |

---

# AZ-900 Exam Tips

- **Blob Storage** → Unstructured data
- **Disk Storage** → Azure Virtual Machines
- **File Storage** → SMB/NFS file shares
- **Table Storage** → NoSQL key-value store
- **Queue Storage** → Application messaging
- **Hot Tier** → Highest storage cost, lowest access cost
- **Archive Tier** → Lowest storage cost, highest access cost
- **LRS** → One datacenter
- **ZRS** → Multiple Availability Zones
- **GRS** → Secondary region replication
- **GZRS** → Highest availability
- **AzCopy** → Command-line file transfer
- **Storage Explorer** → GUI for Azure Storage
- **Azure File Sync** → Sync Windows Server with Azure Files
- **Azure Migrate** → Assess and migrate workloads
- **Azure Data Box** → Offline transfer for datasets larger than 40 TB