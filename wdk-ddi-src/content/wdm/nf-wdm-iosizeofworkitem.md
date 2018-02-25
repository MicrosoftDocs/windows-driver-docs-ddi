---
UID: NF:wdm.IoSizeofWorkItem
title: IoSizeofWorkItem function
author: windows-driver-content
description: The IoSizeofWorkItem routine returns the size, in bytes, of an IO_WORKITEM structure.
old-location: kernel\iosizeofworkitem.htm
old-project: kernel
ms.assetid: 389f0776-1010-4f3c-b5c5-b8807ff07130
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , I, IoSizeofWorkItem, IoSizeofWorkItem routine [Kernel-Mode Driver Architecture], S, W, e, f, i, k, k104_9f2b3349-cd46-48ec-bcff-10e91bd522b5.xml, kernel.iosizeofworkitem, m, o, r, t, wdm/IoSizeofWorkItem, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoSizeofWorkItem
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoSizeofWorkItem function


## -description


The <b>IoSizeofWorkItem</b> routine returns the size, in bytes, of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure. 


## -syntax


````
ULONG IoSizeofWorkItem(void);
````


## -parameters






## -returns



<b>IoSizeofWorkItem</b> returns the number of bytes necessary to hold an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure.




## -remarks



For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>



<a href="..\wdm\nf-wdm-ioinitializeworkitem.md">IoInitializeWorkItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSizeofWorkItem routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

