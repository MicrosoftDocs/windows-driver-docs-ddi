---
UID: NS:ntddk._WHEA_PCIXBUS_ERROR_SECTION
title: _WHEA_PCIXBUS_ERROR_SECTION (ntddk.h)
description: The WHEA_PCIXBUS_ERROR_SECTION structure describes PCI or PCI-X bus error data.
old-location: whea\whea_pcixbus_error_section.htm
tech.root: whea
ms.assetid: f79071e3-7146-49c4-a730-ee13fde4f0d4
ms.date: 02/20/2018
keywords: ["WHEA_PCIXBUS_ERROR_SECTION structure"]
ms.keywords: "*PWHEA_PCIXBUS_ERROR, *PWHEA_PCIXBUS_ERROR_SECTION, PWHEA_PCIXBUS_ERROR_SECTION, PWHEA_PCIXBUS_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_PCIXBUS_ERROR, WHEA_PCIXBUS_ERROR_SECTION, WHEA_PCIXBUS_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_PCIXBUS_ERROR_SECTION, ntddk/PWHEA_PCIXBUS_ERROR_SECTION, ntddk/WHEA_PCIXBUS_ERROR_SECTION, whea.whea_pcixbus_error_section, whearef_6979fd7e-8c18-443b-b9be-1e78316dcd7d.xml"
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
targetos: Windows
req.typenames: WHEA_PCIXBUS_ERROR_SECTION, *PWHEA_PCIXBUS_ERROR_SECTION
f1_keywords:
 - _WHEA_PCIXBUS_ERROR_SECTION
 - ntddk/_WHEA_PCIXBUS_ERROR_SECTION
 - PWHEA_PCIXBUS_ERROR_SECTION
 - ntddk/PWHEA_PCIXBUS_ERROR_SECTION
 - WHEA_PCIXBUS_ERROR_SECTION
 - ntddk/WHEA_PCIXBUS_ERROR_SECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WHEA_PCIXBUS_ERROR_SECTION
---

# _WHEA_PCIXBUS_ERROR_SECTION structure


## -description

The WHEA_PCIXBUS_ERROR_SECTION structure describes PCI or PCI-X bus error data.

## -struct-fields

### -field ValidBits

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section_validbits">WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.

### -field ErrorStatus

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_status">WHEA_ERROR_STATUS</a> structure that contains PCI or PCI-X bus error status data.

This member contains valid data only if the <b>ValidBits.ErrorStatus</b> bit is set.

### -field ErrorType

The type of PCI or PCI-X bus error that occurred. Possible values are:





#### PCIXBUS_ERRTYPE_UNKNOWN

An unknown or platform-specific error.



#### PCIXBUS_ERRTYPE_DATAPARITY

A data parity error.



#### PCIXBUS_ERRTYPE_SYSTEM

A system error.



#### PCIXBUS_ERRTYPE_MASTERABORT

A master abort.



#### PCIXBUS_ERRTYPE_BUSTIMEOUT

A bus timeout, or no device is present.



#### PCIXBUS_ERRTYPE_MASTERDATAPARITY

A master data parity error.



#### PCIXBUS_ERRTYPE_ADDRESSPARITY

An address parity error.



#### PCIXBUS_ERRTYPE_COMMANDPARITY

A command parity error.

This member contains valid data only if the <b>ValidBits.ErrorType</b> bit is set.

### -field BusId

A WHEA_PCIXBUS_ID union that identifies the bus where the error occurred. The WHEA_PCIXBUS_ID union is defined as follows:


```cpp
typedef union _WHEA_PCIXBUS_ID {
  struct {
    UCHAR  BusNumber;
    UCHAR  BusSegment;
  };
  USHORT  AsUSHORT;
} WHEA_PCIXBUS_ID, *PWHEA_PCIXBUS_ID;
```





#### BusNumber

The bus number.



#### BusSegment

The bus segment.



#### AsUSHORT

A USHORT representation of the contents of the WHEA_PCIXBUS_ID union.

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


```cpp
typedef union _WHEA_PCIXBUS_COMMAND {
  struct {
    ULONGLONG  Command:56;
    ULONGLONG  PCIXCommand:1;
    ULONGLONG  Reserved:7;
  };
  ULONGLONG  AsULONGLONG;
} WHEA_PCIXBUS_COMMAND, *PWHEA_PCIXBUS_COMMAND;
```





#### Command

The PCI or PCI-X bus command.



#### PCIXCommand

A single bit that indicates that the command is a PCI-X command.



#### Reserved

Reserved for system use.



#### AsULONGLONG

A ULONGLONG representation of the contents of the WHEA_PCIXBUS_COMMAND union.

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

The WHEA_PCIXBUS_ERROR_SECTION structure describes the error data that is contained in a PCI/PCI-X bus error section of an <a href="https://docs.microsoft.com/windows-hardware/drivers/whea/error-records">error record</a>. An error record contains a PCI/PCI-X bus error section only if the <b>SectionType </b>member of one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains PCIXBUS_ERROR_SECTION_GUID.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560465(v=vs.85)">WHEA_ERROR_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_status">WHEA_ERROR_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pcixbus_error_section_validbits">WHEA_PCIXBUS_ERROR_SECTION_VALIDBITS</a>

