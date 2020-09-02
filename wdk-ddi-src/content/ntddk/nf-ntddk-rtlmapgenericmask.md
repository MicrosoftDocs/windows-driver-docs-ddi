---
UID: NF:ntddk.RtlMapGenericMask
title: RtlMapGenericMask function (ntddk.h)
description: The RtlMapGenericMask routine determines the nongeneric access rights specified by an ACCESS_MASK.
old-location: kernel\rtlmapgenericmask.htm
tech.root: kernel
ms.assetid: dd3a5f87-21a9-4186-bb74-a49e6751622e
ms.date: 04/30/2018
keywords: ["RtlMapGenericMask function"]
ms.keywords: RtlMapGenericMask, RtlMapGenericMask routine [Kernel-Mode Driver Architecture], k109_f0e498a8-0b75-4fb8-a9c6-3f1ce3eb71f3.xml, kernel.rtlmapgenericmask, ntddk/RtlMapGenericMask
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlMapGenericMask
 - ntddk/RtlMapGenericMask
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlMapGenericMask
---

# RtlMapGenericMask function


## -description

The <b>RtlMapGenericMask</b> routine determines the nongeneric access rights specified by an ACCESS_MASK.

## -parameters

### -param AccessMask 

[in, out]
Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> variable. The routine updates this to contain only those access rights that are not also granted by any GENERIC_<i>XXX</i> access rights originally specified the variable. The routine also clears any GENERIC_<i>XXX</i> bits that are set.

### -param GenericMapping 

[in]
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_generic_mapping">GENERIC_MAPPING</a> structure that describes the specific access rights that correspond to each generic access right.

## -returns

None

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_generic_mapping">GENERIC_MAPPING</a>

