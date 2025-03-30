
# 🧩 YLIUM `mdi-cli` — Command-Line Interface

> **Version**: 0.8.0-2  
> A modular CLI tool to manage document notarization, transaction sync, and account operations using the Ylium Core blockchain engine.

---

## 🚀 Getting Started

```bash
node client.js [global options] <command> [subcommand] [arguments]
```

### Global Options
| Option          | Description                    |
|-----------------|--------------------------------|
| `-v, --verbose` | Enable verbose logging         |
| `--version`     | Show current CLI version       |

---

## 🔁 Command: `transaction`

### 📜 `list`
List cached transactions
```bash
node client.js transaction list [--delegee <address>] [--signer <address>] [--account <slot_id>]
```

### 🔍 `detail`
Display transaction detail
```bash
node client.js transaction detail <tx_hash> [--account <slot_id>]
```

### 🔄 `sync`
Synchronize event logs from the blockchain
```bash
node client.js transaction sync [--from-block <n>] [--to-block <n>] [--delegee <address>]
```

---

## 📄 Command: `document`

### 💬 `comment`
Retrieve the comment associated with a notarized document
```bash
node client.js document comment <document_hash>
```

### 🧬 `history`
Display the full notarization history chain of a document
```bash
node client.js document history <document_hash>
```

---

## 👤 Command: `account`

### 📋 `list`
List all configured accounts
```bash
node client.js account list
```

### 🔎 `detail`
Show details of the selected account
```bash
node client.js account detail [--account <slot_id>]
```

### 🗑️ `delete`
Delete an account (requires confirmation)
```bash
node client.js account delete [--account <slot_id>] [-x]
```
- `-x` — also deletes the associated MDI credentials

---

## ⚙️ Internal Modules Overview

| Module                | Key Functions |
|-----------------------|----------------|
| `oybns_transaction.js` | `getDocument`, `getTransactionInfo`, `getTransactionList`, `getEventsFromWeb3Provider` |
| `oybns_document.js`   | `callDocumentComment` |
| `oybns_types.js`      | `get`, `put`, `search`, `del`, `delAll`, `generateIndexKey` |
| `oybns_mdi_signer.js` | `signTransaction` |

---

## 🛠️ Configuration Requirements

Make sure these resources exist before using the CLI:

- ✅ At least one configured `Account` slot
- ✅ Active `Config` (ID = 0)
- ✅ Valid `MdiCredentials` for the selected MDI node

---

## 📎 License

MIT (see LICENSE file)

&copy; Own Your Business Ltd. All rights reserved.

