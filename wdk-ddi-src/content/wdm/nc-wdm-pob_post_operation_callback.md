---
UID: NC:wdm.POB_POST_OPERATION_CALLBACK
title: POB_POST_OPERATION_CALLBACK
author: windows-driver-content
description: The ObjectPostCallback routine is called by the operating system after a process or thread handle operation occurs.
old-location: kernel\objectpostcallback.htm
old-project: kernel
ms.assetid: cfa73359-58bb-4260-ac16-08f57ead67bb
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.objectpostcallback, ObjectPostCallback, ObjectPostCallback callback function [Kernel-Mode Driver Architecture], ObjectPostCallback, POB_POST_OPERATION_CALLBACK, POB_POST_OPERATION_CALLBACK, wdm/ObjectPostCallback, DrvrRtns_f15a2608-233d-47af-84cc-eb5692a6fe9a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	ObjectPostCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# POB_POST_OPERATION_CALLBACK callback


## -description


The <i>ObjectPostCallback</i> routine is called by the operating system after a process or thread handle operation occurs.


## -prototype


````
POB_POST_OPERATION_CALLBACK ObjectPostCallback;

VOID ObjectPostCallback(
  _In_ PVOID                          RegistrationContext,
  _In_ POB_POST_OPERATION_INFORMATION OperationInformation
)
{ ... }
````


## -parameters




#### - RegistrationContext [in]

The context that the driver specifies as the <i>CallBackRegistration</i>-&gt;<b>RegistrationContext</b> parameter of the <a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a> routine. The meaning of this value is driver-defined.


#### - OperationInformation [in]

A pointer to an <a href="..\wdm\ns-wdm-_ob_post_operation_information.md">OB_POST_OPERATION_INFORMATION</a> structure that specifies the parameters of the handle operation.


## -returns


None



## -remarks


Use the <a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a> routine to register an <i>ObjectPostCallback</i> routine, and use the <a href="..\wdm\nf-wdm-obunregistercallbacks.md">ObUnRegisterCallbacks</a> routine to unregister the routine.

An <i>ObjectPostCallback</i> routine is called after an operation on a process handle or thread handle completes, whereas an <a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a> routine is called before the operation occurs. The <i>OperationInformation</i> parameter of the <i>ObjectPreCallback</i> routine is a pointer to an <a href="..\wdm\ns-wdm-_ob_pre_operation_information.md">OB_PRE_OPERATION_INFORMATION</a> structure, which contains information that you can modify. In contrast, the <i>OperationInformation</i> parameter of the <i>ObjectPostCallback</i> routine is a pointer to an <a href="..\wdm\ns-wdm-_ob_post_operation_information.md">OB_POST_OPERATION_INFORMATION</a> structure. The contents of this structure are informational and you cannot modify them.

This routine is called at PASSIVE_LEVEL in an arbitrary thread context with normal kernel APCs disabled. Special kernel APCs are not disabled. For more information about APCs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564853">Types of APCs</a>.



## -see-also

<a href="..\wdm\nc-wdm-pob_pre_operation_callback.md">ObjectPreCallback</a>

<a href="..\wdm\nf-wdm-obregistercallbacks.md">ObRegisterCallbacks</a>

<a href="..\wdm\ns-wdm-_ob_post_operation_information.md">OB_POST_OPERATION_INFORMATION</a>

<a href="..\wdm\nf-wdm-obunregistercallbacks.md">ObUnRegisterCallbacks</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POB_POST_OPERATION_CALLBACK callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

