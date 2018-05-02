---
UID: NF:wdm.IoCsqInitializeEx
title: IoCsqInitializeEx function
author: windows-driver-content
description: The IoCsqInitializeEx routine initializes the dispatch table for a cancel-safe IRP queue.
old-location: kernel\iocsqinitializeex.htm
old-project: kernel
ms.assetid: 9f6501c2-a708-4583-a821-e1b8264ff0af
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoCsqInitializeEx, IoCsqInitializeEx routine [Kernel-Mode Driver Architecture], k104_68bf2330-ba47-4896-8052-41afee2d887e.xml, kernel.iocsqinitializeex, wdm/IoCsqInitializeEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of the Windows operating system. The routine is also available in the Csq.lib library that ships with the Windows Driver Kit (WDK) and the Driver Development Kit (DDK) for Windows Server 2003. Drivers that must also work on Windows XP, Windows 2000, and Windows 98/Me can instead link to Csq.lib to use the routine.
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
-	IoCsqInitializeEx
product: Windows
targetos: Windows
req.typenames: 
---

# IoCsqInitializeEx function


## -description


The <b>IoCsqInitializeEx</b> routine initializes the dispatch table for a cancel-safe IRP queue.


## -parameters




### -param Csq [out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure to be initialized by <b>IoCsqInitializeEx</b>. 


### -param CsqInsertIrp [in]

Pointer to the driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff542956">CsqInsertIrpEx</a> function for the driver's cancel-safe IRP queue.


### -param CsqRemoveIrp [in]

Pointer to the driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff542968">CsqRemoveIrp</a> function for the driver's cancel-safe IRP queue.


### -param CsqPeekNextIrp [in]

Pointer to the driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff542959">CsqPeekNextIrp</a> function for the driver's cancel-safe IRP queue.


### -param CsqAcquireLock [in]

Pointer to the driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff542934">CsqAcquireLock</a> function for the driver's cancel-safe IRP queue.


### -param CsqReleaseLock [in]

Pointer to the driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a> function for the driver's cancel-safe IRP queue.


### -param CsqCompleteCanceledIrp [in]

Pointer to the driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff542940">CsqCompleteCanceledIrp</a> function for the driver's cancel-safe IRP queue.


## -returns



<b>IoCsqInitializeEx</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure.




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff549054">IoCsqInitialize</a> and <b>IoCsqInitializeEx</b> routines initialize an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure that describes a driver's cancel-safe IRP queue. You can use <b>IoCsqInitializeEx</b> to specify an IRP queue with extended capabilities instead of one specified by <b>IoCsqInitialize</b>:

<ul>
<li>
The driver implements a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542956">CsqInsertIrpEx</a> routine rather than a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542947">CsqInsertIrp</a> routine. <i>CsqInsertIrpEx</i> takes an additional parameter, <i>InsertContext</i>. When the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549067">IoCsqInsertIrpEx</a> to insert the IRP, it specifies the value that is passed as <i>InsertContext</i>. 

</li>
<li>
<b>IoCsqInsertIrpEx</b> returns the return value of <i>CsqInsertIrpEx</i>. Drivers can use the return value to indicate whether an insert operation succeeded or failed.

</li>
</ul>
Otherwise, the effect of <b>IoCsqInitializeEx</b> is identical to that of <b>IoCsqInitialize</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542934">CsqAcquireLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542940">CsqCompleteCanceledIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542947">CsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542956">CsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542959">CsqPeekNextIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542965">CsqReleaseLock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542968">CsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550567">IO_CSQ_IRP_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549066">IoCsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549067">IoCsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549070">IoCsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549072">IoCsqRemoveNextIrp</a>
 

 

