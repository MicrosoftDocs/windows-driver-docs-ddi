---
UID: NF:ntifs.FsRtlDeregisterUncProvider
title: FsRtlDeregisterUncProvider function
author: windows-driver-content
description: The FsRtlDeregisterUncProvider routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).
old-location: ifsk\fsrtlderegisteruncprovider.htm
old-project: ifsk
ms.assetid: 3f53a22f-b5d6-4e3d-987d-989bd5840b2a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlDeregisterUncProvider, FsRtlDeregisterUncProvider routine [Installable File System Drivers], fsrtlref_d1eb1778-7643-44df-8f68-edc995b22246.xml, ifsk.fsrtlderegisteruncprovider, ntifs/FsRtlDeregisterUncProvider
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlDeregisterUncProvider
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlDeregisterUncProvider function


## -description


The <b>FsRtlDeregisterUncProvider</b> routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP).


## -parameters




### -param Handle [in]

MUP handle returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547178">FsRtlRegisterUncProvider</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547184">FsRtlRegisterUncProviderEx</a>.


## -returns



None




## -remarks



To register a UNC provider on Windows Server 2003, Windows XP, or Windows 2000, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547178">FsRtlRegisterUncProvider</a>. 

To register a UNC provider on Windows Vista, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547184">FsRtlRegisterUncProviderEx</a>.

For more information, see the following sections in the Design Guide:


<a href="https://msdn.microsoft.com/07c4a498-10c7-41b2-aaeb-73cab946f392">Support for UNC Naming and MUP</a>



<a href="https://msdn.microsoft.com/8ca2f9bc-14f1-45d3-a397-f3e5459cf8ec">MUP Changes in Microsoft Windows Vista</a>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547178">FsRtlRegisterUncProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547184">FsRtlRegisterUncProviderEx</a>
 

 

