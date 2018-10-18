---
UID: NF:wdm.IoCsqInitialize
title: IoCsqInitialize function
author: windows-driver-content
description: The IoCsqInitialize routine initializes the driver's cancel-safe IRP queue dispatch table.
old-location: kernel\iocsqinitialize.htm
tech.root: kernel
ms.assetid: 5287db75-3096-45ab-b35b-1ee8b076157d
ms.date: 4/30/2018
ms.keywords: IoCsqInitialize, IoCsqInitialize routine [Kernel-Mode Driver Architecture], k104_08afe4e8-f68d-4490-86ec-a558b2090a82.xml, kernel.iocsqinitialize, wdm/IoCsqInitialize
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system. Drivers that must also work for Windows 2000 and Windows 98/Me can instead link to Csq.lib to use the routine.
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
-	IoCsqInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCsqInitialize function


## -description


The <b>IoCsqInitialize</b> routine initializes the driver's cancel-safe IRP queue dispatch table.


## -parameters




### -param Csq [out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure to be initialized by <b>IoCsqInitialize</b>.


### -param CsqInsertIrp [in]

Pointer to the driver-defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff542947">CsqInsertIrp</a> function for the driver's cancel-safe IRP queue.


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



This routine returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.




## -remarks



The <b>IoCsqInitialize</b> routine initializes an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550560">IO_CSQ</a> structure that describes a driver's cancel-safe IRP queue. Drivers can also use <a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a> to create an IRP queue with extended capabilities. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540755">Cancel-Safe IRP Queues</a>.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549060">IoCsqInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549066">IoCsqInsertIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549067">IoCsqInsertIrpEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549070">IoCsqRemoveIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549072">IoCsqRemoveNextIrp</a>
 

 

