---
UID: NS:hwnclx._HWN_CLIENT_REGISTRATION_PACKET
title: "_HWN_CLIENT_REGISTRATION_PACKET"
author: windows-driver-content
description: Hardware Notification client driver registration packet that is passed to the class extension when a client driver is registered. Contains version information and client driver callback functions.
old-location: gpiobtn\_hwn_client_registration_packet.htm
tech.root: gpiobtn
ms.assetid: bf8ac72b-c3d6-4965-a1e9-2408d2fa2196
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PHWN_CLIENT_REGISTRATION_PACKET, HWN_CLIENT_REGISTRATION_PACKET, HWN_CLIENT_REGISTRATION_PACKET structure, _HWN_CLIENT_REGISTRATION_PACKET, gpiobtn._hwn_client_registration_packet, hwnclx/HWN_CLIENT_REGISTRATION_PACKET"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hwnclx.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
-	Hwnclx.h
api_name:
-	HWN_CLIENT_REGISTRATION_PACKET
product:
- Windows
targetos: Windows
req.typenames: HWN_CLIENT_REGISTRATION_PACKET, *PHWN_CLIENT_REGISTRATION_PACKET
---

# _HWN_CLIENT_REGISTRATION_PACKET structure


## -description


Hardware Notification client driver registration packet that is passed to the class
extension when a client driver is registered. Contains version information and
client driver callback functions.


## -syntax


````
typedef struct _HWN_CLIENT_REGISTRATION_PACKET {
  USHORT                                Version;
  USHORT                                Size;
  ULONG                                 DeviceContextSize;
  ULONG                                 Reserved;
  PHWN_CLIENT_INITIALIZE_DEVICE         ClientInitializeDevice;
  PHWN_CLIENT_UNINITIALIZE_DEVICE       ClientUnInitializeDevice;
  PHWN_CLIENT_QUERY_DEVICE_INFORMATION  ClientQueryDeviceInformation;
  PHWN_CLIENT_START_DEVICE              ClientStartDevice;
  PHWN_CLIENT_STOP_DEVICE               ClientStopDevice;
  PHWN_CLIENT_SET_STATE                 ClientSetHwNState;
  PHWN_CLIENT_GET_STATE                 ClientGetHwNState;
} HWN_CLIENT_REGISTRATION_PACKET, HWN_CLIENT_REGISTRATION_PACKET;
````


## -struct-fields




### -field Version

Version of this structure.


### -field Size

Size of this structure.


### -field DeviceContextSize

Size of the driver-defined context structure.


### -field Reserved

Reseved.


### -field ClientInitializeDevice

A pointer to the client driver's implementation of the <a href="..\hwnclx\nc-hwnclx-hwn_client_initialize_device.md">HWN_CLIENT_INITIALIZE_DEVICE</a> callback function.


### -field ClientUnInitializeDevice

A pointer to the client driver's implementation of the <a href="..\hwnclx\nc-hwnclx-hwn_client_uninitialize_device.md">HWN_CLIENT_UNINITIALIZE_DEVICE</a> callback function.


### -field ClientQueryDeviceInformation

A pointer to the client driver's implementation of the  <a href="..\hwnclx\nc-hwnclx-hwn_client_query_device_information.md">HWN_CLIENT_QUERY_DEVICE_INFORMATION</a> callback function.


### -field ClientStartDevice

A pointer to the client driver's implementation of the  <a href="..\hwnclx\nc-hwnclx-hwn_client_start_device.md">HWN_CLIENT_START_DEVICE</a> callback function.


### -field ClientStopDevice

A pointer to the client driver's implementation of the  <a href="..\hwnclx\nc-hwnclx-hwn_client_stop_device.md">HWN_CLIENT_STOP_DEVICE</a> callback function.


### -field ClientSetHwNState

A pointer to the client driver's implementation of the  <a href="..\hwnclx\nc-hwnclx-hwn_client_set_state.md">HWN_CLIENT_SET_STATE</a> callback function.


### -field ClientGetHwNState

A pointer to the client driver's implementation of the  <a href="..\hwnclx\nc-hwnclx-hwn_client_get_state.md">HWN_CLIENT_GET_STATE</a> callback function.


## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a>



<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>



 

 


