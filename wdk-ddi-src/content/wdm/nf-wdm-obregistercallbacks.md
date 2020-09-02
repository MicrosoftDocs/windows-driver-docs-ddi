---
UID: NF:wdm.ObRegisterCallbacks
title: ObRegisterCallbacks function (wdm.h)
description: The ObRegisterCallbacks routine registers a list of callback routines for thread, process, and desktop handle operations.
old-location: kernel\obregistercallbacks.htm
tech.root: kernel
ms.assetid: 93593979-fe5f-48de-9c98-92acd43ec750
ms.date: 04/30/2018
keywords: ["ObRegisterCallbacks function"]
ms.keywords: ObRegisterCallbacks, ObRegisterCallbacks routine [Kernel-Mode Driver Architecture], k107_e5976812-0590-42f5-836c-85f9d262f19f.xml, kernel.obregistercallbacks, wdm/ObRegisterCallbacks
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista with Service Pack 1 (SP1) and Windows Server 2008.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ObRegisterCallbacks
 - wdm/ObRegisterCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ObRegisterCallbacks
---

# ObRegisterCallbacks function


## -description

The <b>ObRegisterCallbacks</b> routine registers a list of callback routines for thread, process, and desktop handle operations.

## -parameters

### -param CallbackRegistration 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_callback_registration">OB_CALLBACK_REGISTRATION</a> structure that specifies the list of callback routines and other registration information.

### -param RegistrationHandle 

[out]
A pointer to a variable that receives a value that identifies the set of registered callback routines. The caller passes this value to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obunregistercallbacks">ObUnRegisterCallbacks</a> routine to unregister the set of callbacks.

## -returns

<b>ObRegisterCallbacks</b> returns an NTSTATUS value. This routine might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The specified callback routines are registered with the system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INSTANCE_ALTITUDE_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
The calling driver or another driver has already registered callback routines for the altitude that <i>CallBackRegistration</i>-><b>Altitude</b> specifies. For more information about this altitude, see the description of the <b>Altitude</b> member in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_callback_registration">OB_CALLBACK_REGISTRATION</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One or more of the parameters that were specified in the registration was invalid. <b>ObRegisterCallbacks</b> might return this error, for example, if an invalid value for <i>CallBackRegistration</i>-><b>Version</b> is specified or if registration is attempted for object types that do not support callback routines.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The callback routines do not reside in a signed kernel binary image.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
An attempt to allocate memory failed.

</td>
</tr>
</table>

## -remarks

A driver must unregister all callback routines before it unloads. You can unregister the callback routine by calling the <b>ObUnRegisterCallbacks</b> routine.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_callback_registration">OB_CALLBACK_REGISTRATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obunregistercallbacks">ObUnRegisterCallbacks</a>

