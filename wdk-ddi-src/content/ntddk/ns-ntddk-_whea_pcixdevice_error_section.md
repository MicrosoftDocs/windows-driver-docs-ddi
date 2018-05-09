---
UID: NS:ntddk._WHEA_PCIXDEVICE_ERROR_SECTION
title: "_WHEA_PCIXDEVICE_ERROR_SECTION"
author: windows-driver-content
description: The WHEA_PCIXDEVICE_ERROR_SECTION structure describes PCI or PCI-X device error data.
old-location: whea\whea_pcixdevice_error_section.htm
old-project: whea
ms.assetid: 0d2ec4e5-193d-45bf-8588-6afc1a9fb68c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PCIXDEVICE_ERROR, *PWHEA_PCIXDEVICE_ERROR_SECTION, PWHEA_PCIXDEVICE_ERROR_SECTION, PWHEA_PCIXDEVICE_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_PCIXDEVICE_ERROR, WHEA_PCIXDEVICE_ERROR_SECTION, WHEA_PCIXDEVICE_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_PCIXDEVICE_ERROR_SECTION, ntddk/PWHEA_PCIXDEVICE_ERROR_SECTION, ntddk/WHEA_PCIXDEVICE_ERROR_SECTION, whea.whea_pcixdevice_error_section, whearef_79293b09-c49f-499f-9423-319265088a26.xml"
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
-	WHEA_PCIXDEVICE_ERROR_SECTION
product:
- Windows
targetos: Windows
req.typenames: WHEA_PCIXDEVICE_ERROR_SECTION, *PWHEA_PCIXDEVICE_ERROR_SECTION
---

# _WHEA_PCIXDEVICE_ERROR_SECTION structure


## -description


The WHEA_PCIXDEVICE_ERROR_SECTION structure describes PCI or PCI-X device error data.


## -struct-fields




### -field ValidBits

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560591">WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field ErrorStatus

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560514">WHEA_ERROR_STATUS</a> structure that contains PCI or PCI-X device error status data.

This member contains valid data only if the <b>ValidBits.ErrorStatus</b> bit is set.


### -field IdInfo

A WHEA_PCIXDEVICE_ID structure that contains data that identifies the PCI or PCI-X device. The WHEA_PCIXDEVICE_ID structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _WHEA_PCIXDEVICE_ID {
  USHORT  VendorId;
  USHORT  DeviceId;
  ULONG  ClassCode:24;
  ULONG  FunctionNumber:8;
  ULONG  DeviceNumber:8;
  ULONG  BusNumber:8;
  ULONG  SegmentNumber:8;
  ULONG  Reserved1:8;
  ULONG  Reserved2;
} WHEA_PCIXDEVICE_ID, *PWHEA_PCIXDEVICE_ID;</pre>
</td>
</tr>
</table></span></div>




#### VendorId

The vendor ID of the device.



#### DeviceId

The device ID of the device.



#### ClassCode

The class code of the device.



#### FunctionNumber

The function number of the device on the bus.



#### DeviceNumber

The device number of the device on the bus.



#### BusNumber

The number of the bus that contains the device.



#### SegmentNumber

The number of the bus segment that contains the device.



#### Reserved1

Reserved for system use.



#### Reserved2

Reserved for system use.

This member contains valid data only if the <b>ValidBits.IdInfo</b> bit is set.


### -field MemoryNumber

The number of memory mapped register address/data pair values from the PCI device that are included in the <b>RegisterDataPairs</b> member.

This member contains valid data only if the <b>ValidBits.MemoryNumber</b> bit is set.


### -field IoNumber

The number of I/O mapped register address/data pair values from the PCI device that are included in the <b>RegisterDataPairs</b> member.

This member contains valid data only if the <b>ValidBits.IoNumber</b> bit is set.


### -field RegisterDataPairs

An array of WHEA_PCIXDEVICE_REGISTER_PAIR structures that contains the register address/data pair values for the PCI device. The WHEA_PCIXDEVICE_REGISTER_PAIR structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct WHEA_PCIXDEVICE_REGISTER_PAIR {
  ULONGLONG  Register;
  ULONGLONG  Data;
} WHEA_PCIXDEVICE_REGISTER_PAIR, *PWHEA_PCIXDEVICE_REGISTER_PAIR;</pre>
</td>
</tr>
</table></span></div>




#### Register

The address of the register.



#### Data

The data contained in the register.

This member contains valid data only if the <b>ValidBits.RegisterDataPairs</b> bit is set.


## -remarks



The WHEA_PCIXDEVICE_ERROR_SECTION structure describes the error data that is contained in a PCI/PCI-X device error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a PCI/PCI-X device error section only if the <b>SectionType </b>member of one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains PCIXBUS_ERROR_SECTION_GUID.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560496">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560514">WHEA_ERROR_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560591">WHEA_PCIXDEVICE_ERROR_SECTION_VALIDBITS</a>
 

 

