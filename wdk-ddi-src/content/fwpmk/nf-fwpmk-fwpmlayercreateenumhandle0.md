---
UID: NF:fwpmk.FwpmLayerCreateEnumHandle0
tech.root: netvista
title: FwpmLayerCreateEnumHandle0
ms.date: 06/07/2024
targetos: Windows
description: The FwpmLayerCreateEnumHandle0 function creates a handle used to enumerate a set of layer objects.
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
 - FwpmLayerCreateEnumHandle0
f1_keywords:
 - FwpmLayerCreateEnumHandle0
 - fwpmk/FwpmLayerCreateEnumHandle0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmLayerCreateEnumHandle0
---

## -description

The **FwpmLayerCreateEnumHandle0** function creates a handle used to enumerate a set of layer objects.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param enumTemplate [in, optional]

Template to selectively restrict the enumeration.

### -param enumHandle [out]

Handle for the layer enumeration.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The enumerator was created successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

If *enumTemplate* is **NULL**, all layers are returned.

The enumerator is not live, meaning it does not reflect changes made to the system after the call to **FwpmLayerCreateEnumHandle0** returns. If you need to ensure that the results are current, you must call **FwpmLayerCreateEnumHandle0** and **[FwpmLayerEnum0](nf-fwpmk-fwpmlayerenum0.md)** from within the same explicit transaction.

The caller must free the returned handle by a call to the **[FwpmLayerDestroyEnumHandle0](nf-fwpmk-fwpmlayerdestroyenumhandle0.md)**.

The caller needs **[FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers)** access to the layers' containers and **FWPM_ACTRL_READ** access to the layers. Only layers to which the caller has **FWPM_ACTRL_READ** access will be returned. See [Access Control](/windows/desktop/FWP/access-control) for more information.

FwpmLayerCreateEnumHandle0 is a specific implementation of FwpmLayerCreateEnumHandle. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmLayerEnum0](nf-fwpmk-fwpmlayerenum0.md)**
- **[FwpmLayerDestroyEnumHandle0](nf-fwpmk-fwpmlayerdestroyenumhandle0.md)**
- **[FWPM_ACTRL_ENUM](/windows/desktop/FWP/access-right-identifiers)**
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
