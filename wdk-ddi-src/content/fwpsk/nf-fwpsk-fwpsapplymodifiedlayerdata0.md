---
UID: NF:fwpsk.FwpsApplyModifiedLayerData0
title: FwpsApplyModifiedLayerData0 function (fwpsk.h)
description: The FwpsApplyModifiedLayerData0 function applies changes to layer-specific data made after a call to FwpsAcquireWritableLayerDataPointer0.Note  FwpsApplyModifiedLayerData0 is a specific version of FwpsApplyModifiedLayerData.
old-location: netvista\fwpsapplymodifiedlayerdata0.htm
tech.root: netvista
ms.assetid: d32c19b6-462e-48e3-b22b-02542dca9cc4
ms.date: 05/02/2018
keywords: ["FwpsApplyModifiedLayerData0 function"]
ms.keywords: FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS, FwpsApplyModifiedLayerData0, FwpsApplyModifiedLayerData0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsApplyModifiedLayerData0, netvista.fwpsapplymodifiedlayerdata0, wfp_ref_2_funct_3_fwps_A-B_a7adbeec-b234-451e-9da0-d5e5b7cefc90.xml
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsApplyModifiedLayerData0
 - fwpsk/FwpsApplyModifiedLayerData0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsApplyModifiedLayerData0
---

# FwpsApplyModifiedLayerData0 function


## -description

The **FwpsApplyModifiedLayerData0** function applies changes to layer-specific data made after a call to [FwpsAcquireWritableLayerDataPointer0](nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md).

> [!Note]
> **FwpsApplyModifiedLayerData0** is a specific version of **FwpsApplyModifiedLayerData**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -parameters

### -param classifyHandle 

[in]
The classification handle that identifies the callout driver's processing at the current layer.
This handle is obtained by calling [FwpsAcquireClassifyHandle0](./nf-fwpsk-fwpsacquireclassifyhandle0.md).

### -param modifiedLayerData 

[in]
The data buffer obtained by calling [FwpsAcquireWritableLayerDataPointer0](nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md) with members modified by the callout driver. Supported data types are defined as structures.

### -param flags

[in]

The options to use with this function call. This flag can have the following value.

|Value|Meaning|
|--- |--- |
|**FWPS_CLASSIFY_FLAG_REAUTHORIZE_IF_MODIFIED_BY_OTHERS**|When set, this flag specifies that data at the layer of the pended classify action should be reauthorized if another callout driver modifies the data before the classification is completed. Use this flag only with pended classify and not inline classify, as its use with inline classify can lead to indeterminate results. If you do call this API for inline classify, set flags to zero.|

## -remarks

**FwpsApplyModifiedLayerData0** should be called once for every call made to[FwpsAcquireWritableLayerDataPointer0](nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md), even if the callout driver didn't modify any data.

## -see-also

[FWPS_BIND_REQUEST0](ns-fwpsk-_fwps_bind_request0.md)

[FWPS_CONNECT_REQUEST0](ns-fwpsk-_fwps_connect_request0.md)


[FWPS_FILTER1](/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_filter1)


[FwpsAcquireClassifyHandle0](nf-fwpsk-fwpsacquireclassifyhandle0.md)


[FwpsAcquireWritableLayerDataPointer0](nf-fwpsk-fwpsacquirewritablelayerdatapointer0.md)



[FwpsReleaseClassifyHandle0](nf-fwpsk-fwpsreleaseclassifyhandle0.md)



[classifyFn](../_netvista/index.md)