---
UID: NS:wsk._WSK_TDI_MAP_INFO
title: "_WSK_TDI_MAP_INFO"
author: windows-driver-content
description: The WSK_TDI_MAP_INFO structure specifies a list that contains mappings of a combination of an address family, a socket type, and a protocol to the device name of a TDI transport.
old-location: netvista\wsk_tdi_map_info.htm
old-project: netvista
ms.assetid: b0b4fab4-1a3c-4075-8881-f2aa38fba15e
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWSK_TDI_MAP_INFO, PWSK_TDI_MAP_INFO, PWSK_TDI_MAP_INFO structure pointer [Network Drivers Starting with Windows Vista], WSK_TDI_MAP_INFO, WSK_TDI_MAP_INFO structure [Network Drivers Starting with Windows Vista], _WSK_TDI_MAP_INFO, netvista.wsk_tdi_map_info, wsk/PWSK_TDI_MAP_INFO, wsk/WSK_TDI_MAP_INFO, wskref_27c8b9f2-49b9-4358-aeac-be81e5aeb297.xml"
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
-	wsk.h
api_name:
-	WSK_TDI_MAP_INFO
product: Windows
targetos: Windows
req.typenames: WSK_TDI_MAP_INFO, *PWSK_TDI_MAP_INFO
---

# _WSK_TDI_MAP_INFO structure


## -description


The WSK_TDI_MAP_INFO structure specifies a list that contains mappings of a combination of an address
  family, a socket type, and a protocol to the device name of a 
  <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.


## -struct-fields




### -field ElementCount

The number of structures contained in the array pointed to by the 
     <b>Map</b> member.


### -field Map

A pointer to an array of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571191">WSK_TDI_MAP</a> structures. Each WSK_TDI_MAP
     structure in the array contains a mapping of a particular address family, socket type, and protocol to
     the device name of a 
     <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transport.


## -remarks



A WSK application passes a pointer to a WSK_TDI_MAP_INFO structure to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a> function when specifying
    
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571190">WSK_TDI_DEVICENAME_MAPPING</a> for
    the control code.

If a WSK application uses the WSK_TDI_DEVICENAME_MAPPING client control operation to map combinations
    of address family, socket type, and protocol to device names of 
    <a href="https://msdn.microsoft.com/3878053c-388a-4bbc-a30e-feb16eda2f99">TDI</a> transports, it must do so before it creates any
    sockets.

For more information about using TDI transports, see 
    <a href="https://msdn.microsoft.com/58fb5e62-e15d-4f15-8eb3-3e302ea08c4f">Using TDI Transports</a>.

<div class="alert"><b>Note</b>  TDI will not be supported in Microsoft Windows versions after Windows Vista. Use 
    <a href="https://msdn.microsoft.com/b9d88e59-3c4b-4804-8dd9-02c275927a1e">Windows Filtering
    Platform</a> or 
    <a href="https://msdn.microsoft.com/90264a3d-f002-4205-8e15-9060644117a3">Winsock Kernel</a> instead.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571191">WSK_TDI_MAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571126">WskControlClient</a>
 

 

