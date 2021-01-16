---
UID: NC:wdm.POB_PRE_OPERATION_CALLBACK
title: POB_PRE_OPERATION_CALLBACK (wdm.h)
description: The ObjectPreCallback routine is called by the operating system when a process or thread handle operation occurs.
old-location: kernel\objectprecallback.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["POB_PRE_OPERATION_CALLBACK callback function"]
ms.keywords: DrvrRtns_8ccbcf60-457d-4bd7-b059-423a47a44374.xml, ObjectPreCallback, ObjectPreCallback callback function [Kernel-Mode Driver Architecture], POB_PRE_OPERATION_CALLBACK, POB_PRE_OPERATION_CALLBACK callback, kernel.objectprecallback, wdm/ObjectPreCallback
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
 - POB_PRE_OPERATION_CALLBACK
 - wdm/POB_PRE_OPERATION_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - POB_PRE_OPERATION_CALLBACK
---

# POB_PRE_OPERATION_CALLBACK callback function


## -description

The <i>ObjectPreCallback</i> routine is called by the operating system when a process or thread handle operation occurs.

> [!WARNING]
> The actions that you can perform in this callback are restricted for safe calls. For more info, see [Windows Kernel-Mode Process and Thread Manager](/windows-hardware/drivers/kernel/windows-kernel-mode-process-and-thread-manager).

## -parameters

### -param RegistrationContext 

[in]
The context that the driver specifies as the <i>CallBackRegistration</i>-><b>RegistrationContext</b> parameter of the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a> routine. The meaning of this value is driver-defined.

### -param OperationInformation 

[in]
A pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a> structure that specifies the parameters of the handle operation.

## -returns

<i>ObjectPreCallback</i> returns an OB_PREOP_CALLBACK_STATUS value. Drivers must return OB_PREOP_SUCCESS.

## -remarks

Use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a> routine to register an <i>ObjectPreCallback</i> routine, and use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obunregistercallbacks">ObUnRegisterCallbacks</a> routine to unregister the routine.

This routine is called at PASSIVE_LEVEL in an arbitrary thread context with normal kernel APCs disabled. Special kernel APCs are not disabled. For more information about APCs, see <a href="/windows-hardware/drivers/kernel/types-of-apcs">Types of APCs</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_pre_operation_information">OB_PRE_OPERATION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obregistercallbacks">ObRegisterCallbacks</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-obunregistercallbacks">ObUnRegisterCallbacks</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_post_operation_callback">ObjectPostCallback</a>

