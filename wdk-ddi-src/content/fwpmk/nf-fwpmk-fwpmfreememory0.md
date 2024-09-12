---
UID: NF:fwpmk.FwpmFreeMemory0
tech.root: netvista
title: FwpmFreeMemory0
ms.date: 06/07/2024
targetos: Windows
description: The FwpmFreeMemory0 function is used to release memory resources allocated by the Windows Filtering Platform (WFP) functions.
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
 - FwpmFreeMemory0
f1_keywords:
 - FwpmFreeMemory0
 - fwpmk/FwpmFreeMemory0
dev_langs:
 - c++
helpviewer_keywords:
 - FwpmFreeMemory0
---

## -description

The **FwpmFreeMemory0** function is used to release memory resources allocated by the Windows Filtering Platform (WFP) functions.

## -parameters

### -param p [in, out]

Address of the pointer to be freed.

## -remarks

**FwpmFreeMemory0** is used to free memory returned by the various Fwpm* functions, such as **[FwpmFilterGetByKey0](nf-fwpmk-fwpmfiltergetbykey0.md)**.

Fwpm* functions that return a **HANDLE**, such as **[FwpmCalloutCreateEnumHandle0](nf-fwpmk-fwpmcalloutcreateenumhandle0.md)**, have specific functions to release memory.

If the caller passes a pointer that is not valid, the behavior is undefined.

**FwpmFreeMemory0** is a specific implementation of **FwpmFreeMemory**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmFilterGetByKey0](nf-fwpmk-fwpmfiltergetbykey0.md)**
- **[FwpmCalloutCreateEnumHandle0](nf-fwpmk-fwpmcalloutcreateenumhandle0.md)**
- [WFP Functions](/windows/desktop/FWP/fwp-functions)
- [Windows Filtering Platform API Reference](/windows/desktop/FWP/fwp-reference)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
