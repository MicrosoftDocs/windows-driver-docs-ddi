---
UID: NS:wsk._WSK_PROVIDER_NPI
title: "_WSK_PROVIDER_NPI"
author: windows-driver-content
description: The WSK_PROVIDER_NPI structure identifies a provider Network Programming Interface (NPI) implemented by the WSK subsystem.
old-location: netvista\wsk_provider_npi.htm
old-project: netvista
ms.assetid: 471689f4-d1f6-4785-82df-313fe2ca627a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wsk_provider_npi, wsk/WSK_PROVIDER_NPI, PWSK_PROVIDER_NPI, *PWSK_PROVIDER_NPI, wskref_cbed200a-9ed1-4cd6-b6be-220799cbae1c.xml, WSK_PROVIDER_NPI, WSK_PROVIDER_NPI structure [Network Drivers Starting with Windows Vista], _WSK_PROVIDER_NPI, wsk/PWSK_PROVIDER_NPI, PWSK_PROVIDER_NPI structure pointer [Network Drivers Starting with Windows Vista]
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wsk.h
apiname:
-	WSK_PROVIDER_NPI
product: Windows
targetos: Windows
req.typenames: "*PWSK_PROVIDER_NPI, WSK_PROVIDER_NPI"
req.product: Windows 10 or later.
---

# _WSK_PROVIDER_NPI structure


## -description


The WSK_PROVIDER_NPI structure identifies a provider 
  <mshelp:link keywords="netvista.network_programming_interface" tabindex="0">Network Programming Interface
  (NPI)</mshelp:link> implemented by the WSK subsystem.


## -syntax


````
typedef struct _WSK_PROVIDER_NPI {
  PWSK_CLIENT                 Client;
  const WSK_PROVIDER_DISPATCH *Dispatch;
} WSK_PROVIDER_NPI, *PWSK_PROVIDER_NPI;
````


## -struct-fields




#### - Client

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a> structure that was returned through
     the 
     <i>WskProviderNpi</i> parameter of the 
     <mshelp:link keywords="netvista.wskcaptureprovidernpi" tabindex="0"><b>
     WskCaptureProviderNPI</b></mshelp:link> function.


#### - Dispatch

A pointer to a constant 
     <mshelp:link keywords="netvista.wsk_provider_dispatch" tabindex="0"><b>
     WSK_PROVIDER_DISPATCH</b></mshelp:link> structure.


## -see-also

<a href="..\wsk\ns-wsk-_wsk_provider_dispatch.md">WSK_PROVIDER_DISPATCH</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff571155">WSK_CLIENT</a>

<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_PROVIDER_NPI structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

