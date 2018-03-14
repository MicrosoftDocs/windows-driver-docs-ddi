---
UID: NF:wdm.MmQuerySystemSize
title: MmQuerySystemSize function
author: windows-driver-content
description: The MmQuerySystemSize routine returns an estimate of the amount of memory in the system.
old-location: kernel\mmquerysystemsize.htm
old-project: kernel
ms.assetid: ca4b3154-e1a1-44d1-b085-9cb5d5ed1a4a
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmQuerySystemSize, MmQuerySystemSize routine [Kernel-Mode Driver Architecture], k106_9456af05-c1ea-43b0-a342-bc88a8de874b.xml, kernel.mmquerysystemsize, wdm/MmQuerySystemSize
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
-	MmQuerySystemSize
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmQuerySystemSize function


## -description


The <b>MmQuerySystemSize</b> routine returns an estimate of the amount of memory in the system.


## -syntax


````
MM_SYSTEMSIZE MmQuerySystemSize(void);
````


## -parameters






## -returns



<b>MmQuerySystemSize</b> returns one of <b>MmSmallSystem</b>, <b>MmMediumSystem</b>, or <b>MmLargeSystem</b>.




## -remarks



This routine can be called during driver initialization to determine how much memory it is practical to allocate for an internal buffer. 




## -see-also

<a href="..\ntddk\nf-ntddk-mmisthisanntassystem.md">MmIsThisAnNtAsSystem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmQuerySystemSize routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

