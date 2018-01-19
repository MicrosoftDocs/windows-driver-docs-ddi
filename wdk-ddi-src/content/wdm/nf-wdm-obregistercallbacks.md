---
UID: NF:wdm.ObRegisterCallbacks
title: ObRegisterCallbacks function
author: windows-driver-content
description: The ObRegisterCallbacks routine registers a list of callback routines for thread, process, and desktop handle operations.
old-location: kernel\obregistercallbacks.htm
old-project: kernel
ms.assetid: 93593979-fe5f-48de-9c98-92acd43ec750
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ObRegisterCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with Service Pack 1 (SP1) and Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ObRegisterCallbacks
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ObRegisterCallbacks function



## -description
The <b>ObRegisterCallbacks</b> routine registers a list of callback routines for thread, process, and desktop handle operations.



## -syntax

````
NTSTATUS ObRegisterCallbacks(
  _In_  POB_CALLBACK_REGISTRATION CallBackRegistration,
  _Out_ PVOID                     *RegistrationHandle
);
````


## -parameters

### -param CallBackRegistration [in]

A pointer to an <a href="..\wdm\ns-wdm-_ob_callback_registration.md">OB_CALLBACK_REGISTRATION</a> structure that specifies the list of callback routines and other registration information.


### -param RegistrationHandle [out]

A pointer to a variable that receives a value that identifies the set of registered callback routines. The caller passes this value to the <a href="..\wdm\nf-wdm-obunregistercallbacks.md">ObUnRegisterCallbacks</a> routine to unregister the set of callbacks. 


## -returns
<b>ObRegisterCallbacks</b> returns an NTSTATUS value. This routine might return one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The specified callback routines are registered with the system.
<dl>
<dt><b>STATUS_FLT_INSTANCE_ALTITUDE_COLLISION</b></dt>
</dl>The calling driver or another driver has already registered callback routines for the altitude that <i>CallBackRegistration</i>-&gt;<b>Altitude</b> specifies. For more information about this altitude, see the description of the <b>Altitude</b> member in <a href="..\wdm\ns-wdm-_ob_callback_registration.md">OB_CALLBACK_REGISTRATION</a>.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One or more of the parameters that were specified in the registration was invalid. <b>ObRegisterCallbacks</b> might return this error, for example, if an invalid value for <i>CallBackRegistration</i>-&gt;<b>Version</b> is specified or if registration is attempted for object types that do not support callback routines.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The callback routines do not reside in a signed kernel binary image.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>An attempt to allocate memory failed.

 


## -remarks
A driver must unregister all callback routines before it unloads. You can unregister the callback routine by calling the <b>ObUnRegisterCallbacks</b> routine.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_ob_callback_registration.md">OB_CALLBACK_REGISTRATION</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-obunregistercallbacks.md">ObUnRegisterCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ObRegisterCallbacks routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

