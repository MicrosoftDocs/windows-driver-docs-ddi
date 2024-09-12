---
UID: NF:fwpmk.FwpmConnectionPolicyDeleteByKey0
tech.root: netvista
title: FwpmConnectionPolicyDeleteByKey0
ms.date: 06/04/2024
targetos: Windows
description: The FwpmConnectionPolicyDeleteByKey0 function removes the connection policy that was created with the specified GUID.
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
 - FwpmConnectionPolicyDeleteByKey0
f1_keywords:
 - FwpmConnectionPolicyDeleteByKey0
 - fwpmk/FwpmConnectionPolicyDeleteByKey0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmConnectionPolicyDeleteByKey0
---

## -description

The **FwpmConnectionPolicyDeleteByKey0** function removes the connection policy that was created with the GUID specified in the **[FWPM_PROVIDER_CONTEXT::providerContextKey](/windows/win32/api/fwpmtypes/ns-fwpmtypes-fwpm_provider_context3)** when you called **[FwpmConnectionPolicyAdd0](nf-fwpmk-fwpmconnectionpolicyadd0.md)**.

## -parameters

### -param engineHandle [in]

A handle to an open session with the filter engine. To open a session with the filter engine, call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**.

### -param key [in]

The GUID of the connection policy that was created when you called **[FwpmConnectionPolicyAdd0](nf-fwpmk-fwpmconnectionpolicyadd0.md)**.

## -returns
| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The connection policy was successfully removed. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

## -see-also

- **[FWPM_PROVIDER_CONTEXT::providerContextKey](/windows/win32/api/fwpmtypes/ns-fwpmtypes-fwpm_provider_context3)**
- **[FwpmConnectionPolicyAdd0](nf-fwpmk-fwpmconnectionpolicyadd0.md)**
- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
