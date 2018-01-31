---
UID: NF:wsk.WskReleaseProviderNPI
title: WskReleaseProviderNPI function
author: windows-driver-content
description: The WskReleaseProviderNPI function releases a Network Programming Interface (NPI) that was captured with WskCaptureProviderNPI.
old-location: netvista\wskreleaseprovidernpi.htm
old-project: netvista
ms.assetid: 6b0b995a-61db-4bdf-a896-74d91bd192e7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wsk/WskReleaseProviderNPI, wskref_1ed7116e-c3a0-41dd-9d19-aa2f44eae257.xml, WskReleaseProviderNPI function [Network Drivers Starting with Windows Vista], WskReleaseProviderNPI, netvista.wskreleaseprovidernpi
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
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
req.lib: Netio.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Netio.lib
-	Netio.dll
apiname:
-	WskReleaseProviderNPI
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# WskReleaseProviderNPI function


## -description


The 
  <b>WskReleaseProviderNPI</b> function releases a 
  <mshelp:link keywords="netvista.network_programming_interface" tabindex="0">Network Programming Interface
  (NPI)</mshelp:link> that was captured with 
  <a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>.


## -syntax


````
VOID WskReleaseProviderNPI(
  _In_ PWSK_REGISTRATION WskRegistration
);
````


## -parameters




#### - WskRegistration [in]

A pointer to the memory location initialized by 
     <a href="..\wsk\nf-wsk-wskregister.md">WskRegister</a> that identifies a WSK
     application's registration instance.


## -returns


None



## -remarks


For each call to
    <b>WskCaptureProviderNPI</b> that returns a success code, there must be exactly one corresponding 
    <b>WskReleaseProviderNPI</b> call that uses
    the same 
    <i>WskRegistration</i> parameter that was passed to 
    <b>WskCaptureProviderNPI</b>.



## -see-also

<a href="..\wsk\ns-wsk-_wsk_registration.md">WSK_REGISTRATION</a>

<a href="..\wsk\nf-wsk-wskcaptureprovidernpi.md">WskCaptureProviderNPI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WskReleaseProviderNPI function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

