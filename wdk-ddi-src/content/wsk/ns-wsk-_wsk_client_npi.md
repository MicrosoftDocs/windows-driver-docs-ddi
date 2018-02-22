---
UID: NS:wsk._WSK_CLIENT_NPI
title: "_WSK_CLIENT_NPI"
author: windows-driver-content
description: The WSK_CLIENT_NPI structure identifies a Network Programming Interface (NPI) implemented by a WSK client.
old-location: netvista\wsk_client_npi.htm
old-project: netvista
ms.assetid: 2f50b228-5565-436f-8c68-8885b8916001
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PWSK_CLIENT_NPI, _WSK_CLIENT_NPI, WSK_CLIENT_NPI, netvista.wsk_client_npi, wskref_e498e50c-695d-4f5c-a1db-0f87f4313d4a.xml, WSK_CLIENT_NPI structure [Network Drivers Starting with Windows Vista], *PWSK_CLIENT_NPI, wsk/WSK_CLIENT_NPI, wsk/PWSK_CLIENT_NPI, PWSK_CLIENT_NPI structure pointer [Network Drivers Starting with Windows Vista]
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
-	WSK_CLIENT_NPI
product: Windows
targetos: Windows
req.typenames: WSK_CLIENT_NPI, *PWSK_CLIENT_NPI
req.product: Windows 10 or later.
---

# _WSK_CLIENT_NPI structure


## -description


The WSK_CLIENT_NPI structure identifies a 
  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/network-programming-interface">Network Programming Interface
  (NPI)</a> implemented by a WSK client.


## -syntax


````
typedef struct _WSK_CLIENT_NPI {
  PVOID                     ClientContext;
  const WSK_CLIENT_DISPATCH *Dispatch;
} WSK_CLIENT_NPI, *PWSK_CLIENT_NPI;
````


## -struct-fields




### -field ClientContext

A pointer to the context for the WSK application's binding to the WSK subsystem.


### -field Dispatch

A pointer to a constant 
     <a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a> structure.


## -remarks



For more information about attaching a WSK application to the WSK subsystem, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/registering-a-winsock-kernel-application">Registering a Winsock Kernel
    Application</a>.




## -see-also

<a href="..\wsk\ns-wsk-_wsk_client_dispatch.md">WSK_CLIENT_DISPATCH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_CLIENT_NPI structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

