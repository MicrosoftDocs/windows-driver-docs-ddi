---
UID: NS:wwan._WWAN_SERVICE_ACTIVATION_STATUS
title: "_WWAN_SERVICE_ACTIVATION_STATUS"
author: windows-driver-content
description: The WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the MB device.
old-location: netvista\wwan_service_activation_status.htm
old-project: netvista
ms.assetid: 1bd81e55-6438-4bff-ab50-3de3457d2e99
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_SERVICE_ACTIVATION_STATUS, PWWAN_SERVICE_ACTIVATION_STATUS, PWWAN_SERVICE_ACTIVATION_STATUS structure pointer [Network Drivers Starting with Windows Vista], WWAN_SERVICE_ACTIVATION_STATUS, WWAN_SERVICE_ACTIVATION_STATUS structure [Network Drivers Starting with Windows Vista], WwanRef_b9086c08-c7df-46f1-8ce2-c056dd667eac.xml, _WWAN_SERVICE_ACTIVATION_STATUS, netvista.wwan_service_activation_status, wwan/PWWAN_SERVICE_ACTIVATION_STATUS, wwan/WWAN_SERVICE_ACTIVATION_STATUS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	WWAN_SERVICE_ACTIVATION_STATUS
product: Windows
targetos: Windows
req.typenames: WWAN_SERVICE_ACTIVATION_STATUS, *PWWAN_SERVICE_ACTIVATION_STATUS
req.product: Windows 10 or later.
---

# _WWAN_SERVICE_ACTIVATION_STATUS structure


## -description


The WWAN_SERVICE_ACTIVATION_STATUS structure represents the status of service activation on the MB
  device.


## -struct-fields




### -field uNwError

A network-specific error, if any, that is returned by the network provider. Miniport drivers
     should populate this member only if 
     <b>uStatus</b> does not equal WWAN_STATUS_SUCCESS.


### -field uVendorSpecificBufferSize

The size, in bytes, of the vendor-specific buffer that follows the structure instance in
     memory.


## -see-also




<a href="https://msdn.microsoft.com/669ef35f-0e59-4ec3-b6cc-5cb2156b51a2">
   NDIS_WWAN_SERVICE_ACTIVATION_STATUS</a>
 

 

