---
UID: NF:wdm.ExGetFirmwareEnvironmentVariable
title: ExGetFirmwareEnvironmentVariable function (wdm.h)
description: The ExGetFirmwareEnvironmentVariable routine gets the value of the specified system firmware environment variable.
tech.root: kernel
ms.date: 03/14/2023
keywords: ["ExGetFirmwareEnvironmentVariable function"]
ms.keywords: ExGetFirmwareEnvironmentVariable, ExGetFirmwareEnvironmentVariable routine [Kernel-Mode Driver Architecture], kernel.exgetfirmwareenvironmentvariable, wdm/ExGetFirmwareEnvironmentVariable
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
 - ExGetFirmwareEnvironmentVariable
 - wdm/ExGetFirmwareEnvironmentVariable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExGetFirmwareEnvironmentVariable
---

## -description

The **ExGetFirmwareEnvironmentVariable** routine gets the value of the specified system firmware environment variable.

## -parameters

### -param VariableName [in]

A pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the name of the specified environment variable.

### -param VendorGuid [in]

A pointer to a GUID that identifies the vendor associated with the specified environment variable. Environment variables are grouped into namespaces based on their vendor GUIDs. Some hardware platforms might not support vendor GUIDs. On these platforms, all variables are grouped into one, common namespace, and the *VendorGuid* parameter is ignored.

### -param Value [out, optional]

A pointer to a caller-allocated buffer to which the routine writes the value of the specified environment variable.

### -param ValueLength [in, out]

A pointer to a location that contains the buffer size. On entry, the location pointed to by this parameter contains the size, in bytes, of the caller-supplied *Value* buffer. Before exiting, the routine writes to this location the size, in bytes, of the variable value. If the routine returns STATUS_SUCCESS, the **ValueLength* output value is the number of bytes of data written to the *Value* buffer. If the routine returns STATUS_BUFFER_TOO_SMALL, **ValueLength* is the required buffer size.

### -param Attributes [out, optional]

A pointer to a location to which the routine writes the attributes of the specified environment variable. This parameter is optional and can be set to NULL if the caller does not need the attributes. For more information, see Remarks.

## -returns

**ExGetFirmwareEnvironmentVariable** returns STATUS_SUCCESS if it is successful. Possible return values include the following error status codes.

| Return code | Description |
|---|---|
| **STATUS_INSUFFICIENT_RESOURCES** | Available system resources are insufficient to complete the requested operation. |
| **STATUS_BUFFER_TOO_SMALL** | The *Value* buffer is too small. |
| **STATUS_VARIABLE_NOT_FOUND** | The requested variable does not exist. |
| **STATUS_INVALID_PARAMETER** | One of the parameters is not valid. |
| **STATUS_NOT_IMPLEMENTED** | This routine is not supported on this platform. |
| **STATUS_UNSUCCESSFUL** | The firmware returned an unrecognized error. |

## -remarks

System firmware environment variables contain data values that are passed between the boot firmware environment implemented in the hardware platform and the operating-system loaders and other software that runs in the firmware environment.

The set of firmware environment variables that is available in a hardware platform depends on the boot firmware. The location of these environment variables is also specified by the firmware. For example, on a UEFI-based platform, NVRAM contains firmware environment variables that specify system boot settings. For information about specific variables used, see the Unified Extensible Firmware Interface Specification at the [UEFI](https://uefi.org/specifications) website. For more information about UEFI and Windows, see [UEFI and Windows](/windows-hardware/drivers/bringup/uefi-in-windows).

Firmware environment variables are not supported on a legacy BIOS-based platform. Calls to **ExGetFirmwareEnvironmentVariable** always fail on a legacy BIOS-based platform; they also fail if Windows was installed using the legacy BIOS on a platform that supports both legacy BIOS and UEFI. To identify these conditions, first use uuidgen or a similar tool to generate a random unique GUID statically.  Then call this routine to look for a specific variable name, providing that GUID as the *VendorGuid* parameter.

On a legacy BIOS-based platform, or on a platform that supports both legacy BIOS and UEFI but in which Windows was installed using the legacy BIOS, the function will fail with STATUS_NOT_IMPLEMENTED. On a UEFI-based platform, the function will fail with an error specific to the firmware, such as STATUS_VARIABLE_NOT_FOUND, to indicate that the dummy GUID namespace does not exist.

If the caller specifies a non-NULL *Attributes* parameter, the routine writes the attributes of the specified system firmware environment variable to the location pointed to by *Attributes*. Version 2.3.1 of the UEFI specification defines the following attributes for firmware environment variables.

| Variable name | Value |
|---|---|
| EFI_VARIABLE_NON_VOLATILE | 0x00000001 |
| EFI_VARIABLE_BOOTSERVICE_ACCESS | 0x00000002 |
| EFI_VARIABLE_RUNTIME_ACCESS | 0x00000004 |
| EFI_VARIABLE_HARDWARE_ERROR_RECORD | 0x00000008 |
| EFI_VARIABLE_AUTHENTICATED_WRITE_ACCESS | 0x00000010 |
| EFI_VARIABLE_TIME_BASED_AUTHENTICATED_WRITE_ACCESS | 0x00000020 |
| EFI_VARIABLE_APPEND_WRITE | 0x00000040 |

These attribute values are defined as flag bits. The value written to the ULONG variable pointed to by *Attributes* is either zero or the bitwise OR of one or more attributes in the preceding table. For more information, see the UEFI specification at the [UEFI](https://uefi.org/specifications) website.

If you create a backup datastore, you can use this function to save all the boot settings for the platform so they can be restored by calling the [ExSetFirmwareEnvironmentVariable](/windows-hardware/drivers/ddi/wdm/nf-wdm-exsetfirmwareenvironmentvariable) routine if needed.

**ExGetFirmwareEnvironmentVariable** is the kernel-mode equivalent of the Win32 [GetFirmwareEnvironmentVariable](/windows/win32/api/winbase/nf-winbase-getfirmwareenvironmentvariablea) function.

## -see-also

[ExSetFirmwareEnvironmentVariable](/windows-hardware/drivers/ddi/wdm/nf-wdm-exsetfirmwareenvironmentvariable)

[GetFirmwareEnvironmentVariable](/windows/win32/api/winbase/nf-winbase-getfirmwareenvironmentvariablea)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
