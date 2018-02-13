---
UID: NS:ntddk._WHEA_ERROR_PACKET_V1
title: "_WHEA_ERROR_PACKET_V1"
author: windows-driver-content
description: The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V1 structure is supported in Windows Server 2008 and Windows Vista SP1.
old-location: whea\whea_error_packet_v1.htm
old-project: whea
ms.assetid: 66189a9a-241f-4457-87cd-d5d583a46f14
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_WHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET_V1 structure [WHEA Drivers and Applications], ntddk/WHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET_V1, ntddk/PWHEA_ERROR_PACKET_V1, whearef_d65ca9a6-c7ff-42f0-b7d5-763b6a34b924.xml, WHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET, whea.whea_error_packet_v1, PWHEA_ERROR_PACKET_V1 structure pointer [WHEA Drivers and Applications], *PWHEA_ERROR_PACKET_V1, PWHEA_ERROR_PACKET_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_ERROR_PACKET_V1
product: Windows
targetos: Windows
req.typenames: WHEA_ERROR_PACKET, WHEA_ERROR_PACKET_V1, *PWHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET_V1
---

# _WHEA_ERROR_PACKET_V1 structure


## -description


The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).
<div class="alert"><b>Note</b>  The WHEA_ERROR_PACKET_V1 structure is supported in Windows Server 2008 and Windows Vista SP1.</div><div> </div>

## -syntax


````
typedef struct _WHEA_ERROR_PACKET_V1 {
  ULONG                   Signature;
  WHEA_ERROR_PACKET_FLAGS Flags;
  ULONG                   Size;
  ULONG                   RawDataLength;
  ULONGLONG               Reserved1;
  ULONGLONG               Context;
  WHEA_ERROR_TYPE         ErrorType;
  WHEA_ERROR_SEVERITY     ErrorSeverity;
  ULONG                   ErrorSourceId;
  WHEA_ERROR_SOURCE_TYPE  ErrorSourceType;
  ULONG                   Reserved2;
  ULONG                   Version;
  ULONGLONG               Cpu;
  union {
    WHEA_PROCESSOR_GENERIC_ERROR_SECTION ProcessorError;
    WHEA_MEMORY_ERROR_SECTION            MemoryError;
    WHEA_NMI_ERROR_SECTION               NmiError;
    WHEA_PCIEXPRESS_ERROR_SECTION        PciExpressError;
    WHEA_PCIXBUS_ERROR_SECTION           PciXBusError;
    WHEA_PCIXDEVICE_ERROR_SECTION        PciXDeviceError;
  } u;
  WHEA_RAW_DATA_FORMAT    RawDataFormat;
  ULONG                   RawDataOffset;
  UCHAR                   RawData[1];
} WHEA_ERROR_PACKET_V1, *PWHEA_ERROR_PACKET_V1;
````


## -struct-fields




### -field Signature

The signature of the hardware error packet. This member contains the value WHEA_ERROR_PACKET_V1_SIGNATURE.


### -field Flags

A <a href="..\ntddk\ns-ntddk-_whea_error_packet_flags.md">WHEA_ERROR_PACKET_FLAGS</a> union that describes the error condition. 


### -field Size

The size, in bytes, of the hardware error packet, including the raw data.


### -field RawDataLength

The length, in bytes, of the data that is contained in the <b>RawData</b> member.


### -field Reserved1

Reserved for system use.


### -field Context

Reserved for system use.


### -field ErrorType

A <a href="..\ntddk\ne-ntddk-_whea_error_type.md">WHEA_ERROR_TYPE</a>-typed value that indicates the type of hardware component that reported the hardware error.


### -field ErrorSeverity

A <a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition.


### -field ErrorSourceId

The identifier of the error source that reported the hardware error.


### -field ErrorSourceType

A <a href="..\ntddk\ne-ntddk-_whea_error_source_type.md">WHEA_ERROR_SOURCE_TYPE</a>-typed value that indicates the type of error source that reported the hardware error.


### -field Reserved2

Reserved for system use.


### -field Version

The version of the WHEA_ERROR_PACKET_V1 structure. This member contains the value WHEA_ERROR_PKT_V1VERSION.


### -field Cpu

Reserved for system use.


### -field u

A union consisting of the following members:


### -field u.ProcessorError

A <a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure that describes processor error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeProcessor</b>. 


### -field u.MemoryError

A <a href="..\ntddk\ns-ntddk-_whea_memory_error_section.md">WHEA_MEMORY_ERROR_SECTION</a> structure that describes memory error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeMemory</b>. 


### -field u.NmiError

A <a href="..\ntddk\ns-ntddk-_whea_nmi_error_section.md">WHEA_NMI_ERROR_SECTION</a> structure that describes nonmaskable interrupt (NMI) error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeNMI</b>. 


### -field u.PciExpressError

A <a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure that describes PCI Express (PCIe) error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIExpress</b>. 


### -field u.PciXBusError

A <a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section.md">WHEA_PCIXBUS_ERROR_SECTION</a> structure that describes PCI or PCI-X bus error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIXBus</b>. 


### -field u.PciXDeviceError

A <a href="..\ntddk\ns-ntddk-_whea_pcixdevice_error_section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure that describes PCI or PCI-X device error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIXDevice</b>. 


### -field RawDataFormat

A <a href="..\ntddk\ne-ntddk-_whea_raw_data_format.md">WHEA_RAW_DATA_FORMAT</a>-typed value that indicates the format of the hardware error information that is contained in the <b>RawData</b> data buffer.


### -field RawDataOffset

An offset, in bytes, from the beginning of the <b>RawData</b> data buffer where a PSHED plug-in can add supplementary platform-specific error information to the hardware error packet. The amount of supplementary information that can be added to the hardware error packet is limited by the total size of the packet as specified in the <b>Size</b> member.


### -field RawData

A variable-sized data buffer that contains the raw hardware error information from the error source's status registers. The format of the hardware error data is specified by the <b>RawDataFormat</b> member.


## -remarks



The WHEA_ERROR_PACKET_V1 structure is used to report a hardware error in Windows Server 2008 and Windows Vista SP1.

If your <a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">platform-specific hardware error driver (PSHED) plug-ins</a> run on any WHEA-compatible Windows version, You can inspect the version of WHEA_ERROR_PACKET by following these steps:

<ol>
<li>
If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V1, the code is running on an early version of Windows, and the error packet is formatted as a <b>WHEA_ERROR_PACKET_V1</b> structure.

</li>
<li>
If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V2, the code is running on a later version of Windows, and the error packet is formatted as a <a href="..\ntddk\ns-ntddk-_whea_error_packet_v2.md">WHEA_ERROR_PACKET_V2</a> structure.

</li>
</ol>
An LLHEH passes a WHEA_ERROR_PACKET_V1 structure to the operating system when it reports a hardware error. This hardware error packet contains the raw hardware error data direct from the error source's error status registers.

The WHEA_ERROR_PACKET_V1 structure describes the error data that is contained in a hardware error packet error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a hardware error packet error section only if the  <b>SectionType</b> member of one of the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains WHEA_PACKET_SECTION_GUID.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_memory_error_section.md">WHEA_MEMORY_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_pcixdevice_error_section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_error_packet_v2.md">WHEA_ERROR_PACKET_V2</a>



<a href="..\ntddk\ns-ntddk-_whea_nmi_error_section.md">WHEA_NMI_ERROR_SECTION</a>



<a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>



<a href="..\ntddk\ne-ntddk-_whea_error_type.md">WHEA_ERROR_TYPE</a>



<a href="..\ntddk\ne-ntddk-_whea_error_source_type.md">WHEA_ERROR_SOURCE_TYPE</a>



<a href="..\ntddk\ns-ntddk-_whea_error_packet_flags.md">WHEA_ERROR_PACKET_FLAGS</a>



<a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">Platform-Specific Hardware Error Driver (PSHED) Plug-Ins</a>



<a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>



<a href="..\ntddk\ne-ntddk-_whea_raw_data_format.md">WHEA_RAW_DATA_FORMAT</a>



<a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section.md">WHEA_PCIXBUS_ERROR_SECTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_PACKET_V1 structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

