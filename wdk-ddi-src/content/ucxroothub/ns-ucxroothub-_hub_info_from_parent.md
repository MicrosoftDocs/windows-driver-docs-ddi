---
UID: NS:ucxroothub._HUB_INFO_FROM_PARENT
title: "_HUB_INFO_FROM_PARENT"
author: windows-driver-content
description: Describes information about a hub from its parent device.
old-location: buses\_hub_info_from_parent.htm
old-project: usbref
ms.assetid: 6259CC70-A54B-4A44-B38B-D24C296C8EA0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: P_HUB_INFO_FROM_PARENT, _HUB_INFO_FROM_PARENT, *PHUB_INFO_FROM_PARENT, buses._hub_info_from_parent, ucxroothub/P_HUB_INFO_FROM_PARENT, HUB_INFO_FROM_PARENT structure [Buses], HUB_INFO_FROM_PARENT, P_HUB_INFO_FROM_PARENT structure pointer [Buses], ucxroothub/_HUB_INFO_FROM_PARENT
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




#### - IoTarget

A pointer to the WDM device object of the parent that represents the I/O target.


#### - DeviceDescriptor

A <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a> structure that contains the device descriptor.


#### - U1ExitLatency

The time to transition from the U1 state. 


#### - U2ExitLatency

The time to transition from the U2 state. 


#### - ExitLatencyOfSlowestLinkForU1

The exit latency for the slowest link for U1 transition.


#### - DepthOfSlowestLinkForU1

The depth of the hub based on which the latency
        for the slowest link is calculated for a U1 transition.


#### - ExitLatencyOfSlowestLinkForU2

The exit latency for the slowest link for U2 transition.


#### - DepthOfSlowestLinkForU2

The depth of the hub based on which the latency
        for the slowest link is calculated for a U2 transition.


#### - HostInitiatedU1ExitLatency

Host-initiated exit latency to transition from the U1 state. 


#### - HostInitiatedU2ExitLatency

Host-initiated exit latency to transition from the U2 state. 


#### - TotalHubDepth

Total hub depth.


#### - TotalTPPropogationDelay

The total TP propagation delay.


#### - HubFlags

A bitwise-OR of <a href="..\ucxroothub\ns-ucxroothub-_parent_hub_flags.md">PARENT_HUB_FLAGS</a> flags.


#### - SublinkSpeedAttr

A pointer to a <b>USB_DEVICE_CAPABILITY_SUPERSPEEDPLUS_SPEED</b> structure that describes the USB 3.1capability's sublink speed attributes. For structure declaration, see Usbspec.h


#### - SublinkSpeedAttrCount

The count of sublink speed attributes.

