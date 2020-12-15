---
UID: NS:ntddk._WHEA_ERROR_PACKET_V2
title: _WHEA_ERROR_PACKET_V2 (ntddk.h)
description: The WHEA_ERROR_PACKET_V2 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V2 structure is supported in Windows 7 and later versions of Windows.
tech.root: whea
ms.date: 02/20/2018
keywords: ["WHEA_ERROR_PACKET_V2 structure"]
ms.keywords: "*PWHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET_V2, PWHEA_ERROR_PACKET_V1, PWHEA_ERROR_PACKET_V1 structure pointer [WHEA Drivers and Applications], WHEA_ERROR_PACKET, WHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET_V1 structure [WHEA Drivers and Applications], WHEA_ERROR_PACKET_V2, _WHEA_ERROR_PACKET_V2, ntddk/PWHEA_ERROR_PACKET_V1, ntddk/WHEA_ERROR_PACKET_V1, whea.whea_error_packet_v1, whearef_d65ca9a6-c7ff-42f0-b7d5-763b6a34b924.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
req.typenames: WHEA_ERROR_PACKET_V2, *PWHEA_ERROR_PACKET_V2, WHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET
f1_keywords:
 - _WHEA_ERROR_PACKET_V2
 - ntddk/_WHEA_ERROR_PACKET_V2
 - PWHEA_ERROR_PACKET_V2
 - ntddk/PWHEA_ERROR_PACKET_V2
 - WHEA_ERROR_PACKET_V2
 - ntddk/WHEA_ERROR_PACKET_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WHEA_ERROR_PACKET_V2
---

# _WHEA_ERROR_PACKET_V2 structure


## -description

The WHEA_ERROR_PACKET_V2 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).

## -struct-fields

### -field Signature

The signature of the hardware error packet. This member contains the value WHEA_ERROR_PACKET_V2_SIGNATURE.

### -field Version

The version of the WHEA_ERROR_PACKET_V2 structure. This member contains the value WHEA_ERROR_PACKET_V2_VERSION.

### -field Length

### -field Flags

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_packet_flags">WHEA_ERROR_PACKET_FLAGS</a> union that describes the error condition.

### -field ErrorType

A <a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_type">WHEA_ERROR_TYPE</a>-typed value that indicates the type of hardware component that reported the hardware error.

### -field ErrorSeverity

A <a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_severity">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition.

### -field ErrorSourceId

The identifier of the error source that reported the hardware error.

### -field ErrorSourceType

A <a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_source_type">WHEA_ERROR_SOURCE_TYPE</a>-typed value that indicates the type of error source that reported the hardware error.

### -field NotifyType

### -field Context

Reserved for system use.

### -field DataFormat

### -field Reserved1

Reserved for system use.

### -field DataOffset

### -field DataLength

### -field PshedDataOffset

### -field PshedDataLength

## -remarks

The WHEA_ERROR_PACKET_V2 structure is used to report a hardware error in Windows 7 and later versions of Windows.

If your <a href="/windows-hardware/drivers/whea/platform-specific-hardware-error-driver-plug-ins2">platform-specific hardware error driver (PSHED) plug-ins</a> run on any WHEA-compatible Windows version, You can inspect the version of WHEA_ERROR_PACKET by following these steps:

<ol>
<li>
If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V1_SIGNATURE, the code is running on an early version of Windows, and the error packet is formatted as a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_packet_v1">WHEA_ERROR_PACKET_V1</a> structure.

</li>
<li>
If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V2_SIGNATURE, the code is running on a later version of Windows, and the error packet is formatted as a <b>WHEA_ERROR_PACKET_V2</b> structure.

</li>
</ol>
An LLHEH passes a WHEA_ERROR_PACKET_V2 structure to the operating system when it reports a hardware error. This hardware error packet contains the raw hardware error data direct from the error source's error status registers.

The WHEA_ERROR_PACKET_V2 structure describes the error data that is contained in a hardware error packet error section of an <a href="/windows-hardware/drivers/whea/error-records">error record</a>. An error record contains a hardware error packet error section only if the  <b>SectionType</b> member of one of the <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains WHEA_PACKET_SECTION_GUID.

## -see-also

<a href="/windows-hardware/drivers/whea/platform-specific-hardware-error-driver-plug-ins2">Platform-Specific Hardware Error Driver (PSHED) Plug-Ins</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_packet_flags">WHEA_ERROR_PACKET_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_packet_v2">WHEA_ERROR_PACKET_V2</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_severity">WHEA_ERROR_SEVERITY</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_source_type">WHEA_ERROR_SOURCE_TYPE</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_type">WHEA_ERROR_TYPE</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_memory_error_section">WHEA_MEMORY_ERROR_SECTION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_nmi_error_section">WHEA_NMI_ERROR_SECTION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pciexpress_error_section">WHEA_PCIEXPRESS_ERROR_SECTION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section">WHEA_PCIXBUS_ERROR_SECTION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixdevice_error_section">WHEA_PCIXDEVICE_ERROR_SECTION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_raw_data_format">WHEA_RAW_DATA_FORMAT</a>
