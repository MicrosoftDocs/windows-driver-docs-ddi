---
UID: NS:ucxusbdevice._USBDEVICE_STARTIO
title: "_USBDEVICE_STARTIO"
author: windows-driver-content
description: Contains a handle for the Universal Serial Bus (USB) hub or device on which to start data transfer.
old-location: buses\_usbdevice_startio.htm
old-project: usbref
ms.assetid: 6FE2962A-90A3-44C6-9A2E-CCEBCE8C1417
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBDEVICE_STARTIO, P_USBDEVICE_STARTIO, P_USBDEVICE_STARTIO structure pointer [Buses], USBDEVICE_STARTIO, USBDEVICE_STARTIO structure [Buses], _USBDEVICE_STARTIO, buses._usbdevice_startio, ucxusbdevice/P_USBDEVICE_STARTIO, ucxusbdevice/_USBDEVICE_STARTIO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ucxusbdevice.h
api_name:
-	USBDEVICE_STARTIO
product: Windows
targetos: Windows
req.typenames: USBDEVICE_STARTIO, *PUSBDEVICE_STARTIO
req.product: Windows 10 or later.
---

# _USBDEVICE_STARTIO structure


## -description


Contains a handle for the Universal Serial Bus (USB) hub or device on which to start data transfer. 


## -syntax


````
typedef struct _USBDEVICE_STARTIO {
#if _cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} USBDEVICE_STARTIO, *P_USBDEVICE_STARTIO;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## -see-also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_abortio.md">USBDEVICE_ABORTIO</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_purgeio.md">USBDEVICE_PURGEIO</a>



 

 


