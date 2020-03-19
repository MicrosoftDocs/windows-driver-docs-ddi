---
UID: NF:wdm.IoCsqInitializeEx
title: IoCsqInitializeEx function (wdm.h)
description: The IoCsqInitializeEx routine initializes the dispatch table for a cancel-safe IRP queue.
old-location: kernel\iocsqinitializeex.htm
tech.root: kernel
ms.assetid: 9f6501c2-a708-4583-a821-e1b8264ff0af
ms.date: 04/30/2018
keywords: ["IoCsqInitializeEx function"]
ms.keywords: IoCsqInitializeEx, IoCsqInitializeEx routine [Kernel-Mode Driver Architecture], k104_68bf2330-ba47-4896-8052-41afee2d887e.xml, kernel.iocsqinitializeex, wdm/IoCsqInitializeEx
f1_keywords:
 - "wdm/IoCsqInitializeEx"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoCsqInitializeEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoCsqInitializeEx function


## -description


The <b>IoCsqInitializeEx</b> routine initializes the dispatch table for a cancel-safe IRP queue.


## -parameters




### -param Csq [out]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a> structure to be initialized by <b>IoCsqInitializeEx</b>. 


### -param CsqInsertIrp [in]

Pointer to the driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a> function for the driver's cancel-safe IRP queue.


### -param CsqRemoveIrp [in]

Pointer to the driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a> function for the driver's cancel-safe IRP queue.


### -param CsqPeekNextIrp [in]

Pointer to the driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a> function for the driver's cancel-safe IRP queue.


### -param CsqAcquireLock [in]

Pointer to the driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a> function for the driver's cancel-safe IRP queue.


### -param CsqReleaseLock [in]

Pointer to the driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a> function for the driver's cancel-safe IRP queue.


### -param CsqCompleteCanceledIrp [in]

Pointer to the driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a> function for the driver's cancel-safe IRP queue.


## -returns



<b>IoCsqInitializeEx</b> returns STATUS_SUCCESS on success, or the appropriate error code on failure.




## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitialize">IoCsqInitialize</a> and <b>IoCsqInitializeEx</b> routines initialize an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a> structure that describes a driver's cancel-safe IRP queue. You can use <b>IoCsqInitializeEx</b> to specify an IRP queue with extended capabilities instead of one specified by <b>IoCsqInitialize</b>:

<ul>
<li>
The driver implements a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a> routine rather than a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a> routine. <i>CsqInsertIrpEx</i> takes an additional parameter, <i>InsertContext</i>. When the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a> to insert the IRP, it specifies the value that is passed as <i>InsertContext</i>. 

</li>
<li>
<b>IoCsqInsertIrpEx</b> returns the return value of <i>CsqInsertIrpEx</i>. Drivers can use the return value to indicate whether an insert operation succeeded or failed.

</li>
</ul>
Otherwise, the effect of <b>IoCsqInitializeEx</b> is identical to that of <b>IoCsqInitialize</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/cancel-safe-irp-queues">Cancel-Safe IRP Queues</a>.

Note that <b>IoCsq<i>Xxx</i></b> routines use the <b>DriverContext</b>[3] member of the IRP to hold IRP context information. Drivers that use these routines to queue IRPs must leave that member unused.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_acquire_lock">CsqAcquireLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_complete_canceled_irp">CsqCompleteCanceledIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp">CsqInsertIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_insert_irp_ex">CsqInsertIrpEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_peek_next_irp">CsqPeekNextIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_release_lock">CsqReleaseLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-io_csq_remove_irp">CsqRemoveIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">IO_CSQ_IRP_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinitializeex">IoCsqInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirp">IoCsqInsertIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqinsertirpex">IoCsqInsertIrpEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremoveirp">IoCsqRemoveIrp</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocsqremovenextirp">IoCsqRemoveNextIrp</a>
 

 

