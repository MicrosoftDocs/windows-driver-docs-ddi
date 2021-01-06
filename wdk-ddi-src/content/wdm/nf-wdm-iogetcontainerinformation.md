---
UID: NF:wdm.IoGetContainerInformation
title: IoGetContainerInformation function (wdm.h)
description: The IoGetContainerInformation routine provides information about the current state of a user session.
old-location: kernel\iogetcontainerinformation.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoGetContainerInformation function"]
ms.keywords: IoGetContainerInformation, IoGetContainerInformation routine [Kernel-Mode Driver Architecture], k104_f139cf99-fd05-4f89-ac6e-ac9c88cc97b4.xml, kernel.iogetcontainerinformation, wdm/IoGetContainerInformation
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
 - IoGetContainerInformation
 - wdm/IoGetContainerInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetContainerInformation
---

# IoGetContainerInformation function


## -description

The <b>IoGetContainerInformation</b> routine provides information about the current state of a user session.

## -parameters

### -param InformationClass 

[in]
Specifies the class of events for which the caller (driver) requests information. Set this parameter to the following <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_container_information_class">IO_CONTAINER_INFORMATION_CLASS</a> enumeration value:

<ul>
<li>
<b>IoSessionStateInformation</b>

</li>
</ul>
For more information, see the following Remarks section.

### -param ContainerObject 

[in, optional]
A pointer to an opaque, system object supplied by the I/O manager. For <i>InformationClass</i> = <b>IoSessionStateInformation</b>, set this parameter to the <i>SessionObject</i> parameter value that is provided by the I/O manager during the call to the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-io_session_notification_function">IO_SESSION_NOTIFICATION_FUNCTION</a> function.

### -param Buffer 

[in, out]
A pointer to a caller-allocated buffer into which this routine writes the state information for the event class specified by <i>InformationClass</i>. For <i>InformationClass</i> = <b>IoSessionStateInformation</b>, the routine writes an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_session_state_information">IO_SESSION_STATE_INFORMATION</a> structure to the buffer. The buffer must be large enough to contain this structure.

### -param BufferLength 

[in]
The size, in bytes, of the buffer pointed to by <i>Buffer</i>. For <i>InformationClass</i> = IoSessionStateInformation, <i>BufferLength</i> must be at least <b>sizeof</b>(<b>IO_SESSION_STATE_INFORMATION</b>).

## -returns

<b>IoGetContainerInformation</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>InformationClass</i> is not a valid <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_container_information_class">IO_CONTAINER_INFORMATION_CLASS</a> enumeration constant.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>ContainerObject</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>BufferLength</i> is too small for the information class specified by <i>InformationClass</i>.

</td>
</tr>
</table>

## -remarks

This routine can potentially support queries for a variety of information classes. In Windows 7, this routine supports only queries for <b>IoSessionStateInformation</b> information, which is status information about user sessions.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_container_information_class">IO_CONTAINER_INFORMATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_io_container_notification_class">IO_CONTAINER_NOTIFICATION_CLASS</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_session_state_information">IO_SESSION_STATE_INFORMATION</a>
