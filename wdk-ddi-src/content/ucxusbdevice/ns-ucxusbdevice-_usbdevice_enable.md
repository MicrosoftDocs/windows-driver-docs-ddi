---
UID: NS:ucxusbdevice._USBDEVICE_ENABLE
title: "_USBDEVICE_ENABLE"
author: windows-driver-content
description: Contains parameters for a request to enable the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_ENABLE callback function.
old-location: buses\_usbdevice_enable.htm
old-project: usbref
ms.assetid: DC54CC46-6ECC-4D1F-9C8C-5579EE759B6F
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBDEVICE_ENABLE, P_USBDEVICE_ENABLE, P_USBDEVICE_ENABLE structure pointer [Buses], USBDEVICE_ENABLE, USBDEVICE_ENABLE structure [Buses], _USBDEVICE_ENABLE, buses._usbdevice_enable, ucxusbdevice/P_USBDEVICE_ENABLE, ucxusbdevice/_USBDEVICE_ENABLE"
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
-	USBDEVICE_ENABLE
product: Windows
targetos: Windows
req.typenames: USBDEVICE_ENABLE, *PUSBDEVICE_ENABLE
req.product: Windows 10 or later.
---

# _USBDEVICE_ENABLE structure


## -description


Contains parameters for a request to enable the specified device. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a> callback function.


## -syntax


````
typedef struct _USBDEVICE_ENABLE {
#ifdef __cplusplus
  USBDEVICE_MGMT_HEADER          Header;
#else 
  USBDEVICE_MGMT_HEADER          ;
#endif 
  UCXENDPOINT                    DefaultEndpoint;
  USBDEVICE_ENABLE_FAILURE_FLAGS FailureFlags;
} USBDEVICE_ENABLE, *P_USBDEVICE_ENABLE;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field DefaultEndpoint

The default endpoint for the USB hub or device to enable transfers for.


### -field FailureFlags

The errors, if any, that occurred when attempting to enable the hub or device for transfers.


## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_disable.md">USBDEVICE_DISABLE</a>



 

 


