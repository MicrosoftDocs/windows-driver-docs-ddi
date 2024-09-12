---
UID: NC:fwpmk.FWPM_SERVICE_STATE_CHANGE_CALLBACK0
tech.root: netvista
title: FWPM_SERVICE_STATE_CHANGE_CALLBACK0
ms.date: 05/30/2024
targetos: Windows
description: The FWPM_SERVICE_STATE_CHANGE_CALLBACK0 function is implemented by a WFP callout driver to add custom behavior to the base filtering engine (BFE) service state change notification process.
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
 - LibDef
api_location:
 - fwpmk.h
api_name:
 - FWPM_SERVICE_STATE_CHANGE_CALLBACK0
f1_keywords:
 - FWPM_SERVICE_STATE_CHANGE_CALLBACK0
 - fwpmk/FWPM_SERVICE_STATE_CHANGE_CALLBACK0
dev_langs:
 - c++
helpviewer_keywords:
 - FWPM_SERVICE_STATE_CHANGE_CALLBACK0
---

## -description

The **FWPM_SERVICE_STATE_CHANGE_CALLBACK0** function is implemented by a WFP callout driver to add custom behavior to the base filtering engine (BFE) service state change notification process.

## -parameters

### -param context [in, out]

The pointer that was passed in the *context* parameter when the callout driver called the **[FwpmBfeStateSubscribeChanges0](nf-fwpmk-fwpmbfestatesubscribechanges0.md)** function.

### -param newState [in]

The new BFE service state being changed to.

## -returns

| Return code/value | Description |
| --- | --- |
| **ERROR_SUCCESS**<br>0 | The enumerator was successfully deleted. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The filter engine calls this function whenever there is a change in the state of the filter engine.

## -see-also

- **[FwpmBfeStateSubscribeChanges0](nf-fwpmk-fwpmbfestatesubscribechanges0.md)**
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)