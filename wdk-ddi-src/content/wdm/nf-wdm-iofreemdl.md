---
UID: NF:wdm.IoFreeMdl
title: IoFreeMdl function
author: windows-driver-content
description: The IoFreeMdl routine releases a caller-allocated memory descriptor list (MDL).
old-location: kernel\iofreemdl.htm
old-project: kernel
ms.assetid: e984400a-b94f-4848-af56-79695b327404
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: wdm/IoFreeMdl, k104_30217ed4-82a6-4b6d-b6f6-77fab8faa867.xml, IoFreeMdl routine [Kernel-Mode Driver Architecture], IoFreeMdl, kernel.iofreemdl
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoFreeMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoFreeMdl function


## -description


The <b>IoFreeMdl</b> routine releases a caller-allocated memory descriptor list (MDL). 


## -syntax


````
VOID IoFreeMdl(
  _In_ PMDL Mdl
);
````


## -parameters




### -param Mdl [in]

Pointer to the MDL to be released. 


## -returns



None




## -remarks



If a driver allocates an MDL to describe a buffer, it must explicitly release the MDL when operations on the buffer are done.

If the MDL is a partial MDL, <b>IoFreeMdl</b> unmaps any pages that have been mapped to the MDL.

If the physical pages that are described by the MDL are locked, the driver must unlock the pages before it frees the MDL.

This routine frees only the specified MDL. Any MDLs that are chained to this MDL must be explicitly freed through additional calls to this routine. For a code example that shows how to free an MDL chain, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>. 




## -see-also

<a href="..\wdm\nf-wdm-iobuildpartialmdl.md">IoBuildPartialMdl</a>



<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoFreeMdl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

