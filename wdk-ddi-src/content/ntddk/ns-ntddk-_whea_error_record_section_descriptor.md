---
UID: NS:ntddk._WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
title: _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR (ntddk.h)
description: The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure describes a section of error information that is part of an error record.
old-location: whea\whea_error_record_section_descriptor.htm
tech.root: whea
ms.assetid: f1abbf2b-19c9-4d34-9975-4f7ab98792af
ms.date: 02/20/2018
ms.keywords: "*PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR, PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR, PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure pointer [WHEA Drivers and Applications], WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, ntddk/PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR, ntddk/WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, whea.whea_error_record_section_descriptor, whearef_91e354e5-972e-4bf2-b3e7-34e99299ee1f.xml"
f1_keywords:
 - "ntddk/WHEA_ERROR_RECORD_SECTION_DESCRIPTOR"
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
- WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR
---

# _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure


## -description


The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure describes a section of error information that is part of an <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>.


## -struct-fields




### -field SectionOffset

The offset, in bytes, from the beginning of the error record to the beginning of the error record section.


### -field SectionLength

The length, in bytes, of the error data contained in the error record section.


### -field Revision

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_revision">WHEA_REVISION</a> union that describes the revision level of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.


### -field ValidBits

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor_validbits">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field Reserved

Reserved for system use.


### -field Flags

A WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS union that describes the error record section. The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS {
  struct {
    ULONG  Primary:1;
    ULONG  ContainmentWarning:1;
    ULONG  Reset:1;
    ULONG  ThresholdExceeded:1;
    ULONG  ResourceNotAvailable:1;
    ULONG  LatentError:1;
    ULONG  Reserved:26;
  };
  ULONG  AsULONG;
} WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS;</pre>
</td>
</tr>
</table></span></div>




#### Primary

A single bit that indicates that the corresponding error record section is the primary section within the error record. When there are multiple sections contained in an error record, the primary section is the section that is used for error recovery.



#### ContainmentWarning

A single bit that indicates that the error described by the corresponding error record section was not contained within the processor or memory hierarchy. In this situation, the error might have propagated to other components of the system.



#### Reset

A single bit that indicates that the component must be reinitialized or re-enabled by the operating system.



#### ThresholdExceeded

A single bit that indicates that an error threshold has been exceeded.



#### ResourceNotAvailable

A single bit that indicates that a resource could not be queried for error information due to conflicts with other system software or resources. In this situation, some of the fields of the corresponding error record section will be invalid.



#### LatentError

A single bit that indicates that the reported error is a latent error (one not yet consumed) that could result in a more severe error when it is consumed.



#### Reserved

Reserved for system use.



#### AsULONG

A ULONG representation of the contents of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS union.


### -field SectionType

A GUID that identifies the type of error data that is contained in the error record section. The standard section types are defined as follows:





#### WHEA_PACKET_SECTION_GUID

The error record section contains the hardware error packet that was passed to the operating system by the low-level hardware error handler (LLHEH) that reported the error. This data is described by a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a> structure.



#### PROCESSOR_GENERIC_ERROR_SECTION_GUID

The error record section contains processor error data that is not specific to a particular processor architecture. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.



#### IPF_PROCESSOR_ERROR_SECTION_GUID

The error record section contains processor error data that is specific to the Itanium processor architecture. For more information about the format of the error data that is contained in this error record section, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.



#### FIRMWARE_ERROR_RECORD_REFERENCE_GUID

The error record section contains a reference to a firmware error record that is specific to the Itanium processor architecture. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_firmware_error_record_reference">WHEA_FIRMWARE_ERROR_RECORD_REFERENCE</a> structure.



#### MEMORY_ERROR_SECTION_GUID

The error record section contains platform memory error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_memory_error_section">WHEA_MEMORY_ERROR_SECTION</a> structure.



#### NMI_SECTION_GUID

The error record section contains nonmaskable interrupt (NMI) error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_nmi_error_section">WHEA_NMI_ERROR_SECTION</a> structure.



#### PCIEXPRESS_ERROR_SECTION_GUID

The error record section contains PCI Express (PCIe) error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pciexpress_error_section">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure.



#### PCIXBUS_ERROR_SECTION_GUID

The error record section contains PCI/PCI-X bus error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section">WHEA_PCIXBUS_ERROR_SECTION</a> structure.

The error record section contains PCI/PCI-X device error data. This data is described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixdevice_error_section">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure.



#### XPF_PROCESSOR_ERROR_SECTION_GUID

The error record section contains processor error data that is specific to the x86 or x64 processor architecture. This data is described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560655">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure.

For error record sections that do not conform to one of the standard section types, this member contains a platform-specific GUID that identifies the type of error data that is contained in the error record section. If a platform-specific GUID is not defined for the type of error data that is contained in the error record section, this member contains GENERIC_SECTION_GUID.


### -field FRUId

A GUID that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>ValidBits.FRUId</b> bit is set.


### -field SectionSeverity

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_severity">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition that is described by the error record section.


### -field FRUText

A character string that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>ValidBits.FRUText</b> bit is set.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a> structure contains an array of WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structures. Each descriptor describes a section of error information that is part of the error record.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record">WHEA_ERROR_RECORD</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor_validbits">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_whea_error_severity">WHEA_ERROR_SEVERITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_firmware_error_record_reference">WHEA_FIRMWARE_ERROR_RECORD_REFERENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_memory_error_section">WHEA_MEMORY_ERROR_SECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_nmi_error_section">WHEA_NMI_ERROR_SECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pciexpress_error_section">WHEA_PCIEXPRESS_ERROR_SECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section">WHEA_PCIXBUS_ERROR_SECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixdevice_error_section">WHEA_PCIXDEVICE_ERROR_SECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_processor_generic_error_section">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_revision">WHEA_REVISION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560655">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>
 

 

