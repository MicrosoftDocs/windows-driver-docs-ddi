---
UID: NF:fwpmk.FwpmTransactionBegin0
tech.root: netvista
title: FwpmTransactionBegin0
ms.date: 06/19/2024
targetos: Windows
description: The FwpmTransactionBegin0 function begins an explicit transaction within the current session.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpmk.h
req.idl: 
req.include-header: 
req.irql: <= PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpmk.h
api_name:
 - FwpmTransactionBegin0
f1_keywords:
 - FwpmTransactionBegin0
 - fwpmk/FwpmTransactionBegin0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmTransactionBegin0
---

## -description

The **FwpmTransactionBegin0** function begins an explicit transaction within the current session.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param flags [in]

Possible values:

| Transaction flag | Meaning |
|--|--|
| 0 | Begin read/write transaction. |
| **FWPM_TXN_READ_ONLY** | Begin read-only transaction. |

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The transaction was started successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

This function cannot be called from within a transaction. It will fail with **FWP_E_TXN_IN_PROGRESS**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

For a read-only transaction, the caller needs [FWPM_ACTRL_BEGIN_READ_TXN](/windows/desktop/FWP/access-right-identifiers) access to the filter engine. For a read/write transaction, the caller needs **FWPM_ACTRL_BEGIN_WRITE_TXN** access to the filter engine. See [Access Control](/windows/desktop/FWP/access-control) for more information.

**FwpmTransactionBegin0** is a specific implementation of **FwpmTransactionBegin**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmTransactionBegin0](/windows/win32/api/fwpmu/nf-fwpmu-fwpmtransactionbegin0)** (user mode version)
- [FWPM_ACTRL_BEGIN_READ_TXN](/windows/desktop/FWP/access-right-identifiers)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [Object Management](/windows/desktop/FWP/object-management)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
