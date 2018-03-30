---
UID: NS:wwan._WWAN_AUTH_RESPONSE
title: "_WWAN_AUTH_RESPONSE"
author: windows-driver-content
description: The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.
old-location: netvista\wwan_auth_response.htm
old-project: netvista
ms.assetid: CD0B90A1-032D-4F09-827F-E80607AE4EA7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_AUTH_RESPONSE, PWWAN_AUTH_RESPONSE, PWWAN_AUTH_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_RESPONSE, WWAN_AUTH_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_RESPONSE, netvista.wwan_auth_response, wwan/PWWAN_AUTH_RESPONSE, wwan/WWAN_AUTH_RESPONSE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	wwan.h
api_name:
-	WWAN_AUTH_RESPONSE
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_RESPONSE, *PWWAN_AUTH_RESPONSE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_RESPONSE structure


## -description


The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.


## -struct-fields




### -field AuthMethod

The authentication challenge method used.


### -field u

The container union for the different authentication challenge methods.



#### AuthSim

The esponse from the SIM authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthSim</i>, use this member.



#### AuthAka

The response from the AKA authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthAka, </i>use this member.



#### AuthAkap

The response from the AKA' authentication method.  If <b>AuthMethod</b> is set to <i>WwanAuthAkap, </i>use this member.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439834">NDIS_WWAN_AUTH_RESPONSE</a> structure uses this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439834">NDIS_WWAN_AUTH_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh440303">WWAN_AUTH_AKAP_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464126">WWAN_AUTH_AKA_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464128">WWAN_AUTH_METHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464131">WWAN_AUTH_SIM_RESPONSE</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_RESPONSE structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
