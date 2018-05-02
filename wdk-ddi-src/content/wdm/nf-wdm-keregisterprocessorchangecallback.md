---
UID: NF:wdm.KeRegisterProcessorChangeCallback
title: KeRegisterProcessorChangeCallback function
author: windows-driver-content
description: The KeRegisterProcessorChangeCallback routine registers a callback function with the operating system so that the operating system will notify the driver when a new processor is added to the hardware partition.
old-location: kernel\keregisterprocessorchangecallback.htm
old-project: kernel
ms.assetid: a10d54a2-39e4-4c90-ac91-28d31b3ebfb8
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeRegisterProcessorChangeCallback, KeRegisterProcessorChangeCallback routine [Kernel-Mode Driver Architecture], k105_794d8039-ab35-46e9-8a0d-a38c034f0263.xml, kernel.keregisterprocessorchangecallback, wdm/KeRegisterProcessorChangeCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeRegisterProcessorChangeCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeRegisterProcessorChangeCallback function


## -description


The <b>KeRegisterProcessorChangeCallback</b> routine registers a callback function with the operating system so that the operating system will notify the driver when a new processor is added to the hardware partition.


## -parameters




### -param CallbackFunction [in]

A pointer to a driver-supplied processor change callback function that is to be called by the operating system whenever a new processor is added to the hardware partition. A processor change callback function is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
  ProcessorCallback(
    __in PVOID CallbackContext,
    __in PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT ChangeContext,
    __inout PNTSTATUS OperationStatus
    );</pre>
</td>
</tr>
</table></span></div>




#### CallbackContext

The context that was supplied in the <i>CallbackContext</i> parameter to the <b>KeRegisterProcessorChangeCallback</b> routine when the callback function was registered with the operating system.



#### ChangeContext

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that describes the processor change notification event.



#### OperationStatus

A pointer to a variable that contains an NTSTATUS code. A device driver must not change the value of this variable except if an error occurs during the processing of the callback function when the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that is pointed to by the <i>ChangeContext</i> parameter contains <b>KeProcessorAddStartNotify</b>.

The processor change callback function is called at IRQL = PASSIVE_LEVEL.


### -param CallbackContext [in, optional]

A driver-supplied context that is passed to the callback function. This parameter can be <b>NULL</b>.


### -param Flags [in]

Optional flags that modify the behavior of the <b>KeRegisterProcessorChangeCallback</b> routine. The following is one possible flag:





#### KE_PROCESSOR_CHANGE_ADD_EXISTING

If this flag is set, the registered callback function is immediately called for each active processor that currently exists in the hardware partition, in addition to being called whenever a new processor is added to the hardware partition. If this flag is not set, the registered callback function is only called whenever a new processor is added to the system.


## -returns



<b>KeRegisterProcessorChangeCallback</b> returns a non-<b>NULL</b> callback registration handle if the callback function is successfully registered with the operating system. Otherwise, <b>KeRegisterProcessorChangeCallback</b> returns <b>NULL</b>. For more information about this handle, see the following Remarks section.




## -remarks



A device driver calls the <b>KeRegisterProcessorChangeCallback</b> routine to register a callback function that is to be called by the operating system whenever a new processor is added to the hardware partition. When a user hot-plugs a new processor into the partition, the operating system calls the registered callback functions to rebalance the system resources that are allocated among the processors in the partition.

The registered callback function is called two times whenever a new processor is added to the hardware partition. The first time that the callback function is called, the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that is pointed to by the <i>ChangeContext</i> parameter contains <b>KeProcessorAddStartNotify</b>. It is during this callback that the device driver should allocate any per-processor resources and perform any other tasks in preparation for the new processor to become active in the hardware partition. If an error occurs while the device driver processes this callback that could cause a bugcheck to occur if the operating system continues to add the new processor to the hardware partition, the callback function sets the variable that is pointed to by the <i>OperationStatus</i> parameter to an NTSTATUS code that describes the error condition. For example, if the device driver experiences a memory allocation failure for a per-processor data structure for a new processor, the callback function sets this variable to STATUS_INSUFFICIENT_RESOURCES. If the callback is processed successfully, the contents of the variable that is pointed to by the <i>OperationStatus</i> parameter should not be changed.

The second time that the callback function is called, the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that is pointed to by the <i>ChangeContext</i> parameter contains either <b>KeProcessorAddCompleteNotify</b>, which indicates that the operating system has added the new processor to the hardware partition successfully, or <b>KeProcessorAddFailureNotify</b>, which indicates that the operating system did not add the new processor to the hardware partition. If the operating system successfully adds the new processor to the hardware partition, the callback function is not called the second time until after the new processor has been started and is available for thread scheduling. If the operating system did not add the new processor to the hardware partition, the device driver should free any per-processor resources during the second callback that it allocated during the first callback.

If the device driver specifies the KE_PROCESSOR_CHANGE_ADD_EXISTING flag in the <i>Flags</i> parameter when it calls the <b>KeRegisterProcessorChangeCallback</b> routine, the callback function is immediately called one time for each active processor that currently exists in the hardware partition. For these callbacks, the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that is pointed to by the <i>ChangeContext</i> parameter contains <b>KeProcessorAddStartNotify</b>. It is during these callbacks that the device driver should allocate any per-processor resources and perform any other tasks to prepare to use the existing processors in the hardware partition. If the device driver successfully processes this callback for all active processors that currently exist in the hardware partition, the callback function is immediately called again for each active processor that currently exists in the hardware partition. For these callbacks, the <b>State</b> member of the <b>KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</b> structure that is pointed to by the <i>ChangeContext</i> parameter contains <b>KeProcessorAddCompleteNotify</b>. <b>KeRegisterProcessorChangeCallback</b> returns after these callbacks complete.

If an error occurs while the device driver processes the first callback for one of the existing active processors in the hardware partition that could cause a bugcheck to occur if the driver were to continue to load, the callback function sets the variable pointed to by the <i>OperationStatus</i> parameter to an NTSTATUS code that describes the error condition. For example, if the device driver experiences a memory allocation failure for a per-processor data structure for an existing active processor, the callback function sets this variable to STATUS_INSUFFICIENT_RESOURCES. If the callback is processed successfully, the contents of the variable that is pointed to by the <i>OperationStatus</i> parameter should not be changed.

If the device driver indicates an error when the first callback for one of the existing active processors in the hardware partition is processed, the callback function is not called for any more of the existing active processors. Instead, the callback function is immediately called a second time for each active processor for which the callback was called the first time, excluding the active processor for which the callback indicated the error. For these callbacks, the <b>State</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a> structure that is pointed to by the <i>ChangeContext</i> parameter contains <b>KeProcessorAddFailureNotify</b>.

A device driver typically calls the <b>KeRegisterProcessorChangeCallback</b> routine from within its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine. If the call to the <b>KeRegisterProcessorChangeCallback</b> routine returns <b>NULL</b>, the device driver's <b>DriverEntry</b> routine should return an NTSTATUS code that describes the error condition.

<div class="alert"><b>Note</b>    A device driver can use the context that is passed in the <i>CallbackContext</i> parameter to the <b>KeRegisterProcessorChangeCallback</b> routine as a place where the callback function can store the NTSTATUS code that describes the error condition. This NTSTATUS code can then be used as the return value for the device driver's <b>DriverEntry</b> routine.</div>
<div> </div>
<div class="alert"><b>Note</b>  The status value returned by <b>KeRegisterProcessorChangeCallback</b> indicates only whether the registration of the callback function succeeds or fails. It does not indicate the success or failure of any calls to callback functions that might occur before <b>KeRegisterProcessorChangeCallback</b> returns.</div>
<div> </div>
A callback function that has been registered for notification of processor changes must be unregistered before the device driver is unloaded from the operating system. To unregister the callback function, the device driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552015">KeDeregisterProcessorChangeCallback</a> routine, and passes, as an input parameter to this routine, the registration handle that was returned by the call to the <b>KeRegisterProcessorChangeCallback</b> routine. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554229">KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552015">KeDeregisterProcessorChangeCallback</a>
 

 

