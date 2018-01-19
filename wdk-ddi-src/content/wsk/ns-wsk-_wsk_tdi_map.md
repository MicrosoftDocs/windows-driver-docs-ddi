---
UID: NS:wsk._WSK_TDI_MAP
title: _WSK_TDI_MAP
author: windows-driver-content
description: The WSK_TDI_MAP structure specifies a mapping between a particular address family, socket type, and protocol to the device name of a TDI transport.
old-location: netvista\wsk_tdi_map.htm
old-project: netvista
ms.assetid: 4c1407e9-2e4d-41cc-8d50-017c8c2bf20f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WSK_TDI_MAP, *PWSK_TDI_MAP, WSK_TDI_MAP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_TDI_MAP
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWSK_TDI_MAP, WSK_TDI_MAP
req.product: Windows 10 or later.
---

# _WSK_TDI_MAP structure



## -description
The WSK_TDI_MAP structure specifies a mapping between a particular address family, socket type, and
  protocol to the device name of a 
  <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.



## -syntax

````
typedef struct _WSK_TDI_MAP {
  USHORT         SocketType;
  ADDRESS_FAMILY AddressFamily;
  ULONG          Protocol;
  PCWSTR         TdiDeviceName;
} WSK_TDI_MAP, *PWSK_TDI_MAP;
````


## -struct-fields

### -field SocketType

The socket type. This member can contain any of the SOCK_<i>XXX</i> values that are defined in the 
     Ws2def.h header file.


### -field AddressFamily

The address family. This member can contain any of the AF_<i>XXX</i> values that are defined in the 
     Ws2def.h header file.


### -field Protocol

The transport protocol.


### -field TdiDeviceName

A pointer to a null-terminated wide character string that contains the device name for the 
     <a href="https://msdn.microsoft.com/7c432f72-4de6-40a8-884c-26e13926e550">TDI</a> transport that supports the combination of
     address family, socket type, and protocol specified by the 
     <b>AddressFamily</b>, 
     <b>SocketType</b>, and 
     <b>Protocol</b> members.


## -remarks
The 
    <b>Map</b> member of the 
    <a href="..\wsk\ns-wsk-_wsk_tdi_map_info.md">WSK_TDI_MAP_INFO</a> structure points to an
    array of WSK_TDI_MAP structures, each of which contains a mapping between a particular address family,
    socket type, and protocol to the device name of a 
    <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.

For more information about using TDI transports, see 
    <a href="https://msdn.microsoft.com/58fb5e62-e15d-4f15-8eb3-3e302ea08c4f">Using TDI Transports</a>.


## -see-also
<dl>
<dt>
<a href="..\wsk\ns-wsk-_wsk_tdi_map_info.md">WSK_TDI_MAP_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_TDI_MAP structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

