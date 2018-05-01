---
UID: NF:wdm.RtlGUIDFromString
title: RtlGUIDFromString function
author: windows-driver-content
description: The RtlGUIDFromString routine converts the given Unicode string to a GUID in binary format.
old-location: kernel\rtlguidfromstring.htm
old-project: kernel
ms.assetid: 7bdfc781-93d6-4f49-95f1-46f102908ec5
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: RtlGUIDFromString, RtlGUIDFromString routine [Kernel-Mode Driver Architecture], k109_d6fe22b7-9d81-4024-819c-03bce65d3d14.xml, kernel.rtlguidfromstring, wdm/RtlGUIDFromString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlGUIDFromString
product: Windows
targetos: Windows
req.typenames: 
---

# RtlGUIDFromString function


## -description


The <b>RtlGUIDFromString</b> routine converts the given Unicode string to a GUID in binary format.


## -parameters




### -param GuidString [in]

Pointer to the buffered Unicode string to be converted to a GUID. 


### -param Guid [out]

Pointer to a caller-supplied variable in which the GUID is returned. 


## -returns



If the conversion succeeds, <b>RtlGUIDFromString</b> returns STATUS_SUCCESS. Otherwise, no conversion was done. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562871">RtlStringFromGUID</a>
 

 

