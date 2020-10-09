---
UID: NF:fwpsk.FwpsCompleteClassify0
title: FwpsCompleteClassify0 function (fwpsk.h)
description: A callout driver calls FwpsCompleteClassify0 to asynchronously complete a pended classify request.
old-location: netvista\fwpscompleteclassify0.htm
tech.root: netvista
ms.assetid: 995e86dc-fc26-4903-bc21-45475cb4e2bc
ms.date: 05/02/2018
keywords: ["FwpsCompleteClassify0 function"]
ms.keywords: FwpsCompleteClassify0, FwpsCompleteClassify0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCompleteClassify0, netvista.fwpscompleteclassify0, wfp_ref_2_funct_3_fwps_C_32709694-e6b8-41b8-90ea-4c8ef187ab6f.xml
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
 - FwpsCompleteClassify0
 - fwpsk/FwpsCompleteClassify0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsCompleteClassify0
---

# FwpsCompleteClassify0 function


## -description

A callout driver calls **FwpsCompleteClassify0** to asynchronously complete a pended classify request. The callout driver's [classifyFn](/windows-hardware/drivers/ddi/_netvista/) function must have previously called [FwpsPendClassify0](/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0) to pend the classify request.

> [!Note]
> **FwpsCompleteClassify0** is a specific version of **FwpsCompleteClassify**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -parameters

### -param classifyHandle

[in]
The classification handle that identifies the callout driver's processing at the current layer. This handle is obtained by calling [FwpsAcquireClassifyHandle0](/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsacquireclassifyhandle0).

### -param flags

[in]

This parameter is reserved for future use. Set to zero.

### -param classifyOut

[in, optional] A pointer to a deep copy of the [FWPS_CLASSIFY_OUT0](/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_classify_out0) structure that was originally passed to the [classifyFn](/windows-hardware/drivers/ddi/_netvista/) call when the classification was pended. When classifying asynchronously, the members of this structure can be set the same way as they would be in the callout driver's *classifyFn* function when classifying inline.

If this parameter is used, the classification is taken as the callout driver's final decision. If set to **NULL**, the indication will be reauthorized.

## -remarks

**FwpsCompleteClassify0** must be called after a callout driver has called [FwpsPendClassify0](/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpspendclassify0) to remove the classification from its pended state.

After calling this function, [FwpsReleaseClassifyHandle0](/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsreleaseclassifyhandle0) must be called to free the system resources associated with the classification handle.

## -see-also

[FWPS_CLASSIFY_OUT0](/windows/win32/api/fwpstypes/ns-fwpstypes-fwps_classify_out0)

[FwpsAcquireClassifyHandle0](nf-fwpsk-fwpsacquireclassifyhandle0.md)

[FwpsPendClassify0](nf-fwpsk-fwpspendclassify0.md)

[FwpsReleaseClassifyHandle0](nf-fwpsk-fwpsreleaseclassifyhandle0.md)

[classifyFn](/windows-hardware/drivers/ddi/_netvista/)