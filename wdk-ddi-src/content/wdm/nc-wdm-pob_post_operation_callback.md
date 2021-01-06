---
UID: NC:wdm.POB_POST_OPERATION_CALLBACK
title: POB_POST_OPERATION_CALLBACK (wdm.h)
description: The ObjectPostCallback routine is called by the operating system after a process or thread handle operation occurs.
old-location: kernel\objectpostcallback.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["POB_POST_OPERATION_CALLBACK callback function"]
ms.keywords: DrvrRtns_f15a2608-233d-47af-84cc-eb5692a6fe9a.xml, ObjectPostCallback, ObjectPostCallback callback function [Kernel-Mode Driver Architecture], POB_POST_OPERATION_CALLBACK, POB_POST_OPERATION_CALLBACK callback, kernel.objectpostcallback, wdm/ObjectPostCallback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Server 2008.
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
req.irql: Called at PASSIVE_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - POB_POST_OPERATION_CALLBACK
 - wdm/POB_POST_OPERATION_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - ObjectPostCallback
---

# POB_POST_OPERATION_CALLBACK callback function


## -description

The <i>ObjectPostCallback</i> routine is called by the operating system after a process or thread handle operation occurs.

> [!WARNING]
> The actions that you can perform in this callback are restricted for safe calls. For more info, see [Windows Kernel-Mode Process and Thread Manager](/windows-hardware/drivers/kernel/windows-kernel-mode-process-and-thread-manager).

## -parameters

### -param RegistrationContext 

[in]
The context that the driver specifies as the <i>CallBackRegistration</i>-><b>RegistrationContext</b> parameter of the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a> routine. The meaning of this value is driver-defined.

### -param OperationInformation 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_post_operation_information">OB_POST_OPERATION_INFORMATION</a> structure that specifies the parameters of the handle operation.

## -remarks

Use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a> routine to register an <i>ObjectPostCallback</i> routine, and use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obunregistercallbacks">ObUnRegisterCallbacks</a> routine to unregister the routine.

An <i>ObjectPostCallback</i> routine is called after an operation on a process handle or thread handle completes, whereas an <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_pre_operation_callback">ObjectPreCallback</a> routine is called before the operation occurs. The <i>OperationInformation</i> parameter of the <i>ObjectPreCallback</i> routine is a pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a> structure, which contains information that you can modify. In contrast, the <i>OperationInformation</i> parameter of the <i>ObjectPostCallback</i> routine is a pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_post_operation_information">OB_POST_OPERATION_INFORMATION</a> structure. The contents of this structure are informational and you cannot modify them.

This routine is called at PASSIVE_LEVEL in an arbitrary thread context with normal kernel APCs disabled. Special kernel APCs are not disabled. For more information about APCs, see <a href="/windows-hardware/drivers/kernel/types-of-apcs">Types of APCs</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_post_operation_information">OB_POST_OPERATION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obunregistercallbacks">ObUnRegisterCallbacks</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_pre_operation_callback">ObjectPreCallback</a>
