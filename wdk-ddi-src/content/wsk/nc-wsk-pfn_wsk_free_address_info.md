---
UID: NC:wsk.PFN_WSK_FREE_ADDRESS_INFO
title: PFN_WSK_FREE_ADDRESS_INFO (wsk.h)
description: The WskFreeAddressInfo function frees address information that the WskGetAddressInfo function has dynamically allocated.
old-location: netvista\wskfreeaddressinfo.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["PFN_WSK_FREE_ADDRESS_INFO callback function"]
ms.keywords: PFN_WSK_FREE_ADDRESS_INFO, PFN_WSK_FREE_ADDRESS_INFO callback, WskFreeAddressInfo, WskFreeAddressInfo callback function [Network Drivers Starting with Windows Vista], netvista.wskfreeaddressinfo, wsk/WskFreeAddressInfo, wskref_dff141b0-8164-439d-9ad7-69a4d2207f31.xml
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
req.typenames: 
f1_keywords:
 - PFN_WSK_FREE_ADDRESS_INFO
 - wsk/PFN_WSK_FREE_ADDRESS_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - wsk.h
api_name:
 - PFN_WSK_FREE_ADDRESS_INFO
---

# PFN_WSK_FREE_ADDRESS_INFO callback function


## -description

The 
  <b>WskFreeAddressInfo</b> function frees address information that the 
  <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_address_info">WskGetAddressInfo</a> function has dynamically
  allocated.

## -parameters

### -param Client 

[in]
[in] A pointer to a 
     <a href="/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">
     WskCaptureProviderNPI</a> function.

### -param AddrInfo 

[in]
[in] A pointer to a linked list of one or more <a href="/windows/win32/api/ws2def/ns-ws2def-addrinfoexw">ADDRINFOEXW</a> structures that contain response
     information about the host. This pointer was returned through the 
     <i>Result</i> parameter of the 
     <a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_address_info">WskGetAddressInfo</a> function.
     

The <a href="/windows/win32/api/ws2def/ns-ws2def-addrinfoexw">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header file. It is identical to the 
     <a href="/windows/win32/api/ws2def/ns-ws2def-addrinfoexw">addrinfoex</a> structure.

<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/network/wsk-client">WSK_CLIENT</a>



<a href="/windows-hardware/drivers/ddi/wsk/nf-wsk-wskcaptureprovidernpi">WskCaptureProviderNPI</a>



<a href="/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_get_address_info">WskGetAddressInfo</a>

