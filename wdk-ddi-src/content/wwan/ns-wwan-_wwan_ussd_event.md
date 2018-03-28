---
UID: NS:wwan._WWAN_USSD_EVENT
title: "_WWAN_USSD_EVENT"
author: windows-driver-content
description: The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) event.
old-location: netvista\wwan_ussd_event.htm
old-project: netvista
ms.assetid: 5E90FB65-AF23-47C0-B0E9-2B6EF353D095
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_USSD_EVENT, PWWAN_USSD_EVENT, PWWAN_USSD_EVENT structure pointer [Network Drivers Starting with Windows Vista], WWAN_USSD_EVENT, WWAN_USSD_EVENT structure [Network Drivers Starting with Windows Vista], _WWAN_USSD_EVENT, netvista.wwan_ussd_event, wwan/PWWAN_USSD_EVENT, wwan/WWAN_USSD_EVENT"
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
-	WWAN_USSD_EVENT
product: Windows
targetos: Windows
req.typenames: WWAN_USSD_EVENT, *PWWAN_USSD_EVENT
req.product: Windows 10 or later.
---

# _WWAN_USSD_EVENT structure


## -description


The WWAN_USSD_REQUEST structure describes an Unstructured Supplementary Service Data (USSD) event.


## -struct-fields




### -field EventType

The type of USSD event.


### -field SessionState

The USSD string is the first message of a USSD session.


### -field UssdString

The USSD string that accompanies the event.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464137">WWAN_USSD_EVENT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464140">WWAN_USSD_SESSION_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464141">WWAN_USSD_STRING</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_USSD_EVENT structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

