---
UID: NS:ucxroothub._ROOTHUB_INFO
title: _ROOTHUB_INFO
author: windows-driver-content
description: Provides information about a USB root hub. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_INFO callback function.
old-location: buses\_roothub_info.htm
old-project: usbref
ms.assetid: 634398E9-7AAA-424C-8C81-287F70CE3578
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _ROOTHUB_INFO, *PROOTHUB_INFO, ROOTHUB_INFO
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
req.alt-api: ROOTHUB_INFO
req.alt-loc: ucxroothub.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PROOTHUB_INFO, ROOTHUB_INFO
req.product: Windows 10 or later.
---

# _ROOTHUB_INFO structure



## -description
Provides information about a USB root hub. This structure is passed by UCX in the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_info.md">EVT_UCX_ROOTHUB_GET_INFO</a> callback function.



## -syntax

````
typedef struct _ROOTHUB_INFO {
  ULONG           Size;
  CONTROLLER_TYPE ControllerType;
  USHORT          NumberOf20Ports;
  USHORT          NumberOf30Ports;
  USHORT          MaxU1ExitLatency;
  USHORT          MaxU2ExitLatency;
} ROOTHUB_INFO, *P_ROOTHUB_INFO;
````


## -struct-fields

### -field Size

The size in bytes of this structure.


### -field ControllerType

A <a href="..\ucxroothub\ne-ucxroothub-_controller_type.md">CONTROLLER_TYPE</a> value that identifies the type of eXtensible Host Controller Interface (xHCI) which has the root hub.


### -field NumberOf20Ports

The number of USB 2.0 ports connected to the root hub.


### -field NumberOf30Ports

The number of USB 3.0 ports connected to the root hub.


### -field MaxU1ExitLatency

The exit latency for the slowest link for U1 transition.


### -field MaxU2ExitLatency

The exit latency for the slowest link for U2 transition.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_get_info.md">EVT_UCX_ROOTHUB_GET_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20ROOTHUB_INFO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

