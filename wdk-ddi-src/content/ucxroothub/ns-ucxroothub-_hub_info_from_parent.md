---
UID: NS:ucxroothub._HUB_INFO_FROM_PARENT
title: "_HUB_INFO_FROM_PARENT"
author: windows-driver-content
description: Describes information about a hub from its parent device.
old-location: buses\_hub_info_from_parent.htm
old-project: usbref
ms.assetid: 6259CC70-A54B-4A44-B38B-D24C296C8EA0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHUB_INFO_FROM_PARENT, HUB_INFO_FROM_PARENT, HUB_INFO_FROM_PARENT structure [Buses], P_HUB_INFO_FROM_PARENT, P_HUB_INFO_FROM_PARENT structure pointer [Buses], _HUB_INFO_FROM_PARENT, buses._hub_info_from_parent, ucxroothub/P_HUB_INFO_FROM_PARENT, ucxroothub/_HUB_INFO_FROM_PARENT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxroothub.h
apiname:
-	HUB_INFO_FROM_PARENT
product: Windows
targetos: Windows
req.typenames: HUB_INFO_FROM_PARENT, *PHUB_INFO_FROM_PARENT
req.product: Windows 10 or later.
---

# _HUB_INFO_FROM_PARENT structure


## -description


Describes information about a hub from its parent device. 


## -syntax


````
typedef struct _HUB_INFO_FROM_PARENT {
  PDEVICE_OBJECT                              IoTarget;
  USB_DEVICE_DESCRIPTOR                       DeviceDescriptor;
  USHORT                                      U1ExitLatency;
  USHORT                                      U2ExitLatency;
  USHORT                                      ExitLatencyOfSlowestLinkForU1;
  UCHAR                                       DepthOfSlowestLinkForU1;
  USHORT                                      ExitLatencyOfSlowestLinkForU2;
  UCHAR                                       DepthOfSlowestLinkForU2;
  USHORT                                      HostInitiatedU1ExitLatency;
  USHORT                                      HostInitiatedU2ExitLatency;
  UCHAR                                       TotalHubDepth;
  USHORT                                      TotalTPPropogationDelay;
  PARENT_HUB_FLAGS                            HubFlags;
  PUSB_DEVICE_CAPABILITY_SUPERSPEEDPLUS_SPEED SublinkSpeedAttr;
  ULONG                                       SublinkSpeedAttrCount;
} HUB_INFO_FROM_PARENT, *P_HUB_INFO_FROM_PARENT;
````


## -struct-fields




### -field IoTarget

A pointer to the WDM device object of the parent that represents the I/O target.


### -field DeviceDescriptor

A <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a> structure that contains the device descriptor.


### -field U1ExitLatency

The time to transition from the U1 state. 


### -field U2ExitLatency

The time to transition from the U2 state. 


### -field ExitLatencyOfSlowestLinkForU1

The exit latency for the slowest link for U1 transition.


### -field DepthOfSlowestLinkForU1

The depth of the hub based on which the latency
        for the slowest link is calculated for a U1 transition.


### -field ExitLatencyOfSlowestLinkForU2

The exit latency for the slowest link for U2 transition.


### -field DepthOfSlowestLinkForU2

The depth of the hub based on which the latency
        for the slowest link is calculated for a U2 transition.


### -field HostInitiatedU1ExitLatency

Host-initiated exit latency to transition from the U1 state. 


### -field HostInitiatedU2ExitLatency

Host-initiated exit latency to transition from the U2 state. 


### -field TotalHubDepth

Total hub depth.


### -field TotalTPPropogationDelay

The total TP propagation delay.


### -field HubFlags

A bitwise-OR of <a href="..\ucxroothub\ns-ucxroothub-_parent_hub_flags.md">PARENT_HUB_FLAGS</a> flags.


### -field SublinkSpeedAttr

A pointer to a <b>USB_DEVICE_CAPABILITY_SUPERSPEEDPLUS_SPEED</b> structure that describes the USB 3.1capability's sublink speed attributes. For structure declaration, see Usbspec.h


### -field SublinkSpeedAttrCount

The count of sublink speed attributes.

