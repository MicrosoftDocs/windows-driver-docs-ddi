---
UID: NS:wdm._DRIVER_INFO_ENTRY
title: _DRIVER_INFO_ENTRY (wdm.h)
description: Describes a single driver image in a driver runtime report.
tech.root: kernel
ms.date: 07/24/2026
ai-usage: ai-assisted
keywords: ["DRIVER_INFO_ENTRY structure"]
ms.keywords: "*PDRIVER_INFO_ENTRY, DRIVER_INFO_ENTRY, DRIVER_INFO_ENTRY structure [Kernel-Mode Driver Architecture], PDRIVER_INFO_ENTRY, _DRIVER_INFO_ENTRY, kernel.driver_info_entry, wdm/DRIVER_INFO_ENTRY, wdm/PDRIVER_INFO_ENTRY"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: DRIVER_INFO_ENTRY, *PDRIVER_INFO_ENTRY
f1_keywords:
 - _DRIVER_INFO_ENTRY
 - wdm/_DRIVER_INFO_ENTRY
 - PDRIVER_INFO_ENTRY
 - wdm/PDRIVER_INFO_ENTRY
 - DRIVER_INFO_ENTRY
 - wdm/DRIVER_INFO_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_INFO_ENTRY
 - PDRIVER_INFO_ENTRY
 - DRIVER_INFO_ENTRY
---

# _DRIVER_INFO_ENTRY structure


## -description

The <b>DRIVER_INFO_ENTRY</b> structure describes a single driver image in a driver runtime report.

## -struct-fields

### -field InternalName

Internal name of the driver from the resource section. This field is <b>DRIVER_REPORT_NAME_MAX_LENGTH</b> (32) characters.

### -field ImageHashAlgorithm

Hash algorithm used to calculate the image digest.

### -field PublisherThumbprintHashAlgorithm

Hash algorithm used to calculate the thumbprint of the leaf certificate that validates the entire image.

### -field ImageHashOffset

Offset from the start of the driver report to a buffer containing the digest of the driver image on disk.

### -field PublisherThumbprintOffset

Offset from the start of the driver report to a buffer containing the thumbprint of the leaf certificate validating the entire image.

### -field LoadCount

Number of times that this driver image has been loaded into the system.

### -field OemNameSize

Size of a string indicating the OEM name stored in the authenticated OPUS block of the image digital signature. There is no OEM name for inbox Windows-signed drivers. The size does *not* include the NULL terminator (even though the string is NULL-terminated).

### -field OemNameOffset

Offset of a string indicating the OEM name stored in the authenticated OPUS block of the image digital signature.

### -field Flags

Flags indicating various properties of the current driver image.

### -field Flags.Unloaded

Set to 1 in case the driver is currently unloaded.

### -field Flags.BootDriver

Set to 1 in case the image is a boot driver; 0 otherwise (the image is a runtime driver).

### -field Flags.HotPatch

Set to 1 in case the image can be also loaded as a hotpatch.

### -field Flags.Reserved

Reserved flags bits.

### -field Flags.AsUInt16

The flags as a single 16-bit value.

### -field Padding

Padding field.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-driver_runtime_report">DRIVER_RUNTIME_REPORT</a>

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-runtime_report_header">RUNTIME_REPORT_HEADER</a>

<a href="/windows/win32/api/winnt/ns-winnt-driver_info_entry">DRIVER_INFO_ENTRY (winnt.h)</a>

<a href="/windows/win32/api/sysinfoapi/nf-sysinfoapi-getruntimeattestationreport">GetRuntimeAttestationReport</a>
