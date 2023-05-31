---
UID: NS:ntddk._PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
title: _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER (ntddk.h)
description: The _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure (ntddk.h)  describes a PCI Express (PCIe) link capabilities register of a PCIe capability structure.
old-location: pci\pci_express_link_capabilities_register.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure"]
ms.keywords: "*PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER, PCI.pci_express_link_capabilities_register, PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, PCI_EXPRESS_LINK_CAPABILITIES_REGISTER union [Buses], PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER, PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER union pointer [Buses], _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, ntddk/PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, ntddk/PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER, pci_struct_22681134-04dc-4d7c-86a0-3d92c21ef8b3.xml"
req.header: ntddk.h
req.include-header: Ntddk.h, Miniport.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, *PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER
f1_keywords:
 - _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
 - ntddk/_PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
 - PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER
 - ntddk/PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER
 - PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
 - ntddk/PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
 - PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER
 - PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
---

# _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure (ntddk.h)



## -description

The **PCI_EXPRESS_LINK_CAPABILITIES_REGISTER** structure describes a PCI Express (PCIe) link capabilities register of a PCIe capability structure.

## -struct-fields

### -field DUMMYSTRUCTNAME

### -field AsULONG

A **ULONG** representation of the contents of the **PCI_EXPRESS_LINK_CAPABILITIES_REGISTER** structure.


### -field DUMMYSTRUCTNAME.MaximumLinkSpeed

The maximum link speed of the PCIe link (when [PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER](ns-ntddk-pci_express_link_capabilities_2_register.md) is not implemented or the value of [SupportedLinkSpeedsVector](ns-ntddk-pci_express_link_capabilities_2_register.md#members) is 0). If [PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER](ns-ntddk-pci_express_link_capabilities_2_register.md) is implemented, then **SupportedLinkSpeedsVector** is used and **MaximumLinkSpeed** is disregarded on Windows.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td><b>1</b></td>
<td>2.5 GT/s</td>
</tr>
<tr>
<td><b>2</b></td>
<td>5.0 GT/s</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved</td>
</tr>
</table>
 

### -field DUMMYSTRUCTNAME.MaximumLinkWidth

The maximum link width (number of lanes) implemented by the component. Possible values are:


<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td><b>1</b></td>
<td>x1 (1 lane)</td>
</tr>
<tr>
<td><b>2</b></td>
<td>x2 (2 lanes)</td>
</tr>
<tr>
<td><b>4</b></td>
<td>x4 (4 lanes)</td>
</tr>
<tr>
<td><b>8</b></td>
<td>x8 (8 lanes)</td>
</tr>
<tr>
<td><b>12</b></td>
<td>x12 (12 lanes)</td>
</tr>
<tr>
<td><b>16</b></td>
<td>x16 (16 lanes)</td>
</tr>
<tr>
<td><b>32</b></td>
<td>x32 (32 lanes)</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved.</td>
</tr>
</table>


### -field DUMMYSTRUCTNAME.ActiveStatePMSupport

The level of active state power management supported on the PCIe link. Possible values are:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td><b>L0sEntrySupport</b></td>
<td>L0s is supported.</td>
</tr>
<tr>
<td><b>L0sAndL1EntrySupport</b></td>
<td>L0s and L1 are supported.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved.</td>
</tr>
</table>


### -field DUMMYSTRUCTNAME.ClockPowerManagement

A single bit that indicates that the component supports clock power management.


### -field DUMMYSTRUCTNAME.DataLinkLayerActiveReportingCapable

A single bit that indicates that the component supports the optional capability of reporting the data link active state of the data link control and management state machine. This bit only applies to downstream ports. Hot-plug capable downstream ports must support this capability.


### -field DUMMYSTRUCTNAME.L0sExitLatency

The L0s exit latency for the PCIe link. This value indicates the length of time this port requires to complete a transition from L0s to L0.


<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td><b>L0s_Below64ns</b></td>
<td>Less than 64 nanoseconds</td>
</tr>
<tr>
<td><b>L0s_64ns_128ns</b></td>
<td>64 nanoseconds to 128 nanoseconds</td>
</tr>
<tr>
<td><b>L0s_128ns_256ns</b></td>
<td>128 nanoseconds to 256 nanoseconds</td>
</tr>
<tr>
<td><b>L0s_256ns_512ns</b></td>
<td>256 nanoseconds to 512 nanoseconds</td>
</tr>
<tr>
<td><b>L0s_512ns_1us</b></td>
<td>512 nanoseconds to 1 microsecond</td>
</tr>
<tr>
<td><b>L0s_1us_2us</b></td>
<td>1 microsecond to 2 microseconds</td>
</tr>
<tr>
<td><b>L0s_2us_4us</b></td>
<td>2 microseconds to 4 microseconds</td>
</tr>
<tr>
<td><b>L0s_Above4us</b></td>
<td>More than 4 microseconds</td>
</tr>
</table>


### -field DUMMYSTRUCTNAME.L1ExitLatency

The L1 exit latency for the PCIe link. This value indicates the length of time this port requires to complete a transition from L1 to L0.


<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td><b>L1_Below1us</b></td>
<td>Less than 1 microsecond</td>
</tr>
<tr>
<td><b>L1_1us_2us</b></td>
<td>1 microsecond to 2 microseconds</td>
</tr>
<tr>
<td><b>L1_2us_4us</b></td>
<td>2 microseconds to 4 microseconds</td>
</tr>
<tr>
<td><b>L1_4us_8us</b></td>
<td>4 microseconds to 8 microseconds</td>
</tr>
<tr>
<td><b>L1_8us_16us</b></td>
<td>8 microseconds to 16 microseconds</td>
</tr>
<tr>
<td><b>L1_16us_32us</b></td>
<td>16 microseconds to 32 microseconds</td>
</tr>
<tr>
<td><b>L1_32us_64us</b></td>
<td>32 microseconds to 64 microseconds</td>
</tr>
<tr>
<td><b>L1_Above64us</b></td>
<td>More than 64 microseconds</td>
</tr>
</table>


This value is ignored if the <b>ActiveStatePMSupport </b>member is not set to <b>L0sAndL1EntrySupport</b>.

### -field DUMMYSTRUCTNAME.SurpriseDownErrorReportingCapable

A single bit that indicates that the component supports the optional capability of detecting and reporting a surprise-down error condition. This bit only applies to downstream ports.

### -field DUMMYSTRUCTNAME.LinkBandwidthNotificationCapability

### -field DUMMYSTRUCTNAME.AspmOptionalityCompliance


### -field DUMMYSTRUCTNAME.Rsvd

Reserved.

### -field DUMMYSTRUCTNAME.PortNumber

The PCIe port number for the PCIe link.


## -syntax

```cpp
typedef union _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER {
  struct {
    ULONG MaximumLinkSpeed  :4;
    ULONG MaximumLinkWidth  :6;
    ULONG ActiveStatePMSupport  :2;
    ULONG L0sExitLatency  :3;
    ULONG L1ExitLatency  :3;
    ULONG ClockPowerManagement  :1;
    ULONG SurpriseDownErrorReportingCapable  :1;
    ULONG DataLinkLayerActiveReportingCapable  :1;
    ULONG LinkBandwidthNotificationCapability:1;
    ULONG AspmOptionalityCompliance:1;
    ULONG Rsvd  :1;
    ULONG PortNumber  :8;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, *PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER;
```

## -remarks

The **PCI_EXPRESS_LINK_CAPABILITIES_REGISTER** structure is available in Windows Server 2008 and later versions of Windows.

A **PCI_EXPRESS_LINK_CAPABILITIES_REGISTER** structure is contained in the [PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md) structure.

## -see-also

[PCI_EXPRESS_CAPABILITY_REGISTER](ns-ntddk-_pci_express_capability.md)

[PCI_EXPRESS_LINK_CAPABILITIES_2_REGISTER](ns-ntddk-pci_express_link_capabilities_2_register.md)
