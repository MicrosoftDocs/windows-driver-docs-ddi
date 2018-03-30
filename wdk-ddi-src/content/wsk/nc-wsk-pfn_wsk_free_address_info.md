---
UID: NC:wsk.PFN_WSK_FREE_ADDRESS_INFO
title: PFN_WSK_FREE_ADDRESS_INFO
author: windows-driver-content
description: The WskFreeAddressInfo function frees address information that the WskGetAddressInfo function has dynamically allocated.
old-location: netvista\wskfreeaddressinfo.htm
old-project: netvista
ms.assetid: 552b4024-03d3-4e9b-b149-cf584c7e7259
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PFN_WSK_FREE_ADDRESS_INFO, WskFreeAddressInfo, WskFreeAddressInfo callback function [Network Drivers Starting with Windows Vista], netvista.wskfreeaddressinfo, wsk/WskFreeAddressInfo, wskref_dff141b0-8164-439d-9ad7-69a4d2207f31.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wsk.h
api_name:
-	WskFreeAddressInfo
product: Windows
targetos: Windows
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_FREE_ADDRESS_INFO callback


## -description


The 
  <b>WskFreeAddressInfo</b> function frees address information that the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff571132">WskGetAddressInfo</a> function has dynamically
  allocated.


## -parameters




### -param Client [in]

[in] A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <a href="https://msdn.microsoft.com/b5c6667e-33b4-4482-8817-c01d9d314c3a">
     WskCaptureProviderNPI</a> function.


### -param AddrInfo [in]

[in] A pointer to a linked list of one or more <a href="https://msdn.microsoft.com/1077e03d-a1a4-45ab-a5d2-29a67e03f5df">ADDRINFOEXW</a> structures that contain response
     information about the host. This pointer was returned through the 
     <i>Result</i> parameter of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571132">WskGetAddressInfo</a> function.
     

The <a href="https://msdn.microsoft.com/1077e03d-a1a4-45ab-a5d2-29a67e03f5df">ADDRINFOEXW</a> structure is defined in the 
     Ws2def.h header file. It is identical to the 
     <a href="https://msdn.microsoft.com/1077e03d-a1a4-45ab-a5d2-29a67e03f5df">addrinfoex</a> structure.

<div class="alert"><b>Important</b>  The 
     Ws2def.h header file is automatically included in 
     Wsk.h. Do not use 
     Ws2def.h directly.</div>
<div> </div>

## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571122">WskCaptureProviderNPI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571132">WskGetAddressInfo</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_FREE_ADDRESS_INFO callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
