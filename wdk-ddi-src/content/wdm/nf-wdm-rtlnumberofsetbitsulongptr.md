---
UID: NF:wdm.RtlNumberOfSetBitsUlongPtr
title: RtlNumberOfSetBitsUlongPtr function (wdm.h)
description: The RtlNumberOfSetBitsUlongPtr routine returns the number of bits in the specified ULONG_PTR integer value that are set to one.
old-location: kernel\rtlnumberofsetbitsulongptr.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlNumberOfSetBitsUlongPtr function"]
ms.keywords: RtlNumberOfSetBitsUlongPtr, RtlNumberOfSetBitsUlongPtr routine [Kernel-Mode Driver Architecture], kernel.rtlnumberofsetbitsulongptr, wdm/RtlNumberOfSetBitsUlongPtr
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: Any IRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlNumberOfSetBitsUlongPtr
 - wdm/RtlNumberOfSetBitsUlongPtr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlNumberOfSetBitsUlongPtr
---

# RtlNumberOfSetBitsUlongPtr function


## -description

The <b>RtlNumberOfSetBitsUlongPtr</b> routine returns the number of bits in the specified ULONG_PTR integer value that are set to one.

## -parameters

### -param Target [in]


A ULONG_PTR integer value.

## -returns

<b>RtlNumberOfSetBitsUlongPtr</b> returns a count of the bits in the <i>Target</i> parameter that are set to one.

