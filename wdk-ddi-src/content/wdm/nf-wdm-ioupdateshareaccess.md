---
UID: NF:wdm.IoUpdateShareAccess
title: IoUpdateShareAccess function
author: windows-driver-content
description: The IoUpdateShareAccess routine updates the share access for the given file object, usually when the file is being opened.
old-location: kernel\ioupdateshareaccess.htm
old-project: kernel
ms.assetid: b8e14607-a8d4-4e15-8b1d-92096879ea65
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k104_24b78a73-20f1-4d8b-be0e-67964e8dbc31.xml, IoUpdateShareAccess, kernel.ioupdateshareaccess, IoUpdateShareAccess routine [Kernel-Mode Driver Architecture], wdm/IoUpdateShareAccess
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
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoUpdateShareAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoUpdateShareAccess function


## -description


The <b>IoUpdateShareAccess</b> routine updates the share access for the given file object, usually when the file is being opened.


## -syntax


````
VOID IoUpdateShareAccess(
  _In_    PFILE_OBJECT  FileObject,
  _Inout_ PSHARE_ACCESS ShareAccess
);
````


## -parameters




### -param FileObject [in]

Pointer to a referenced file object representing the file or associated device object for which to update the share access.


### -param ShareAccess [in, out]

Pointer to the common <b>SHARE_ACCESS</b> structure associated with the <i>FileObject</i>. Drivers should treat this structure as opaque.


## -returns



None




## -remarks



<b>IoUpdateShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoUpdateShareAccess </b>by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Before calling <b>IoUpdateShareAccess</b>, the caller must successfully call <b>IoCheckShareAccess</b> with <i>Update</i> set to False. Such a call to <b>IoCheckShareAccess</b> determines whether the requested shared access is compatible with the way the file object is currently being accessed by other opens, but it does not update the <b>SHARE_ACCESS</b> structure. <b>IoUpdateShareAccess</b> actually updates the <b>SHARE_ACCESS</b> structure associated with the file object. 




## -see-also

<a href="..\wdm\nf-wdm-iosetshareaccess.md">IoSetShareAccess</a>



<a href="..\wdm\nf-wdm-iocheckshareaccess.md">IoCheckShareAccess</a>



<a href="..\wdm\nf-wdm-iosetshareaccess.md">IoSetShareAccess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUpdateShareAccess routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

