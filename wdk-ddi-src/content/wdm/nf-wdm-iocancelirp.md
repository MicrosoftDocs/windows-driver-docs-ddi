---
UID: NF:wdm.IoCancelIrp
title: IoCancelIrp function
author: windows-driver-content
description: The IoCancelIrp routine sets the cancel bit in a given IRP and calls the cancel routine for the IRP if there is one.
old-location: kernel\iocancelirp.htm
old-project: kernel
ms.assetid: 8d991192-2df8-4b4d-a4c5-df5091492e67
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IoCancelIrp routine [Kernel-Mode Driver Architecture], k104_b43eae94-7d4e-4649-b56c-498285b5033f.xml, kernel.iocancelirp, IoCancelIrp, wdm/IoCancelIrp
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
req.ddi-compliance: HwStorPortProhibitedDDIs
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
-	IoCancelIrp
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoCancelIrp function


## -description


The <b>IoCancelIrp</b> routine sets the cancel bit in a given IRP and calls the cancel routine for the IRP if there is one.


## -syntax


````
BOOLEAN IoCancelIrp(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

A pointer to the IRP to be canceled.


## -returns



<b>IoCancelIrp</b> returns <b>TRUE</b> if the IRP had a cancel routine and this routine was called. Otherwise, it returns <b>FALSE</b>. In either case, the IRP's cancel bit is set to <b>TRUE</b>. For more information, see Remarks.




## -remarks



If the IRP has a cancel routine, <b>IoCancelIrp</b> sets the cancel bit and calls the cancel routine.

If <i>Irp</i>-&gt;<b>CancelRoutine</b> is <b>NULL</b>, and therefore the IRP is not cancelable, <b>IoCancelIrp</b> sets the IRP's cancel bit and returns <b>FALSE</b>. The IRP should be canceled at a later time when it becomes cancelable.

If a driver that does not own the IRP calls <b>IoCancelIrp</b>, the results are unpredictable. The IRP might be completed with a successful status even though its cancel bit was set.

An intermediate driver should not arbitrarily call <b>IoCancelIrp</b> unless that driver created the IRP passed in the call. Otherwise, the intermediate driver might cancel an IRP that some higher-level driver is tracking for purposes of its own.




## -see-also

<a href="..\wdm\nf-wdm-iosetcancelroutine.md">IoSetCancelRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCancelIrp routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

