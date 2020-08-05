---
UID: NS:wdm._KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT
title: _KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT (wdm.h)
description: The KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure describes the notification context that is passed to a registered callback function when a new processor is dynamically added to a hardware partition.
old-location: kernel\ke_processor_change_notify_context.htm
tech.root: kernel
ms.assetid: b8b8e2af-487c-4d7b-8af0-b6365d4703b0
ms.date: 04/30/2018
keywords: ["KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure"]
ms.keywords: "*PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure [Kernel-Mode Driver Architecture], PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure pointer [Kernel-Mode Driver Architecture], _KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, kernel.ke_processor_change_notify_context, kstruct_c_dcd6ab01-880a-4a63-bd74-acff53b786d1.xml, wdm/KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, wdm/PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT"
f1_keywords:
 - "wdm/KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT"
 - "KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Server 2008.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT
targetos: Windows
req.typenames: KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, *PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT
---

# _KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure


## -description


The <b>KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</b> structure describes the notification context that is passed to a registered callback function when a new processor is dynamically added to a hardware partition.


## -struct-fields




### -field State

The state of the processor add operation. Possible values are as follows:





#### KeProcessorAddStartNotify

The operating system is about to add the processor. At this state, a device driver that receives this notification can allocate any per-processor data structures and perform any other required tasks to prepare the driver for execution on the new processor.



#### KeProcessorAddCompleteNotify

The operating system has successfully added the processor. At this state, a device driver that receives this notification can start scheduling threads on the new processor.



#### KeProcessorAddFailureNotify

The operating system failed to add the processor. If a device driver receives this notification, it should free any per-processor data structures that it allocated for the new processor when it received the <b>KeProcessorAddStartNotify</b> notification.


### -field NtNumber

The processor index of the new processor. For information about the relationship between a processor index and a processor number, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetprocessornumberfromindex">KeGetProcessorNumberFromIndex</a>.


### -field Status

If the <b>State</b> member contains <b>KeProcessorAddFailureNotify</b>, this member contains the error status that indicates why the processor add operation failed.


### -field ProcNumber

The processor number of the new processor. This member is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a> structure that specifies a group number and a group-relative processor number.


## -remarks



The <b>KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</b> structure is available starting with Windows Server 2008.

A device driver registers to receive notification when a new processor is dynamically added to the hardware partition by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterprocessorchangecallback">KeRegisterProcessorChangeCallback</a> function. For more information about registering for this notification, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/registering-for-synchronous-driver-notification">Registering for Synchronous Driver Notification</a>.

When a new processor is dynamically added to the hardware partition, the operating system calls each registered callback function two times. The operating system calls each registered callback function the first time with the <b>KeProcessorAddStartNotify</b> state, and the second time with either the <b>KeProcessorAddCompleteNotify</b> state or the <b>KeProcessorAddFailureNotify</b> state.

A device driver's callback function that receives these notifications must not modify the contents of the <b>KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetprocessornumberfromindex">KeGetProcessorNumberFromIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keregisterprocessorchangecallback">KeRegisterProcessorChangeCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/miniport/ns-miniport-_processor_number">PROCESSOR_NUMBER</a>
 

 

