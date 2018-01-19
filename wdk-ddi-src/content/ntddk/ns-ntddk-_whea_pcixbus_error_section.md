---
UID: NS:ntddk._WHEA_PCIXBUS_ERROR_SECTION
title: _WHEA_PCIXBUS_ERROR_SECTION
author: windows-driver-content
description: The WHEA_PCIXBUS_ERROR_SECTION structure describes PCI or PCI-X bus error data.
old-location: whea\whea_pcixbus_error_section.htm
old-project: whea
ms.assetid: f79071e3-7146-49c4-a730-ee13fde4f0d4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WHEA_PCIXBUS_ERROR_SECTION, WHEA_PCIXBUS_ERROR_SECTION, *PWHEA_PCIXBUS_ERROR_SECTION, *PWHEA_PCIXBUS_ERROR, WHEA_PCIXBUS_ERROR
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
req.alt-api: WHEA_PCIXBUS_ERROR_SECTION
req.alt-loc: ntddk.h
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
req.typenames: WHEA_PCIXBUS_ERROR_SECTION, *PWHEA_PCIXBUS_ERROR_SECTION
---

# _WHEA_PCIXBUS_ERROR_SECTION structure



## -description
The WHEA_PCIXBUS_ERROR_SECTION structure describes PCI or PCI-X bus error data.



## -syntax

````
typedef struct _WHEA_PCIXBUS_ERROR_SECTION {
  WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS ValidBits;
  WHEA_ERROR_STATUS                    ErrorStatus;
  USHORT                               ErrorType;
  WHEA_PCIXBUS_ID                      BusId;
  ULONG                                Reserved;
  ULONGLONG                            BusAddress;
  ULONGLONG                            BusData;
  WHEA_PCIXBUS_COMMAND                 BusCommand;
  ULONGLONG                            RequesterId;
  ULONGLONG                            CompleterId;
  ULONGLONG                            TargetId;
} WHEA_PCIXBUS_ERROR_SECTION, *PWHEA_PCIXBUS_ERROR_SECTION;
````


## -struct-fields

### -field ValidBits

A <a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section_validbits.md">WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field ErrorStatus

A <a href="..\ntddk\ns-ntddk-_whea_error_status.md">WHEA_ERROR_STATUS</a> structure that contains PCI or PCI-X bus error status data.

This member contains valid data only if the <b>ValidBits.ErrorStatus</b> bit is set.


### -field ErrorType

The type of PCI or PCI-X bus error that occurred. Possible values are:




### -field PCIXBUS_ERRTYPE_UNKNOWN

An unknown or platform-specific error.


### -field PCIXBUS_ERRTYPE_DATAPARITY

A data parity error.


### -field PCIXBUS_ERRTYPE_SYSTEM

A system error.


### -field PCIXBUS_ERRTYPE_MASTERABORT

A master abort.


### -field PCIXBUS_ERRTYPE_BUSTIMEOUT

A bus timeout, or no device is present.


### -field PCIXBUS_ERRTYPE_MASTERDATAPARITY

A master data parity error.


### -field PCIXBUS_ERRTYPE_ADDRESSPARITY

An address parity error.


### -field PCIXBUS_ERRTYPE_COMMANDPARITY

A command parity error.

</dd>
</dl>
This member contains valid data only if the <b>ValidBits.ErrorType</b> bit is set.


### -field BusId

A WHEA_PCIXBUS_ID union that identifies the bus where the error occurred. The WHEA_PCIXBUS_ID union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_PCIXBUS_ID {
  struct {
    UCHAR  BusNumber;
    UCHAR  BusSegment;
  };
  USHORT  AsUSHORT;
} WHEA_PCIXBUS_ID, *PWHEA_PCIXBUS_ID;</pre>
</td>
</tr>
</table></span></div>



### -field BusNumber

The bus number.


### -field BusSegment

The bus segment.


### -field AsUSHORT

A USHORT representation of the contents of the WHEA_PCIXBUS_ID union.

</dd>
</dl>
This member contains valid data only if the <b>ValidBits.BusId</b> bit is set.


### -field Reserved

Reserved for system use.


### -field BusAddress

The memory or I/O address on the bus when the error occurred.

This member contains valid data only if the <b>ValidBits.BusAddress</b> bit is set.


### -field BusData

The data on the bus when the error occurred.

This member contains valid data only if the <b>ValidBits.BusData</b> bit is set.


### -field BusCommand

A WHEA_PCIXBUS_COMMAND union that contains the bus command when the error occurred. The WHEA_PCIXBUS_COMMAND union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_PCIXBUS_COMMAND {
  struct {
    ULONGLONG  Command:56;
    ULONGLONG  PCIXCommand:1;
    ULONGLONG  Reserved:7;
  };
  ULONGLONG  AsULONGLONG;
} WHEA_PCIXBUS_COMMAND, *PWHEA_PCIXBUS_COMMAND;</pre>
</td>
</tr>
</table></span></div>



### -field Command

The PCI or PCI-X bus command.


### -field PCIXCommand

A single bit that indicates that the command is a PCI-X command.


### -field Reserved

Reserved for system use.


### -field AsULONGLONG

A ULONGLONG representation of the contents of the WHEA_PCIXBUS_COMMAND union.

</dd>
</dl>
This member contains valid data only if the <b>ValidBits.BusCommand</b> bit is set.


### -field RequesterId

An identifier that uniquely identifies the requester that is associated with the error.

This member contains valid data only if the <b>ValidBits.RequesterId</b> bit is set.


### -field CompleterId

An identifier that uniquely identifies the PCI bus responder that is associated with the error.

This member contains valid data only if the <b>ValidBits.CompleterId</b> bit is set.


### -field TargetId

An identifier that uniquely identifies the intended target of the PCI bus command.

This member contains valid data only if the <b>ValidBits.TargetId</b> bit is set.


## -remarks
The WHEA_PCIXBUS_ERROR_SECTION structure describes the error data that is contained in a PCI/PCI-X bus error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a PCI/PCI-X bus error section only if the <b>SectionType </b>member of one of the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains PCIXBUS_ERROR_SECTION_GUID.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_error_status.md">WHEA_ERROR_STATUS</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-_whea_pcixbus_error_section_validbits.md">WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PCIXBUS_ERROR_SECTION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

