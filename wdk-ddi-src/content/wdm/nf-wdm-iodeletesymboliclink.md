---
UID: NF:wdm.IoDeleteSymbolicLink
title: IoDeleteSymbolicLink function
description: The IoDeleteSymbolicLink routine removes a symbolic link from the system.
old-location: kernel\iodeletesymboliclink.htm
tech.root: kernel
ms.assetid: 68ad19a5-4694-4b75-8062-75b06bdc16ed
ms.date: 04/30/2018
ms.keywords: IoDeleteSymbolicLink, IoDeleteSymbolicLink routine [Kernel-Mode Driver Architecture], k104_6ff2f570-3573-4d12-b338-cca69515ef1a.xml, kernel.iodeletesymboliclink, wdm/IoDeleteSymbolicLink
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive4, PowerIrpDDis, HwStorPortProhibitedDDIs
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
-	IoDeleteSymbolicLink
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoDeleteSymbolicLink function


## -description


The <b>IoDeleteSymbolicLink</b> routine removes a symbolic link from the system.


## -parameters




### -param SymbolicLinkName [in]

Pointer to a buffered Unicode string that is the user-visible name for the symbolic link. 


## -returns



<b>IoDeleteSymbolicLink</b> returns STATUS_SUCCESS if the symbolic link object is deleted.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549043">IoCreateSymbolicLink</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549050">IoCreateUnprotectedSymbolicLink</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549076">IoDeassignArcName</a>
 

 

