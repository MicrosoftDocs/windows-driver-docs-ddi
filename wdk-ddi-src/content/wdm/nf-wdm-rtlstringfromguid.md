---
UID: NF:wdm.RtlStringFromGUID
title: RtlStringFromGUID function (wdm.h)
description: The RtlStringFromGUID routine converts a given GUID from binary format into a Unicode string.
old-location: kernel\rtlstringfromguid.htm
tech.root: kernel
ms.assetid: 89a3ca92-7c8a-40e3-a818-0127af6f2e91
ms.date: 04/30/2018
ms.keywords: RtlStringFromGUID, RtlStringFromGUID routine [Kernel-Mode Driver Architecture], k109_8a3ac592-7ade-48fc-9536-d8a6c84fb033.xml, kernel.rtlstringfromguid, wdm/RtlStringFromGUID
ms.topic: function
f1_keywords:
 - "wdm/RtlStringFromGUID"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlStringFromGUID
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlStringFromGUID function


## -description


The <b>RtlStringFromGUID</b> routine converts a given GUID from binary format into a Unicode string. 


## -parameters




### -param Guid [in]

Specifies the binary-format GUID to convert. 


### -param GuidString [out]

Pointer to a caller-supplied variable in which a pointer to the converted GUID string is returned. <b>RtlStringFromGUID</b> allocates the buffer space for the string, which the caller must free by calling <b>RtlFreeUnicodeString</b>.  The returned string is in the form `{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}`, including the prepended and appended braces.


## -returns



If the conversion succeeds, <b>RtlStringFromGUID</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, nor was the conversion performed.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlguidfromstring">RtlGUIDFromString</a>
 

 

