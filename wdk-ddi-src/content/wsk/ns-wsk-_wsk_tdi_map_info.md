---
UID: NS:wsk._WSK_TDI_MAP_INFO
title: _WSK_TDI_MAP_INFO (wsk.h)
description: The WSK_TDI_MAP_INFO structure specifies a list that contains mappings of a combination of an address family, a socket type, and a protocol to the device name of a TDI transport.
old-location: netvista\wsk_tdi_map_info.htm
tech.root: netvista
ms.assetid: b0b4fab4-1a3c-4075-8881-f2aa38fba15e
ms.date: 05/02/2018
keywords: ["_WSK_TDI_MAP_INFO structure"]
ms.keywords: "*PWSK_TDI_MAP_INFO, PWSK_TDI_MAP_INFO, PWSK_TDI_MAP_INFO structure pointer [Network Drivers Starting with Windows Vista], WSK_TDI_MAP_INFO, WSK_TDI_MAP_INFO structure [Network Drivers Starting with Windows Vista], _WSK_TDI_MAP_INFO, netvista.wsk_tdi_map_info, wsk/PWSK_TDI_MAP_INFO, wsk/WSK_TDI_MAP_INFO, wskref_27c8b9f2-49b9-4358-aeac-be81e5aeb297.xml"
f1_keywords:
 - "wsk/WSK_TDI_MAP_INFO"
 - "WSK_TDI_MAP_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wsk.h
api_name:
- WSK_TDI_MAP_INFO
targetos: Windows
req.typenames: WSK_TDI_MAP_INFO, *PWSK_TDI_MAP_INFO
---

# _WSK_TDI_MAP_INFO structure


## -description


The WSK_TDI_MAP_INFO structure specifies a list that contains mappings of a combination of an address
  family, a socket type, and a protocol to the device name of a 
  <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565094(v=vs.85)">TDI</a> transport.


## -struct-fields




### -field ElementCount

The number of structures contained in the array pointed to by the 
     <b>Map</b> member.


### -field Map

A pointer to an array of 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_tdi_map">WSK_TDI_MAP</a> structures. Each WSK_TDI_MAP
     structure in the array contains a mapping of a particular address family, socket type, and protocol to
     the device name of a 
     <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565094(v=vs.85)">TDI</a> transport.


## -remarks



A WSK application passes a pointer to a WSK_TDI_MAP_INFO structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_client">WskControlClient</a> function when specifying    
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wsk-tdi-devicename-mapping">WSK_TDI_DEVICENAME_MAPPING</a> for
    the control code.

If a WSK application uses the WSK_TDI_DEVICENAME_MAPPING client control operation to map combinations
    of address family, socket type, and protocol to device names of 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff565094(v=vs.85)">TDI</a> transports, it must do so before it creates any
    sockets.

For more information about using TDI transports, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-tdi-transports">Using TDI Transports</a>.

<div class="alert"><b>Note</b>  TDI will not be supported in Microsoft Windows versions after Windows Vista. Use 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">Windows Filtering
    Platform</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">Winsock Kernel</a> instead.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_tdi_map">WSK_TDI_MAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_control_client">WskControlClient</a>
 

 

