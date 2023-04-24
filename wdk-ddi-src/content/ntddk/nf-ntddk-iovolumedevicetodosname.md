---
UID: NF:ntddk.IoVolumeDeviceToDosName
title: IoVolumeDeviceToDosName function (ntddk.h)
description: The IoVolumeDeviceToDosName routine returns the MS-DOS path for a specified device object that represents a file system volume.
tech.root: kernel
ms.date: 04/20/2023
keywords: ["IoVolumeDeviceToDosName function"]
ms.keywords: IoVolumeDeviceToDosName, IoVolumeDeviceToDosName routine [Kernel-Mode Driver Architecture], k104_01cdeb80-9a49-4d42-a311-cf8b69d03b9c.xml, kernel.iovolumedevicetodosname, ntddk/IoVolumeDeviceToDosName
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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
 - IoVolumeDeviceToDosName
 - ntddk/IoVolumeDeviceToDosName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoVolumeDeviceToDosName
---

## -description

The **IoVolumeDeviceToDosName** routine returns the MS-DOS path for a specified device object that represents a file system volume.

## -parameters

### -param VolumeDeviceObject [in]

A pointer to a device object that represents a volume device object created by a storage class driver.

### -param DosName [out]

A pointer to a caller-allocated [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure. If the call is successful, **IoVolumeDeviceToDosName** sets the values of the **Length**, **MaximumLength**, and **Buffer** members of this structure. On exit, the **Buffer** member points to a wide-character, null-terminated string that contains the MS-DOS path of the volume device object specified by *VolumeDeviceObject*. For more information, see Remarks.

## -returns

**IoVolumeDeviceToDosName** returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

| Return value | Description |
|--|--|
| STATUS_INVALID_PARAMETER | The routine failed due to invalid parameter values passed by the caller. |
| STATUS_INSUFFICIENT_RESOURCES | The routine failed to allocate resources required for this operation. |

## -remarks

**IoVolumeDeviceToDosName** allocates the string buffer pointed to by the **Buffer** member of the [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that the *DosName* parameter points to. After this buffer is no longer required, a caller of this routine should call the [ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool) routine to free the buffer.

Starting with Windows Vista, you must ensure that APCs are not disabled before calling this routine. The [KeAreAllApcsDisabled](/windows-hardware/drivers/ddi/wdm/nf-wdm-keareallapcsdisabled) routine can be used to verify that APCs are not disabled.

## -see-also

[ExFreePool](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool)

[KeAreAllApcsDisabled](/windows-hardware/drivers/ddi/wdm/nf-wdm-keareallapcsdisabled)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
