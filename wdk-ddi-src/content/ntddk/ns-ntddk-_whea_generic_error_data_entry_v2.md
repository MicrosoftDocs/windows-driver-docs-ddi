---
UID: NS:ntddk._WHEA_GENERIC_ERROR_DATA_ENTRY_V2
title: _WHEA_GENERIC_ERROR_DATA_ENTRY_V2 (ntddk.h)
description: The WHEA_GENERIC_ERROR_DATA_ENTRY structure describes an error data section in a generic error status block.
old-location: whea\whea_generic_error_data_entry.htm
tech.root: whea
ms.assetid: 86834d99-34bd-487a-bbd4-4c0143d849a0
ms.date: 02/20/2018
keywords: ["_WHEA_GENERIC_ERROR_DATA_ENTRY_V2 structure"]
ms.keywords: "*PWHEA_GENERIC_ERROR_DATA_ENTRY, *PWHEA_GENERIC_ERROR_DATA_ENTRY_V2, PWHEA_GENERIC_ERROR_DATA_ENTRY, PWHEA_GENERIC_ERROR_DATA_ENTRY structure pointer [WHEA Drivers and Applications], WHEA_GENERIC_ERROR_DATA_ENTRY, WHEA_GENERIC_ERROR_DATA_ENTRY structure [WHEA Drivers and Applications], WHEA_GENERIC_ERROR_DATA_ENTRY_V2, _WHEA_GENERIC_ERROR_DATA_ENTRY_V2, ntddk/PWHEA_GENERIC_ERROR_DATA_ENTRY, ntddk/WHEA_GENERIC_ERROR_DATA_ENTRY, whea.whea_generic_error_data_entry, whearef_9e532654-fd5a-4936-8465-f9d6f9eafad2.xml"
f1_keywords:
 - "ntddk/WHEA_GENERIC_ERROR_DATA_ENTRY"
 - "WHEA_GENERIC_ERROR_DATA_ENTRY"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- WHEA_GENERIC_ERROR_DATA_ENTRY
targetos: Windows
req.typenames: WHEA_GENERIC_ERROR_DATA_ENTRY_V2, *PWHEA_GENERIC_ERROR_DATA_ENTRY_V2, WHEA_GENERIC_ERROR_DATA_ENTRY, *PWHEA_GENERIC_ERROR_DATA_ENTRY
---

# _WHEA_GENERIC_ERROR_DATA_ENTRY_V2 structure


## -description


The WHEA_GENERIC_ERROR_DATA_ENTRY structure describes an error data section in a generic error status block.


## -struct-fields




### -field SectionType

A GUID that identifies the type of error data that is contained in the error data section. The standard section types are defined as follows:





#### WHEA_PACKET_SECTION_GUID

The error data section contains the hardware error packet that was passed to the operating system by the low-level hardware error handler (LLHEH) that reported the error. This data is described by a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a> structure.



#### PROCESSOR_GENERIC_ERROR_SECTION_GUID

The error data section contains processor error data that is not specific to a particular processor architecture. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.



#### FIRMWARE_ERROR_RECORD_REFERENCE_GUID

The error data section contains a reference to a firmware error record that is specific to the Itanium processor architecture. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_firmware_error_record_reference">WHEA_FIRMWARE_ERROR_RECORD_REFERENCE</a> structure.



#### IPF_PROCESSOR_ERROR_SECTION_GUID

The error data section contains processor error data that is specific to the Itanium processor architecture. For more information about the format of the error data that is contained in this error data section, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.



#### MEMORY_ERROR_SECTION_GUID

The error data section contains platform memory error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_memory_error_section">WHEA_MEMORY_ERROR_SECTION</a> structure.



#### NMI_SECTION_GUID

The error data section contains nonmaskable interrupt (NMI) error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_nmi_error_section">WHEA_NMI_ERROR_SECTION</a> structure.



#### PCIEXPRESS_ERROR_SECTION_GUID

The error data section contains PCI Express (PCIe) error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pciexpress_error_section">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure.



#### PCIXBUS_ERROR_SECTION_GUID

The error data section contains PCI/PCI-X bus error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section">WHEA_PCIXBUS_ERROR_SECTION</a> structure.

The error data section contains PCI/PCI-X device error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixdevice_error_section">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure.



#### XPF_PROCESSOR_ERROR_SECTION_GUID

The error data section contains processor error data that is specific to the x86 or x64 processor architecture. This data is described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560655">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure.

For error data sections that do not conform to one of the standard section types, this member contains a platform-specific GUID that identifies the type of error data that is contained in the error data section. If a platform-specific GUID is not defined for the type of error data that is contained in the error data section, this member contains GENERIC_SECTION_GUID.


### -field ErrorSeverity

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_severity">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition that is described by the error data section.


### -field Revision

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_revision">WHEA_REVISION</a> union that describes the revision level of the WHEA_GENERIC_ERROR_DATA_ENTRY structure.


### -field ValidBits

A bitwise OR'ed combination of values that specifies which members of this structure contain valid data. Possible values are:





#### 0x01

A single bit that indicates that the <b>FRUId</b> member contains valid data.



#### 0x02

A single bit that indicates that the <b>FRUText</b> member contains valid data.


### -field Flags

A bitwise OR'ed combination of values that describes the error data section. Possible values are:





#### 0x01

A single bit that indicates that this error data section is the primary section within the generic error status block. When there are multiple sections contained in a generic error status block, the primary section is the section that is used for error recovery.



#### 0x02

A single bit that indicates that the error described by this error data section was not contained within the processor or memory hierarchy. In this situation, the error might have propagated to other components of the system.



#### 0x04

A single bit that indicates that the component must be reinitialized or re-enabled by the operating system.



#### 0x08

A single bit that indicates that an error threshold has been exceeded.



#### 0x10

A single bit that indicates that a resource could not be queried for error information due to conflicts with other system software or resources. In this situation, some of the fields of the error data section will be invalid.



#### 0x20

A single bit that indicates that the reported error is a latent error (one not yet consumed) that could result in a more severe error when it is consumed.


### -field ErrorDataLength

The length, in bytes, of the error data that is contained in the <b>Data</b> member.


### -field FRUId

A GUID that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>0x01</b> bit is set in the <b>ValidBits</b> member.


### -field FRUText

A character string that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>0x02</b> bit is set in the <b>ValidBits</b> member.


### -field Timestamp

 


### -field Data

A variable-sized buffer that contains the error data for the error data section. The format of the data that is contained in this buffer is determined by the section type that is specified in the <b>SectionType</b> member.


## -remarks



A generic error status block can contain one or more WHEA_GENERIC_ERROR_DATA_ENTRY structures. Each WHEA_GENERIC_ERROR_DATA_ENTRY structure describes a section of error information that is part of the error status data for a generic error source.

The <b>Data</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error">WHEA_GENERIC_ERROR</a> structure contains a generic error status block that contains the WHEA_GENERIC_ERROR_DATA_ENTRY structures. The number of WHEA_GENERIC_ERROR_DATA_ENTRY structures that are included in the generic error status block is specified by the <b>ErrorDataEntryCount</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error_blockstatus">WHEA_GENERIC_ERROR_BLOCKSTATUS</a> union.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error">WHEA_GENERIC_ERROR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_generic_error_blockstatus">WHEA_GENERIC_ERROR_BLOCKSTATUS</a>
 

 

