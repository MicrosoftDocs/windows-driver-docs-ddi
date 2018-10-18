---
UID: NF:wdm.ExDeleteResourceLite
title: ExDeleteResourceLite function
author: windows-driver-content
description: The ExDeleteResourceLite routine deletes a given resource from the system's resource list.
old-location: kernel\exdeleteresourcelite.htm
tech.root: kernel
ms.assetid: 83efb1eb-4c45-4bfc-84dd-88032e40076a
ms.date: 4/30/2018
ms.keywords: ExDeleteResourceLite, ExDeleteResourceLite routine [Kernel-Mode Driver Architecture], k102_92907ac3-1391-4ede-8ffa-71a211c7634e.xml, kernel.exdeleteresourcelite, wdm/ExDeleteResourceLite
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte3, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExDeleteResourceLite
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExDeleteResourceLite function


## -description


The <b>ExDeleteResourceLite</b> routine deletes a given resource from the system's resource list.


## -parameters




### -param Resource [in, out]

A pointer to the caller-supplied storage for the initialized resource variable to be deleted.


## -returns



<b>ExDeleteResourceLite</b> returns STATUS_SUCCESS if the resource was deleted.




## -remarks



After calling <b>ExDeleteResourceLite</b>, the caller can free the memory it allocated for its resource.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545317">ExInitializeResourceLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545542">ExReinitializeResourceLite</a>
 

 

