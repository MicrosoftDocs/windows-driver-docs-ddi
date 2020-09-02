---
UID: NF:wdm.ExSetFirmwareEnvironmentVariable
title: ExSetFirmwareEnvironmentVariable function (wdm.h)
description: The ExSetFirmwareEnvironmentVariable routine sets the value of the specified system firmware environment variable.
old-location: kernel\exsetfirmwareenvironmentvariable.htm
tech.root: kernel
ms.assetid: 04447D92-EB9E-400B-A018-E70B186EA3DB
ms.date: 04/30/2018
keywords: ["ExSetFirmwareEnvironmentVariable function"]
ms.keywords: ExSetFirmwareEnvironmentVariable, ExSetFirmwareEnvironmentVariable routine [Kernel-Mode Driver Architecture], kernel.exsetfirmwareenvironmentvariable, wdm/ExSetFirmwareEnvironmentVariable
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExSetFirmwareEnvironmentVariable
 - wdm/ExSetFirmwareEnvironmentVariable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExSetFirmwareEnvironmentVariable
---

# ExSetFirmwareEnvironmentVariable function


## -description

The <b>ExSetFirmwareEnvironmentVariable</b> routine sets the value of the specified system firmware environment variable.

## -parameters

### -param VariableName 

[in]
A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the specified environment variable.

### -param VendorGuid 

[in]
A pointer to a GUID that identifies the vendor associated with the specified environment variable. Environment variables are grouped into namespaces based on their vendor GUIDs. Some hardware platforms might not support vendor GUIDs. On these platforms, all variables are grouped into one, common namespace, and the <i>VendorGuid</i> parameter is ignored.

### -param Value 

[in]
A pointer to a caller-allocated buffer that contains the data value to write to the specified environment variable.

### -param ValueLength 

[in]
The size, in bytes, of the data value contained in the <i>Value</i> buffer.

### -param Attributes 

[in]
The attributes to assign to the specified environment variable. The VARIABLE_ATTRIBUTE_NON_VOLATILE attribute bit must be set or this call will fail. For more information about the attribute bits that are defined for this parameter, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetfirmwareenvironmentvariable">ExGetFirmwareEnvironmentVariable</a>.

## -returns

<b>ExSetFirmwareEnvironmentVariable</b> returns STATUS_SUCCESS if it is successful. Possible return values include the following error status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Available system resources are insufficient to complete the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This routine is not supported on this platform.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The firmware returned an unrecognized error.

</td>
</tr>
</table>

## -remarks

The caller requires the system environment privilege (SE_SYSTEM_ENVIRONMENT_PRIVILEGE) to use this routine.

System firmware environment variables contain data values that are passed between the boot firmware environment implemented in the hardware platform and the operating-system loaders and other software that runs in the firmware environment.  For more information, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetfirmwareenvironmentvariable">ExGetFirmwareEnvironmentVariable</a>.

If you create a backup datastore, you can use the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetfirmwareenvironmentvariable">ExGetFirmwareEnvironmentVariable</a> routine to save all the boot settings for the platform. Later, you can use <b>ExSetFirmwareEnvironmentVariable</b> to restore these settings if needed.

<b>ExSetFirmwareEnvironmentVariable</b> is the kernel-mode equivalent of the Win32 <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-setfirmwareenvironmentvariablea">SetFirmwareEnvironmentVariable</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetfirmwareenvironmentvariable">ExGetFirmwareEnvironmentVariable</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-setfirmwareenvironmentvariablea">SetFirmwareEnvironmentVariable</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>

