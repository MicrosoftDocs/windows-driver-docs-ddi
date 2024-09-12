---
UID: NF:fwpmk.FwpmFilterAdd0
tech.root: netvista
title: FwpmFilterAdd0
ms.date: 06/21/2024
targetos: Windows
description: The FwpmFilterAdd0 function adds a new filter object to the system.
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
 - FwpmFilterAdd0
f1_keywords:
 - FwpmFilterAdd0
 - fwpmk/FwpmFilterAdd0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmFilterAdd0
---

## -description

The **FwpmFilterAdd0** function adds a new filter object to the system.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param filter [in]

The filter object to be added.

### -param sd [in, optional]

Security information about the filter object.

### -param id [out, optional]

The runtime identifier for this filter.

## -returns

| Return code/value | Description |
| ----------------- | ----------- |
| ERROR_SUCCESS<br>0 | The filter was successfully added. |
| ERROR_INVALID_SECURITY_DESCR<br>0x8007053A | The security descriptor structure is invalid. Or, a filter condition contains a security descriptor in absolute format. |
| FWP_E_CALLOUT_NOTIFICATION_FAILED<br>0x80320037 | The caller added a callout filter and the callout returned an error from its notification routine. |
| FWP_E_* error code<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/desktop/FWP/wfp-error-codes) for details. |
| RPC_* error code<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

**FwpmFilterAdd0** adds the filter to the specified sub-layer at every filtering layer in the system.

Some fields in the **[FWPM_FILTER0](/windows/win32/api/fwpmtypes/ns-fwpmtypes-fwpm_filter0)** structure are assigned by the system, not the caller, and are ignored in the call to **FwpmFilterAdd0**.

If the caller supplies a **NULL** security descriptor, the system will assign a default security descriptor.

To block connections to particular locations, add a **[FWP_ACTION_BLOCK](/windows/win32/api/fwpmtypes/ns-fwpmtypes-fwpm_action0)** filter specifying the local address at the [FWPM_LAYER_ALE_AUTH_CONNECT_V*](/windows/desktop/FWP/management-filtering-layer-identifiers-) layer, or add a **FWP_ACTION_BLOCK** filter without specifying the local address at the **FWPM_LAYER_ALE_RESOURCE_ASSIGNMENT_V*** layer.

If a local address is specified at the resource assignment layer, an implicit bind would succeed because address, address type, and port may come back as **[FWP_EMPTY](/windows/win32/api/fwptypes/ne-fwptypes-fwp_data_type)**.

The [FWPM_FILTER0](/windows/win32/api/fwpmtypes/ns-fwpmtypes-fwpm_filter0) structure can label a filter as a boot-time or persistent filter.  Boot-time filters are added to the Base Filtering Engine (BFE) when the TCP/IP driver starts, and are removed once the BFE finishes initialization.  Persistent objects are added when the BFE starts.

This function cannot be called from within a read-only transaction, it fails  with **FWP_E_INCOMPATIBLE_TXN**. See [Object Management](/windows/desktop/FWP/object-management) for more information about transactions.

The caller needs the following access rights:

- [FWPM_ACTRL_ADD](/windows/desktop/FWP/access-right-identifiers) access to the filter's container
- [FWPM_ACTRL_ADD_LINK](/windows/desktop/FWP/access-right-identifiers) access to the provider (if any)
- [FWPM_ACTRL_ADD_LINK](/windows/desktop/FWP/access-right-identifiers) access to the applicable layer
- [FWPM_ACTRL_ADD_LINK](/windows/desktop/FWP/access-right-identifiers) access to the applicable sub-layer
- [FWPM_ACTRL_ADD_LINK](/windows/desktop/FWP/access-right-identifiers) access to the callout (if any)
- [FWPM_ACTRL_ADD_LINK](/windows/desktop/FWP/access-right-identifiers) access to the provider context (if any).
  
See [Access Control](/windows/desktop/FWP/access-control) for more information.

To add a filter that references a callout, invoke the functions in the following order.

- Call **[FwpsCalloutRegister0](../fwpsk/nf-fwpsk-fwpscalloutregister0.md)** (documented in the Windows Driver Kit (WDK)), to register the callout with the filter engine.
- Call **[FwpmCalloutAdd0](nf-fwpmk-fwpmcalloutadd0.md)** to add the callout to the system.
- Call **FwpmFilterAdd0** to add the filter that references the callout to the system.

By default filters that reference callouts that have been added but have not yet registered with the filter engine are treated as Block filters.

**FwpmFilterAdd0** is a specific implementation of FwpmFilterAdd. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)  for more information.

### Examples

The following C++ example shows how to initialize and add a filter using **FwpmFilterAdd0** that specifically blocks traffic on IP V4 for all applications.

```cpp
// Add filter to block traffic on IP V4 for all applications. 
//
FWPM_FILTER0      fwpFilter;
FWPM_SUBLAYER0    fwpFilterSubLayer;  

RtlZeroMemory(&fwpFilter, sizeof(FWPM_FILTER0));

fwpFilter.layerKey = FWPM_LAYER_ALE_AUTH_RECV_ACCEPT_V4;
fwpFilter.action.type = FWP_ACTION_BLOCK;

if (&fwpFilterSubLayer.subLayerKey != NULL)
    fwpFilter.subLayerKey = fwpFilterSubLayer.subLayerKey;

fwpFilter.weight.type = FWP_EMPTY; // auto-weight.
fwpFilter.numFilterConditions = 0; // this applies to all application traffic
fwpFilter.displayData.name = L"Receive/Accept Layer Block";
fwpFilter.displayData.description = L"Filter to block all inbound connections.";

printf("Adding filter to block all inbound connections.\n");
result = FwpmFilterAdd0(engineHandle, &fwpFilter, NULL, NULL);

if (result != ERROR_SUCCESS)
    printf("FwpmFilterAdd0 failed. Return value: %d.\n", result);
else
    printf("Filter added successfully.\n");

```

## -see-also

- **[FwpsCalloutRegister0](/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpscalloutregister0)**
- **[FwpmCalloutAdd0](nf-fwpmk-fwpmcalloutadd0.md)**
- **[FWPM_FILTER0](/windows/win32/api/fwpmtypes/ns-fwpmtypes-fwpm_filter0)**
- [Management Functions](/windows/desktop/FWP/fwp-mgmt-functions)
- [WFP Functions](/windows/desktop/FWP/fwp-functions)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
