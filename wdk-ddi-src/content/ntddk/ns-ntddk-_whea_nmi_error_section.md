---
UID: NS:ntddk._WHEA_NMI_ERROR_SECTION
title: "_WHEA_NMI_ERROR_SECTION"
author: windows-driver-content
description: The WHEA_NMI_ERROR_SECTION structure describes nonmaskable interrupt (NMI) error data.
old-location: whea\whea_nmi_error_section.htm
old-project: whea
ms.assetid: 960186a4-09ca-4636-b704-166137da6113
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_NMI_ERROR_SECTION, PWHEA_NMI_ERROR_SECTION, PWHEA_NMI_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_NMI_ERROR_SECTION, WHEA_NMI_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_NMI_ERROR_SECTION, ntddk/PWHEA_NMI_ERROR_SECTION, ntddk/WHEA_NMI_ERROR_SECTION, whea.whea_nmi_error_section, whearef_295c8b30-1ec5-41a3-ba50-f00c1b1b5524.xml"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_NMI_ERROR_SECTION
product:
- Windows
targetos: Windows
req.typenames: WHEA_NMI_ERROR_SECTION, *PWHEA_NMI_ERROR_SECTION
---

# _WHEA_NMI_ERROR_SECTION structure


## -description


The WHEA_NMI_ERROR_SECTION structure describes nonmaskable interrupt (NMI) error data.


## -struct-fields




### -field Data

An 8-byte data buffer that contains the data that was read from the NMI I/O ports by the NMI low-level hardware error handler (LLHEH).


### -field Flags

A WHEA_NMI_ERROR__SECTION_FLAGS union that describes the source of the NMI error. The WHEA_NMI_ERROR_FLAGS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_NMI_ERROR_SECTION_FLAGS {
  struct {
    ULONG  HypervisorError:1;
    ULONG  Reserved:31;
  };
  ULONG  AsULONG;
} WHEA_NMI_ERROR_SECTION_FLAGS, *PWHEA_NMI_ERROR_SECTION_FLAGS;</pre>
</td>
</tr>
</table></span></div>




#### HypervisorError

A hypervisor error has occurred.



#### Reserved

Reserved for system use.



#### AsULONG

A ULONG representation of the contents of the WHEA_NMI_ERROR_SECTION_FLAGS union.


## -remarks



The WHEA_NMI_ERROR_SECTION structure describes the error data contained in a nonmaskable interrupt (NMI) error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains an NMI error section only if the <b>SectionType </b>member of one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains NMI_SECTION_GUID.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
 

 

