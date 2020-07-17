---
UID: NF:wdm.ExGetFirmwareEnvironmentVariable
title: ExGetFirmwareEnvironmentVariable function (wdm.h)
description: The ExGetFirmwareEnvironmentVariable routine gets the value of the specified system firmware environment variable.
old-location: kernel\exgetfirmwareenvironmentvariable.htm
tech.root: kernel
ms.assetid: 5AD76955-A44C-4231-9394-0B6595CFB33D
ms.date: 04/30/2018
keywords: ["ExGetFirmwareEnvironmentVariable function"]
ms.keywords: ExGetFirmwareEnvironmentVariable, ExGetFirmwareEnvironmentVariable routine [Kernel-Mode Driver Architecture], kernel.exgetfirmwareenvironmentvariable, wdm/ExGetFirmwareEnvironmentVariable
f1_keywords:
 - "wdm/ExGetFirmwareEnvironmentVariable"
 - "ExGetFirmwareEnvironmentVariable"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExGetFirmwareEnvironmentVariable
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExGetFirmwareEnvironmentVariable function


## -description


The <b>ExGetFirmwareEnvironmentVariable</b> routine gets the value of the specified system firmware environment variable.


## -parameters




### -param VariableName [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of the specified environment variable.


### -param VendorGuid [in]

A pointer to a GUID that identifies the vendor associated with the specified environment variable. Environment variables are grouped into namespaces based on their vendor GUIDs. Some hardware platforms might not support vendor GUIDs. On these platforms, all variables are grouped into one, common namespace, and the <i>VendorGuid</i> parameter is ignored.


### -param Value [out, optional]

A pointer to a caller-allocated buffer to which the routine writes the value of the specified environment variable.


### -param ValueLength [in, out]

A pointer to a location that contains the buffer size. On entry, the location pointed to by this parameter contains the size, in bytes, of the caller-supplied <i>Value</i> buffer. Before exiting, the routine writes to this location the size, in bytes, of the variable value. If the routine returns STATUS_SUCCESS, the *<i>ValueLength</i> output value is the number of bytes of data written to the <i>Value</i> buffer. If the routine returns STATUS_BUFFER_TOO_SMALL, *<i>ValueLength</i> is the required buffer size.


### -param Attributes [out, optional]

A pointer to a location to which the routine writes the attributes of the specified environment variable. This parameter is optional and can be set to NULL if the caller does not need the attributes. For more information, see Remarks.


## -returns



<b>ExGetFirmwareEnvironmentVariable</b> returns STATUS_SUCCESS if it is successful. Possible return values include the following error status codes.

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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>Value</i> buffer is too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VARIABLE_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The requested variable does not exist.

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



System firmware environment variables contain data values that are passed between the boot firmware environment implemented in the hardware platform and the operating-system loaders and other software that runs in the firmware environment.

The set of firmware environment variables that is available in a hardware platform depends on the boot firmware. The location of these environment variables is also specified by the firmware. For example, on a UEFI-based platform, NVRAM contains firmware environment variables that specify system boot settings. For information about specific variables used, see the Unified Extensible Firmware Interface Specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=183072">UEFI</a> website. For more information about UEFI and Windows, see <a href="https://go.microsoft.com/fwlink/p/?linkid=183071">UEFI and Windows</a>.

Firmware environment variables are not supported on a legacy BIOS-based platform. Calls to <b>ExGetFirmwareEnvironmentVariable</b> always fail on a legacy BIOS-based platform; they also fail if Windows was installed using the legacy BIOS on a platform that supports both legacy BIOS and UEFI. To identify these conditions, first use uuidgen or a similar tool to generate a random unique GUID statically.  Then call this routine to look for a specific variable name, providing that GUID as the <i>VendorGuid</i> parameter.

On a legacy BIOS-based platform, or on a platform that supports both legacy BIOS and UEFI but in which Windows was installed using the legacy BIOS, the function will fail with STATUS_NOT_IMPLEMENTED. On a UEFI-based platform, the function will fail with an error specific to the firmware, such as STATUS_VARIABLE_NOT_FOUND, to indicate that the dummy GUID namespace does not exist.

If the caller specifies a non-NULL <i>Attributes</i> parameter, the routine writes the attributes of the specified system firmware environment variable to the location pointed to by <i>Attributes</i>. Version 2.3.1 of the UEFI specification defines the following attributes for firmware environment variables.

<table>
<tr>
<th>Variable name</th>
<th>Value</th>
</tr>
<tr>
<td>EFI_VARIABLE_NON_VOLATILE</td>
<td>0x00000001</td>
</tr>
<tr>
<td>EFI_VARIABLE_BOOTSERVICE_ACCESS</td>
<td>0x00000002</td>
</tr>
<tr>
<td>EFI_VARIABLE_RUNTIME_ACCESS</td>
<td>0x00000004</td>
</tr>
<tr>
<td>EFI_VARIABLE_HARDWARE_ERROR_RECORD</td>
<td>0x00000008</td>
</tr>
<tr>
<td>EFI_VARIABLE_AUTHENTICATED_WRITE_ACCESS</td>
<td>0x00000010</td>
</tr>
<tr>
<td>EFI_VARIABLE_TIME_BASED_AUTHENTICATED_WRITE_ACCESS</td>
<td>0x00000020</td>
</tr>
<tr>
<td>EFI_VARIABLE_APPEND_WRITE</td>
<td>0x00000040</td>
</tr>
</table>
 

These attribute values are defined as flag bits. The value written to the ULONG variable pointed to by <i>Attributes</i> is either zero or the bitwise OR of one or more attributes in the preceding table. For more information, see the UEFI specification at the <a href="https://go.microsoft.com/fwlink/p/?linkid=183072">UEFI</a> website.

If you create a backup datastore, you can use this function to save all the boot settings for the platform so they can be restored by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsetfirmwareenvironmentvariable">ExSetFirmwareEnvironmentVariable</a> routine if needed.

<b>ExGetFirmwareEnvironmentVariable</b> is the kernel-mode equivalent of the Win32 <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-getfirmwareenvironmentvariablea">GetFirmwareEnvironmentVariable</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exsetfirmwareenvironmentvariable">ExSetFirmwareEnvironmentVariable</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-getfirmwareenvironmentvariablea">GetFirmwareEnvironmentVariable</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

