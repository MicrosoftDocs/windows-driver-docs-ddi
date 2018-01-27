---
UID: NS:ntddk._WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
title: _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
author: windows-driver-content
description: The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure describes a section of error information that is part of an error record.
old-location: whea\whea_error_record_section_descriptor.htm
old-project: whea
ms.assetid: f1abbf2b-19c9-4d34-9975-4f7ab98792af
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: whea.whea_error_record_section_descriptor, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR, PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR, ntddk/PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure [WHEA Drivers and Applications], _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, ntddk/WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, whearef_91e354e5-972e-4bf2-b3e7-34e99299ee1f.xml, PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure pointer [WHEA Drivers and Applications]
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
-	WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
---

# _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure


## -description


The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure describes a section of error information that is part of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>.


## -syntax


````
typedef struct _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR {
  ULONG                                          SectionOffset;
  ULONG                                          SectionLength;
  WHEA_REVISION                                  Revision;
  WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS ValidBits;
  UCHAR                                          Reserved;
  WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS     Flags;
  GUID                                           SectionType;
  GUID                                           FRUId;
  WHEA_ERROR_SEVERITY                            SectionSeverity;
  CCHAR                                          FRUText[20];
} WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR;
````


## -struct-fields




### -field SectionOffset

The offset, in bytes, from the beginning of the error record to the beginning of the error record section.


### -field SectionLength

The length, in bytes, of the error data contained in the error record section.


### -field Revision

A <a href="..\ntddk\ns-ntddk-_whea_revision.md">WHEA_REVISION</a> union that describes the revision level of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.


### -field ValidBits

A <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor_validbits.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS</a> union that specifies which members of this structure contain valid data.


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


### -field SectionType

A GUID that identifies the type of error data that is contained in the error record section. The standard section types are defined as follows:



For error record sections that do not conform to one of the standard section types, this member contains a platform-specific GUID that identifies the type of error data that is contained in the error record section. If a platform-specific GUID is not defined for the type of error data that is contained in the error record section, this member contains GENERIC_SECTION_GUID.


### -field FRUId

A GUID that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>ValidBits.FRUId</b> bit is set.


### -field SectionSeverity

A <a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition that is described by the error record section.


### -field FRUText

A character string that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>ValidBits.FRUText</b> bit is set.


##### - SectionType.IPF_PROCESSOR_ERROR_SECTION_GUID

The error record section contains processor error data that is specific to the Itanium processor architecture. For more information about the format of the error data that is contained in this error record section, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.


##### - SectionType.PCIEXPRESS_ERROR_SECTION_GUID

The error record section contains PCI Express (PCIe) error data. This data is described by a <a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure.


##### - Flags.Reserved

Reserved for system use.


##### - Flags.AsULONG

A ULONG representation of the contents of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS union.


##### - SectionType.PROCESSOR_GENERIC_ERROR_SECTION_GUID

The error record section contains processor error data that is not specific to a particular processor architecture. This data is described by a <a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.


##### - Flags.ResourceNotAvailable

A single bit that indicates that a resource could not be queried for error information due to conflicts with other system software or resources. In this situation, some of the fields of the corresponding error record section will be invalid.


##### - Flags.LatentError

A single bit that indicates that the reported error is a latent error (one not yet consumed) that could result in a more severe error when it is consumed.


##### - Flags.Primary

A single bit that indicates that the corresponding error record section is the primary section within the error record. When there are multiple sections contained in an error record, the primary section is the section that is used for error recovery.


##### - SectionType.FIRMWARE_ERROR_RECORD_REFERENCE_GUID

The error record section contains a reference to a firmware error record that is specific to the Itanium processor architecture. This data is described by a <a href="..\ntddk\ns-ntddk-_whea_firmware_error_record_reference.md">WHEA_FIRMWARE_ERROR_RECORD_REFERENCE</a> structure.


##### - SectionType.XPF_PROCESSOR_ERROR_SECTION_GUID

The error record section contains processor error data that is specific to the x86 or x64 processor architecture. This data is described by a <a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure.


##### - Flags.ContainmentWarning

A single bit that indicates that the error described by the corresponding error record section was not contained within the processor or memory hierarchy. In this situation, the error might have propagated to other components of the system.


##### - SectionType.NMI_SECTION_GUID

The error record section contains nonmaskable interrupt (NMI) error data. This data is described by a <a href="..\ntddk\ns-ntddk-_whea_nmi_error_section.md">WHEA_NMI_ERROR_SECTION</a> structure.


##### - SectionType.WHEA_PACKET_SECTION_GUID

The error record section contains the hardware error packet that was passed to the operating system by the low-level hardware error handler (LLHEH) that reported the error. This data is described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a> structure.


##### - SectionType.PCIXBUS_ERROR_SECTION_GUID

The error record section contains PCI/PCI-X bus error data. This data is described by a <a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section.md">WHEA_PCIXBUS_ERROR_SECTION</a> structure.

The error record section contains PCI/PCI-X device error data. This data is described by a <a href="..\ntddk\ns-ntddk-_whea_pcixdevice_error_section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure.


##### - SectionType.MEMORY_ERROR_SECTION_GUID

The error record section contains platform memory error data. This data is described by a <a href="..\ntddk\ns-ntddk-_whea_memory_error_section.md">WHEA_MEMORY_ERROR_SECTION</a> structure.


##### - Flags.ThresholdExceeded

A single bit that indicates that an error threshold has been exceeded.


##### - Flags.Reset

A single bit that indicates that the component must be reinitialized or re-enabled by the operating system.


## -remarks


The <a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a> structure contains an array of WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structures. Each descriptor describes a section of error information that is part of the error record.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section.md">WHEA_PCIXBUS_ERROR_SECTION</a>

<a href="..\ntddk\ns-ntddk-_whea_error_record.md">WHEA_ERROR_RECORD</a>

<a href="..\ntddk\ns-ntddk-_whea_memory_error_section.md">WHEA_MEMORY_ERROR_SECTION</a>

<a href="..\ntddk\ns-ntddk-_whea_pcixdevice_error_section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a>

<a href="..\ntddk\ne-ntddk-_whea_error_severity.md">WHEA_ERROR_SEVERITY</a>

<a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a>

<a href="..\ntddk\ns-ntddk-_whea_firmware_error_record_reference.md">WHEA_FIRMWARE_ERROR_RECORD_REFERENCE</a>

<a href="..\ntddk\ns-ntddk-_whea_revision.md">WHEA_REVISION</a>

<a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>

<a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>

<a href="..\ntddk\ns-ntddk-_whea_nmi_error_section.md">WHEA_NMI_ERROR_SECTION</a>

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor_validbits.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

