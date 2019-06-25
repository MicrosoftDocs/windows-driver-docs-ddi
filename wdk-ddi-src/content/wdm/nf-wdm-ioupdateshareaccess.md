---
UID: NF:wdm.IoUpdateShareAccess
title: IoUpdateShareAccess function (wdm.h)
description: The IoUpdateShareAccess routine updates the share access for the given file object, usually when the file is being opened.
old-location: kernel\ioupdateshareaccess.htm
tech.root: kernel
ms.assetid: b8e14607-a8d4-4e15-8b1d-92096879ea65
ms.date: 04/30/2018
ms.keywords: IoUpdateShareAccess, IoUpdateShareAccess routine [Kernel-Mode Driver Architecture], k104_24b78a73-20f1-4d8b-be0e-67964e8dbc31.xml, kernel.ioupdateshareaccess, wdm/IoUpdateShareAccess
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoUpdateShareAccess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoUpdateShareAccess function


## -description


The <b>IoUpdateShareAccess</b> routine updates the share access for the given file object, usually when the file is being opened.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocheckshareaccess">IoCheckShareAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioremoveshareaccess">IoRemoveShareAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iosetshareaccess">IoSetShareAccess</a>
 

 

