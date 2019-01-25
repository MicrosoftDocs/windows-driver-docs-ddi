---
UID: NS:ntddk._WHEA_ERROR_PACKET_V1
title: "_WHEA_ERROR_PACKET_V1" (ntddk.h)
description: The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V1 structure is supported in Windows Server 2008 and Windows Vista SP1.
old-location: whea\whea_error_packet_v1.htm
tech.root: whea
ms.assetid: 66189a9a-241f-4457-87cd-d5d583a46f14
ms.date: 02/20/2018
ms.keywords: "*PWHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET_V1, PWHEA_ERROR_PACKET_V1, PWHEA_ERROR_PACKET_V1 structure pointer [WHEA Drivers and Applications], WHEA_ERROR_PACKET, WHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET_V1 structure [WHEA Drivers and Applications], _WHEA_ERROR_PACKET_V1, ntddk/PWHEA_ERROR_PACKET_V1, ntddk/WHEA_ERROR_PACKET_V1, whea.whea_error_packet_v1, whearef_d65ca9a6-c7ff-42f0-b7d5-763b6a34b924.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_ERROR_PACKET_V1
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_PACKET_V1, *PWHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET, *PWHEA_ERROR_PACKET
---

# _WHEA_ERROR_PACKET_V1 structure


## -description


The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).
<div class="alert"><b>Note</b>  The WHEA_ERROR_PACKET_V1 structure is supported in Windows Server 2008 and Windows Vista SP1.</div><div> </div>

## -struct-fields




### -field Signature

The signature of the hardware error packet. This member contains the value WHEA_ERROR_PACKET_V1_SIGNATURE.


### -field Flags

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560472">WHEA_ERROR_PACKET_FLAGS</a> union that describes the error condition. 


### -field Size

The size, in bytes, of the hardware error packet, including the raw data.


### -field RawDataLength

The length, in bytes, of the data that is contained in the <b>RawData</b> member.


### -field Reserved1

Reserved for system use.


### -field Context

Reserved for system use.


### -field ErrorType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560515">WHEA_ERROR_TYPE</a>-typed value that indicates the type of hardware component that reported the hardware error.


### -field ErrorSeverity

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560503">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition.


### -field ErrorSourceId

The identifier of the error source that reported the hardware error.


### -field ErrorSourceType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560511">WHEA_ERROR_SOURCE_TYPE</a>-typed value that indicates the type of error source that reported the hardware error.


### -field Reserved2

Reserved for system use.


### -field Version

The version of the WHEA_ERROR_PACKET_V1 structure. This member contains the value WHEA_ERROR_PKT_V1VERSION.


### -field Cpu

Reserved for system use.


### -field u

A union consisting of the following members:


### -field u.ProcessorError

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560607">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure that describes processor error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeProcessor</b>. 


### -field u.MemoryError

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a> structure that describes memory error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeMemory</b>. 


### -field u.NmiError

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560571">WHEA_NMI_ERROR_SECTION</a> structure that describes nonmaskable interrupt (NMI) error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeNMI</b>. 


### -field u.PciExpressError

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560576">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure that describes PCI Express (PCIe) error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIExpress</b>. 


### -field u.PciXBusError

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560583">WHEA_PCIXBUS_ERROR_SECTION</a> structure that describes PCI or PCI-X bus error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIXBus</b>. 


### -field u.PciXDeviceError

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560589">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure that describes PCI or PCI-X device error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIXDevice</b>. 


### -field RawDataFormat

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560619">WHEA_RAW_DATA_FORMAT</a>-typed value that indicates the format of the hardware error information that is contained in the <b>RawData</b> data buffer.


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
If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V2, the code is running on a later version of Windows, and the error packet is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560480">WHEA_ERROR_PACKET_V2</a> structure.

</li>
</ol>
An LLHEH passes a WHEA_ERROR_PACKET_V1 structure to the operating system when it reports a hardware error. This hardware error packet contains the raw hardware error data direct from the error source's error status registers.

The WHEA_ERROR_PACKET_V1 structure describes the error data that is contained in a hardware error packet error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a hardware error packet error section only if the  <b>SectionType</b> member of one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains WHEA_PACKET_SECTION_GUID.




## -see-also




<a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">Platform-Specific Hardware Error Driver (PSHED) Plug-Ins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560472">WHEA_ERROR_PACKET_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560480">WHEA_ERROR_PACKET_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560503">WHEA_ERROR_SEVERITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560511">WHEA_ERROR_SOURCE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560515">WHEA_ERROR_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560565">WHEA_MEMORY_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560571">WHEA_NMI_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560576">WHEA_PCIEXPRESS_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560583">WHEA_PCIXBUS_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560589">WHEA_PCIXDEVICE_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560607">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560619">WHEA_RAW_DATA_FORMAT</a>
 

 

