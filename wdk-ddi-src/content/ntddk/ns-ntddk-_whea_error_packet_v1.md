---
UID: NS:ntddk._WHEA_ERROR_PACKET_V1
title: WHEA_ERROR_PACKET_V1 (ntddk.h)
description: The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V1 structure is supported in Windows Server 2008 and Windows Vista SP1.
tech.root: whea
ms.date: 12/09/2022
keywords: ["WHEA_ERROR_PACKET_V1 structure"]
ms.keywords: "*PWHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET_V1, PWHEA_ERROR_PACKET_V1, PWHEA_ERROR_PACKET_V1 structure pointer [WHEA Drivers and Applications], WHEA_ERROR_PACKET, WHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET_V1 structure [WHEA Drivers and Applications], _WHEA_ERROR_PACKET_V1, ntddk/PWHEA_ERROR_PACKET_V1, ntddk/WHEA_ERROR_PACKET_V1, whea.whea_error_packet_v1, whearef_d65ca9a6-c7ff-42f0-b7d5-763b6a34b924.xml"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008 and Windows Vista SP1.
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
req.typenames: WHEA_ERROR_PACKET_V1, *PWHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET
f1_keywords:
 - _WHEA_ERROR_PACKET_V1
 - ntddk/_WHEA_ERROR_PACKET_V1
 - PWHEA_ERROR_PACKET_V1
 - ntddk/PWHEA_ERROR_PACKET_V1
 - WHEA_ERROR_PACKET_V1
 - ntddk/WHEA_ERROR_PACKET_V1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_ERROR_PACKET_V1
 - PWHEA_ERROR_PACKET_V1
 - WHEA_ERROR_PACKET_V1
---

## -description

The **WHEA_ERROR_PACKET_V1** structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).

The **WHEA_ERROR_PACKET_V1** structure is supported in Windows Server 2008 and Windows Vista SP1.

For Windows 7 and later versions of Windows, use the [**WHEA_ERROR_PACKET_V2**](ns-ntddk-_whea_error_packet_v2.md) structure.

## -struct-fields

### -field Signature

The signature of the hardware error packet. This member contains the value WHEA_ERROR_PACKET_V1_SIGNATURE.

### -field Flags

A [**WHEA_ERROR_PACKET_FLAGS**](./ns-ntddk-_whea_error_packet_flags.md) union that describes the error condition.

### -field Size

The size, in bytes, of the hardware error packet, including the raw data.

### -field RawDataLength

The length, in bytes, of the data that is contained in the **RawData** member.

### -field Reserved1

Reserved for system use.

### -field Context

Reserved for system use.

### -field ErrorType

A [WHEA_ERROR_TYPE](./ne-ntddk-_whea_error_type.md)-typed value that indicates the type of hardware component that reported the hardware error.

### -field ErrorSeverity

A [WHEA_ERROR_SEVERITY](./ne-ntddk-_whea_error_severity.md)-typed value that indicates the severity of the error condition.

### -field ErrorSourceId

The identifier of the error source that reported the hardware error.

### -field ErrorSourceType

A [WHEA_ERROR_SOURCE_TYPE](./ne-ntddk-_whea_error_source_type.md)-typed value that indicates the type of error source that reported the hardware error.

### -field Reserved2

Reserved for system use.

### -field Version

The version of the WHEA_ERROR_PACKET_V1 structure. This member contains the value WHEA_ERROR_PKT_V1VERSION.

### -field Cpu

Reserved for system use.

### -field u

A union consisting of the following members:

### -field u.ProcessorError

A [**WHEA_PROCESSOR_GENERIC_ERROR_SECTION**](./ns-ntddk-_whea_processor_generic_error_section.md) structure that describes processor error data. This member is used only when the **ErrorType** member is set to **WheaErrTypeProcessor**.

### -field u.MemoryError

A [**WHEA_MEMORY_ERROR_SECTION**](./ns-ntddk-_whea_memory_error_section.md) structure that describes memory error data. This member is used only when the **ErrorType** member is set to **WheaErrTypeMemory**.

### -field u.NmiError

A [**WHEA_NMI_ERROR_SECTION**](./ns-ntddk-_whea_nmi_error_section.md) structure that describes nonmaskable interrupt (NMI) error data. This member is used only when the **ErrorType** member is set to **WheaErrTypeNMI**.

### -field u.PciExpressError

A [**WHEA_PCIEXPRESS_ERROR_SECTION**](./ns-ntddk-_whea_pciexpress_error_section.md) structure that describes PCI Express (PCIe) error data. This member is used only when the **ErrorType** member is set to **WheaErrTypePCIExpress**.

### -field u.PciXBusError

A [**WHEA_PCIXBUS_ERROR_SECTION**](./ns-ntddk-_whea_pcixbus_error_section.md) structure that describes PCI or PCI-X bus error data. This member is used only when the **ErrorType** member is set to **WheaErrTypePCIXBus**.

### -field u.PciXDeviceError

A [**WHEA_PCIXDEVICE_ERROR_SECTION**](./ns-ntddk-_whea_pcixdevice_error_section.md) structure that describes PCI or PCI-X device error data. This member is used only when the **ErrorType** member is set to **WheaErrTypePCIXDevice**.

### -field RawDataFormat

A [WHEA_RAW_DATA_FORMAT](./ne-ntddk-_whea_raw_data_format.md)-typed value that indicates the format of the hardware error information that is contained in the **RawData** data buffer.

### -field RawDataOffset

An offset, in bytes, from the beginning of the **RawData** data buffer where a PSHED plug-in can add supplementary platform-specific error information to the hardware error packet. The amount of supplementary information that can be added to the hardware error packet is limited by the total size of the packet as specified in the **Size** member.

### -field RawData

A variable-sized data buffer that contains the raw hardware error information from the error source's status registers. The format of the hardware error data is specified by the **RawDataFormat** member.

### -field u.PmemError

## -remarks

The WHEA_ERROR_PACKET_V1 structure is used to report a hardware error in Windows Server 2008 and Windows Vista SP1.

If your [platform-specific hardware error driver (PSHED) plug-ins](/windows-hardware/drivers/whea/platform-specific-hardware-error-driver-plug-ins2) run on any WHEA-compatible Windows version, You can inspect the version of WHEA_ERROR_PACKET by following these steps:

1. If the **Signature** member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V1_SIGNATURE, the code is running on an early version of Windows, and the error packet is formatted as a **WHEA_ERROR_PACKET_V1** structure.

1. If the **Signature** member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V2_SIGNATURE, the code is running on a later version of Windows, and the error packet is formatted as a [**WHEA_ERROR_PACKET_V2**](./ns-ntddk-_whea_error_packet_v2.md) structure.

An LLHEH passes a **WHEA_ERROR_PACKET_V1** structure to the operating system when it reports a hardware error. This hardware error packet contains the raw hardware error data direct from the error source's error status registers.

The WHEA_ERROR_PACKET_V1 structure describes the error data that is contained in a hardware error packet error section of an [error record](/windows-hardware/drivers/whea/error-records). An error record contains a hardware error packet error section only if the  **SectionType** member of one of the [**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md) structures that describe the error record sections for that error record contains WHEA_PACKET_SECTION_GUID.

## -see-also

[Platform-Specific Hardware Error Driver (PSHED) Plug-Ins](/windows-hardware/drivers/whea/platform-specific-hardware-error-driver-plug-ins2)

[**WHEA_ERROR_PACKET_FLAGS**](./ns-ntddk-_whea_error_packet_flags.md)

[**WHEA_ERROR_PACKET_V2**](./ns-ntddk-_whea_error_packet_v2.md)

[**WHEA_ERROR_RECORD_SECTION_DESCRIPTOR**](./ns-ntddk-_whea_error_record_section_descriptor.md)

[WHEA_ERROR_SEVERITY](./ne-ntddk-_whea_error_severity.md)

[WHEA_ERROR_SOURCE_TYPE](./ne-ntddk-_whea_error_source_type.md)

[WHEA_ERROR_TYPE](./ne-ntddk-_whea_error_type.md)

[**WHEA_MEMORY_ERROR_SECTION**](./ns-ntddk-_whea_memory_error_section.md)

[**WHEA_NMI_ERROR_SECTION**](./ns-ntddk-_whea_nmi_error_section.md)

[**WHEA_PCIEXPRESS_ERROR_SECTION**](./ns-ntddk-_whea_pciexpress_error_section.md)

[**WHEA_PCIXBUS_ERROR_SECTION**](./ns-ntddk-_whea_pcixbus_error_section.md)

[**WHEA_PCIXDEVICE_ERROR_SECTION**](./ns-ntddk-_whea_pcixdevice_error_section.md)

[**WHEA_PROCESSOR_GENERIC_ERROR_SECTION**](./ns-ntddk-_whea_processor_generic_error_section.md)

[WHEA_RAW_DATA_FORMAT](./ne-ntddk-_whea_raw_data_format.md)