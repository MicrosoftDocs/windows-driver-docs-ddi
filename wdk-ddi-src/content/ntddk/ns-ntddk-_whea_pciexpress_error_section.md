---
UID: NS:ntddk._WHEA_PCIEXPRESS_ERROR_SECTION
title: "_WHEA_PCIEXPRESS_ERROR_SECTION"
author: windows-driver-content
description: The WHEA_PCIEXPRESS_ERROR_SECTION structure describes PCI Express (PCIe) error data.
old-location: whea\whea_pciexpress_error_section.htm
old-project: whea
ms.assetid: 1d96a799-6e52-49e0-b440-a8643111176f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PCIEXPRESS_ERROR, *PWHEA_PCIEXPRESS_ERROR_SECTION, PWHEA_PCIEXPRESS_ERROR_SECTION, PWHEA_PCIEXPRESS_ERROR_SECTION structure pointer [WHEA Drivers and Applications], WHEA_PCIEXPRESS_ERROR, WHEA_PCIEXPRESS_ERROR_SECTION, WHEA_PCIEXPRESS_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_PCIEXPRESS_ERROR_SECTION, ntddk/PWHEA_PCIEXPRESS_ERROR_SECTION, ntddk/WHEA_PCIEXPRESS_ERROR_SECTION, whea.whea_pciexpress_error_section, whearef_77796d60-3376-4d78-9b24-9ddb1e3d6132.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_PCIEXPRESS_ERROR_SECTION
product: Windows
targetos: Windows
req.typenames: WHEA_PCIEXPRESS_ERROR_SECTION, *PWHEA_PCIEXPRESS_ERROR_SECTION
---

# _WHEA_PCIEXPRESS_ERROR_SECTION structure


## -description


The WHEA_PCIEXPRESS_ERROR_SECTION structure describes PCI Express (PCIe) error data.


## -syntax


````
typedef struct _WHEA_PCIEXPRESS_ERROR_SECTION {
  WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS ValidBits;
  WHEA_PCIEXPRESS_DEVICE_TYPE             PortType;
  WHEA_PCIEXPRESS_VERSION                 Version;
  WHEA_PCIEXPRESS_COMMAND_STATUS          CommandStatus;
  ULONG                                   Reserved;
  WHEA_PCIEXPRESS_DEVICE_ID               DeviceId;
  ULONGLONG                               DeviceSerialNumber;
  WHEA_PCIEXPRESS_BRIDGE_CONTROL_STATUS   BridgeControlStatus;
  UCHAR                                   ExpressCapability[60];
  UCHAR                                   AerInfo[96];
} WHEA_PCIEXPRESS_ERROR_SECTION, *PWHEA_PCIEXPRESS_ERROR_SECTION;
````


## -struct-fields




### -field ValidBits

A <a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section_validbits.md">WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS</a> union that specifies which members of this structure contain valid data.


### -field PortType

The device type or port type of the PCIe component where the error occurred. Possible values are:





#### WheaPciExpressEndpoint

A PCIe endpoint device.



#### WheaPciExpressLegacyEndpoint

A legacy PCIe endpoint device.



#### WheaPciExpressRootPort

A root port of a PCIe root complex.



#### WheaPciExpressUpstreamSwitchPort

An upstream port of a PCIe switch.



#### WheaPciExpressDownstreamSwitchPort

A downstream port of a PCIe switch.



#### WheaPciExpressToPciXBridge

A PCIe-to-PCI or PCI-X bridge.



#### WheaPciXToExpressBridge

A PCI or PCI-X-to-PCIe bridge.



#### WheaPciExpressRootComplexIntegratedEndpoint

A PCIe endpoint device that is integrated into the root complex.



#### WheaPciExpressRootComplexEventCollector

A PCIe root complex event collector.

This member contains valid data only if the <b>ValidBits.PortType</b> bit is set.


### -field Version

A WHEA_PCIEXPRESS_VERSION union that contains the version of the PCIe specification that is supported by the hardware platform. The WHEA_PCIEXPRESS_VERSION union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_PCIEXPRESS_VERSION {
  struct {
    UCHAR  MinorVersion;
    UCHAR  MajorVersion;
    USHORT  Reserved;
  };
  ULONG  AsULONG;
} WHEA_PCIEXPRESS_VERSION, *PWHEA_PCIEXPRESS_VERSION;</pre>
</td>
</tr>
</table></span></div>




#### MinorVersion

The minor version number.



#### MajorVersion

The major version number.



#### Reserved

Reserved for system use.



#### AsULONG

A ULONG representation of the contents of the WHEA_PCIEXPRESS_VERSION union.

This member contains valid data only if the <b>ValidBits.Version</b> bit is set.


### -field CommandStatus

A WHEA_PCIEXPRESS_COMMAND_STATUS union that contains the contents of the PCI command and status registers of the PCIe device where the error occurred. The WHEA_PCIEXPRESS_COMMAND_STATUS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_PCIEXPRESS_COMMAND_STATUS {
  struct {
    USHORT  Command;
    USHORT  Status;
  };
  ULONG  AsULONG;
} WHEA_PCIEXPRESS_COMMAND_STATUS, *PWHEA_PCIEXPRESS_COMMAND_STATUS;</pre>
</td>
</tr>
</table></span></div>




#### Command

The contents of the PCI command register.



#### Status

The contents of the PCI status register.



#### AsULONG

A ULONG representation of the contents of the WHEA_PCIEXPRESS_COMMAND_STATUS union.

This member contains valid data only if the <b>ValidBits.CommandStatus</b> bit is set.


### -field Reserved

Reserved for system use.


### -field DeviceId

A WHEA_PCIEXPRESS_DEVICE_ID structure that contains data that identifies the PCIe device where the error occurred. The WHEA_PCIEXPRESS_DEVICE_ID structure is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _WHEA_PCIEXPRESS_DEVICE_ID {
  USHORT  VendorID;
  USHORT  DeviceID;
  ULONG  ClassCode:24;
  ULONG  FunctionNumber:8;
  ULONG  DeviceNumber:8;
  ULONG  Segment:16;
  ULONG  PrimaryBusNumber:8;
  ULONG  SecondaryBusNumber:8;
  ULONG Reserved1:3;
  ULONG SlotNumber:13;  ULONG  Reserved2:8;
} WHEA_PCIEXPRESS_DEVICE_ID, *PWHEA_PCIEXPRESS_DEVICE_ID;</pre>
</td>
</tr>
</table></span></div>




#### VendorID

The vendor ID of the device.



#### DeviceId

The device ID of the device.



#### ClassCode

The class code of the device.



#### FunctionNumber

The function number of the device on the bus.



#### DeviceNumber

The device number of the device on the bus.



#### Segment

The number of the bus segment that contains the device.



#### PrimaryBusNumber

The root port/bridge primary bus number or the device bus number.



#### SecondaryBusNumber

The root port/bridge secondary bus number.



#### Reserved1

Reserved for system use.



#### SlotNumber

The slot number where the device is located in the system.



#### Reserved2

Reserved for system use.

This member contains valid data only if the <b>ValidBits.DeviceId</b> bit is set.


### -field DeviceSerialNumber

The serial number of the PCIe device where the error occurred.

This member contains valid data only if the <b>ValidBits.DeviceSerialNumber</b> bit is set.


### -field BridgeControlStatus

A WHEA_PCIEXPRESS_BRIDGE_CONTROL_STATUS union that contains the contents of the PCI control and secondary status registers of the bridge device where the error occurred. The WHEA_PCIEXPRESS_BRIDGE_CONTROL_STATUS union is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_PCIEXPRESS_BRIDGE_CONTROL_STATUS {
  struct {
    USHORT  BridgeSecondaryStatus;
    USHORT  BridgeControl;
  };
  ULONG  AsULONG;
} WHEA_PCIEXPRESS_BRIDGE_CONTROL_STATUS, *PWHEA_PCIEXPRESS_BRIDGE_CONTROL_STATUS;</pre>
</td>
</tr>
</table></span></div>




#### BridgeSecondaryStatus

The contents of the secondary status register of the bridge device.



#### BridgeControl

The contents of the control register of the bridge device.



#### AsULONG

A ULONG representation of the contents of the WHEA_PCIEXPRESS_BRIDGE_CONTROL_STATUS union.

This member contains valid data only if the <b>ValidBits.BridgeControlStatus</b> bit is set.


### -field ExpressCapability

A buffer that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure that describes the PCIe capability structure for the device where the error occurred.

This member contains valid data only if the <b>ValidBits.ExpressCapability</b> bit is set.


### -field AerInfo

A buffer that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a> structure that describes the PCIe advanced error reporting (AER) extended capability structure for the device where the error occurred.

This member contains valid data only if the <b>ValidBits.AerInfo</b> bit is set.


## -remarks



The WHEA_PCIEXPRESS_ERROR_SECTION structure describes the error data that is contained in a PCI Express (PCIe) error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a PCIe error section only if the <b>SectionType </b>member of one of the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains PCIEXPRESS_ERROR_SECTION_GUID.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section_validbits.md">WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS</a>



<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560465">WHEA_ERROR_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537457">PCI_EXPRESS_AER_CAPABILITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>



 

 


