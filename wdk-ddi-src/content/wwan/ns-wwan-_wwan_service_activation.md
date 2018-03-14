---
UID: NS:wwan._WWAN_SERVICE_ACTIVATION
title: "_WWAN_SERVICE_ACTIVATION"
author: windows-driver-content
description: The WWAN_SERVICE_ACTIVATION structure represents a vendor-specific buffer to be associated with service activation.
old-location: netvista\wwan_service_activation.htm
old-project: netvista
ms.assetid: 1893a929-c9e6-446e-a840-3825f4992c18
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_SERVICE_ACTIVATION, PWWAN_SERVICE_ACTIVATION, PWWAN_SERVICE_ACTIVATION structure pointer [Network Drivers Starting with Windows Vista], WWAN_SERVICE_ACTIVATION, WWAN_SERVICE_ACTIVATION structure [Network Drivers Starting with Windows Vista], WwanRef_90dec032-ce8e-4b19-a4d8-e9a7a22d681e.xml, _WWAN_SERVICE_ACTIVATION, netvista.wwan_service_activation, wwan/PWWAN_SERVICE_ACTIVATION, wwan/WWAN_SERVICE_ACTIVATION"
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
-	WWAN_SERVICE_ACTIVATION
product: Windows
targetos: Windows
req.typenames: WWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION
req.product: Windows 10 or later.
---

# _WWAN_SERVICE_ACTIVATION structure


## -description


The WWAN_SERVICE_ACTIVATION structure represents a vendor-specific buffer to be associated with
  service activation.


## -syntax


````
typedef struct _WWAN_SERVICE_ACTIVATION {
  ULONG uVendorSpecificBufferSize;
} WWAN_SERVICE_ACTIVATION, *PWWAN_SERVICE_ACTIVATION;
````


## -struct-fields




### -field uVendorSpecificBufferSize

The size, in bytes, of the vendor-specific buffer that follows the structure instance in
     memory.


## -see-also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_service_activation.md">NDIS_WWAN_SERVICE_ACTIVATION</a>



 

 


