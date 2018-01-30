---
UID: NS:ntddk._PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
title: "_PCI_EXPRESS_LINK_CAPABILITIES_REGISTER"
author: windows-driver-content
description: The PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) link capabilities register of a PCIe capability structure.
old-location: pci\pci_express_link_capabilities_register.htm
old-project: PCI
ms.assetid: d49d1deb-cb98-4dc0-9ec5-7015b765c9e4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI.pci_express_link_capabilities_register, pci_struct_22681134-04dc-4d7c-86a0-3d92c21ef8b3.xml, PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, PCI_EXPRESS_LINK_CAPABILITIES_REGISTER union [Buses], ntddk/PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, ntddk/PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER, PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER, _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER union pointer [Buses], *PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PCI_EXPRESS_LINK_CAPABILITIES_REGISTER
product: Windows
targetos: Windows
req.typenames: "*PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER, PCI_EXPRESS_LINK_CAPABILITIES_REGISTER"
---

# _PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure


## -description


The PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure describes a PCI Express (PCIe) link capabilities register of a PCIe capability structure.


## -syntax


````
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
    ULONG Rsvd  :3;
    ULONG PortNumber  :8;
  };
  ULONG  AsULONG;
} PCI_EXPRESS_LINK_CAPABILITIES_REGISTER, *PPCI_EXPRESS_LINK_CAPABILITIES_REGISTER;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.MaximumLinkSpeed

 


### -field DUMMYSTRUCTNAME.MaximumLinkWidth

 


### -field DUMMYSTRUCTNAME.ActiveStatePMSupport

 


### -field DUMMYSTRUCTNAME.L0sExitLatency

 


### -field DUMMYSTRUCTNAME.L1ExitLatency

 


### -field DUMMYSTRUCTNAME.ClockPowerManagement

 


### -field DUMMYSTRUCTNAME.SurpriseDownErrorReportingCapable

 


### -field DUMMYSTRUCTNAME.DataLinkLayerActiveReportingCapable

 


### -field DUMMYSTRUCTNAME.LinkBandwidthNotificationCapability

 


### -field DUMMYSTRUCTNAME.AspmOptionalityCompliance

 


### -field DUMMYSTRUCTNAME.Rsvd

 


### -field DUMMYSTRUCTNAME.PortNumber

 


### -field AsULONG

A ULONG representation of the contents of the PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure.


#### - MaximumLinkSpeed

The maximum link speed of the PCIe link. The only valid value is:



All other values are reserved.


#### 1

2.5 gigabits per second


#### - MaximumLinkWidth

The maximum link width (number of lanes) implemented by the component. Possible values are:



All other values are reserved.


#### 1

x1 (1 lane)


#### 2

x2 (2 lanes)


#### 4

x4 (4 lanes)


#### 8

x8 (8 lanes)


#### 12

x12 (12 lanes)


#### 16

x16 (16 lanes)


#### 32

x32 (32 lanes)


#### - ActiveStatePMSupport

The level of active state power management supported on the PCIe link. Possible values are:



All other values are reserved.


#### L0sEntrySupport

L0s is supported.


#### L0sAndL1EntrySupport

L0s and L1 are supported.


#### - L0sExitLatency

The L0s exit latency for the PCIe link. This value indicates the length of time this port requires to complete a transition from L0s to L0.




#### L0s_Below64ns

Less than 64 nanoseconds


#### L0s_64ns_128ns

64 nanoseconds to 128 nanoseconds


#### L0s_128ns_256ns

128 nanoseconds to 256 nanoseconds


#### L0s_256ns_512ns

256 nanoseconds to 512 nanoseconds


#### L0s_512ns_1us

512 nanoseconds to 1 microsecond


#### L0s_1us_2us

1 microsecond to 2 microseconds


#### L0s_2us_4us

2 microseconds to 4 microseconds


#### L0s_Above4us

More than 4 microseconds


#### - L1ExitLatency

The L1 exit latency for the PCIe link. This value indicates the length of time this port requires to complete a transition from L1 to L0.



This value is ignored if the <b>ActiveStatePMSupport </b>member is not set to <b>L0sAndL1EntrySupport</b>.


#### L1_Below1us

Less than 1 microsecond


#### L1_1us_2us

1 microsecond to 2 microseconds


#### L1_2us_4us

2 microseconds to 4 microseconds


#### L1_4us_8us

4 microseconds to 8 microseconds


#### L1_8us_16us

8 microseconds to 16 microseconds


#### L1_16us_32us

16 microseconds to 32 microseconds


#### L1_32us_64us

32 microseconds to 64 microseconds


#### L1_Above64us

More than 64 microseconds


#### - ClockPowerManagement

A single bit that indicates that the component supports clock power management.


#### - SurpriseDownErrorReportingCapable

A single bit that indicates that the component supports the optional capability of detecting and reporting a surprise-down error condition. This bit only applies to downstream ports.


#### - DataLinkLayerActiveReportingCapable

A single bit that indicates that the component supports the optional capability of reporting the data link active state of the data link control and management state machine. This bit only applies to downstream ports. Hot-plug capable downstream ports must support this capability.


#### - Rsvd

Reserved.


#### - PortNumber

The PCIe port number for the PCIe link.


## -remarks


The PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure is available in Windows Server 2008 and later versions of Windows.

A PCI_EXPRESS_LINK_CAPABILITIES_REGISTER structure is contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a> structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537460">PCI_EXPRESS_CAPABILITY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\buses]:%20PCI_EXPRESS_LINK_CAPABILITIES_REGISTER union%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

