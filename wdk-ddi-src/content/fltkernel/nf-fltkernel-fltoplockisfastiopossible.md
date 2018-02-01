---
UID: NF:fltkernel.FltOplockIsFastIoPossible
title: FltOplockIsFastIoPossible function
author: windows-driver-content
description: The FltOplockIsFastIoPossible routine checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.
old-location: ifsk\fltoplockisfastiopossible.htm
old-project: ifsk
ms.assetid: 0b1a4e61-9e1f-4469-b8d3-a3b75667ee7e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltOplockIsFastIoPossible, fltkernel/FltOplockIsFastIoPossible, FltOplockIsFastIoPossible routine [Installable File System Drivers], ifsk.fltoplockisfastiopossible, FltApiRef_e_to_o_d80a24fe-5ca7-43e6-8e6f-cb9414c427c3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltOplockIsFastIoPossible
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltOplockIsFastIoPossible function


## -description


The <b>FltOplockIsFastIoPossible</b> routine checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. 


## -syntax


````
BOOLEAN FltOplockIsFastIoPossible(
  _In_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in]

Opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>. 


## -returns


<b>FltOplockIsFastIoPossible</b> returns <b>FALSE</b> if there are outstanding oplocks on the file that prevent fast I/O from being performed; <b>TRUE</b> otherwise. 



## -remarks


<b>FltOplockIsFastIoPossible</b> determines whether fast I/O can be performed on a file, according to the following conditions: 
<ul>
<li>
If the <i>Oplock</i> parameter is <b>NULL</b>, or if the value of *<i>Oplock</i> is <b>NULL</b>, there are no outstanding oplocks on the file, and fast I/O can be performed on the file. 

</li>
<li>
If an exclusive oplock was granted for the file, but no oplock break is in progress, fast I/O can be performed on the file. 

</li>
</ul>For detailed information about opportunistic locks, see the Windows SDK documentation. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>

<a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>

<a href="..\fltkernel\nf-fltkernel-fltcheckoplock.md">FltCheckOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>

<a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>

<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>

<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>

<a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOplockIsFastIoPossible routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

