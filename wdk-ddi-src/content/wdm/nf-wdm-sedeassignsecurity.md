---
UID: NF:wdm.SeDeassignSecurity
title: SeDeassignSecurity function
author: windows-driver-content
description: The SeDeassignSecurity routine deallocates the memory associated with a security descriptor that was assigned using SeAssignSecurity.
old-location: kernel\sedeassignsecurity.htm
tech.root: kernel
ms.assetid: c7060b86-8ff6-4229-94e0-7965ae59aa90
ms.date: 4/30/2018
ms.keywords: SeDeassignSecurity, SeDeassignSecurity routine [Kernel-Mode Driver Architecture], k110_9c1ca048-addd-4343-bfee-34e905b143b3.xml, kernel.sedeassignsecurity, wdm/SeDeassignSecurity
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	SeDeassignSecurity
product:
- Windows
targetos: Windows
req.typenames: 
---

# SeDeassignSecurity function


## -description


The  
   <b>SeDeassignSecurity</b> routine deallocates the memory associated with a security descriptor that was assigned using <b>SeAssignSecurity</b>.


## -parameters




### -param SecurityDescriptor [in, out]

Pointer to the buffered <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> being released.


## -returns



If the deallocation succeeds, <b>SeDeassignSecurity</b> returns STATUS_SUCCESS.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563676">SeAssignSecurity</a>
 

 

