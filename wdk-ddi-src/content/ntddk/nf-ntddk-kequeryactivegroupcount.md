---
UID: NF:ntddk.KeQueryActiveGroupCount
title: KeQueryActiveGroupCount function
author: windows-driver-content
description: The KeQueryActiveGroupCount routine returns the number of active processor groups in a multiprocessor system.
old-location: kernel\kequeryactivegroupcount.htm
old-project: kernel
ms.assetid: a5447dd8-6a4f-4686-b4e3-7deb4b61ff92
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: KeQueryActiveGroupCount, KeQueryActiveGroupCount routine [Kernel-Mode Driver Architecture], k105_29b5c7ca-1596-4a3e-8cda-20c6ccec4ebb.xml, kernel.kequeryactivegroupcount, wdm/KeQueryActiveGroupCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryActiveGroupCount
product: Windows
targetos: Windows
req.typenames: 
---

# KeQueryActiveGroupCount function


## -description


The <b>KeQueryActiveGroupCount</b> routine returns the number of active processor groups in a multiprocessor system.


## -parameters






## -returns



<b>KeQueryActiveGroupCount</b> returns a count of the active groups.




## -remarks



A processor group is active if it contains one or more active logical processors.

An active logical processor is a logical processor that Windows has started up and added to a multiprocessor system. The term <i>active processor</i> applies to a processor that is available to perform processing work, regardless of whether the processor is currently performing processing work or is idle. In some systems, the number of active processors might remain unchanged from system startup to shutdown. In other systems, Windows might dynamically add active processors while the system is running. Windows never removes active processors from a system.

Thus, the number of active processors in a multiprocessor system can increase between system startup and shutdown, but this number never decreases. Similarly, the number of active groups in the system can increase if a processor is dynamically added to an inactive group while the system is running. The number of active groups never decreases.

In contrast, the value that is returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff553035">KeQueryMaximumGroupCount</a> remains constant during runtime. This value is the maximum number of groups that the system can have.

Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a> routine to determine the number of active logical processors in a particular group.

Windows 7 is the first version of Windows to support processor groups. In Windows 7, only 64-bit versions of Windows support multiple groups; 32-bit versions of Windows support only one group. If a multiprocessor system is running a 64-bit version of Windows and contains no more than 64 logical processors, Windows assigns all processors to group 0. A multiprocessor system that is running a 32-bit version of Windows can contain no more than 32 processors.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553035">KeQueryMaximumGroupCount</a>
 

 

