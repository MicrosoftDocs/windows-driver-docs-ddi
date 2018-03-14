---
UID: NF:wdm.MmSizeOfMdl
title: MmSizeOfMdl function
author: windows-driver-content
description: The MmSizeOfMdl routine returns the number of bytes to allocate for an MDL describing a given address range.
old-location: kernel\mmsizeofmdl.htm
old-project: kernel
ms.assetid: 83e7d4be-df76-4dc8-a8e2-91d279127ef1
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmSizeOfMdl, MmSizeOfMdl routine [Kernel-Mode Driver Architecture], k106_7cddc848-8b01-4a6a-b5b1-977f2386fc21.xml, kernel.mmsizeofmdl, wdm/MmSizeOfMdl
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
-	MmSizeOfMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmSizeOfMdl function


## -description


The <b>MmSizeOfMdl</b> routine returns the number of bytes to allocate for an MDL describing a given address range.


## -syntax


````
SIZE_T MmSizeOfMdl(
  _In_ PVOID  Base,
  _In_ SIZE_T Length
);
````


## -parameters




### -param Base [in]

Pointer to the base virtual address for the range. 


### -param Length [in]

Supplies the size, in bytes, of the range. 


## -returns



<b>MmSizeOfMdl</b> returns the number of bytes required to contain the MDL. 




## -remarks



Memory for the MDL itself must be allocated from nonpaged pool. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554500">MmCreateMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554568">MmInitializeMdl</a>



 

 


