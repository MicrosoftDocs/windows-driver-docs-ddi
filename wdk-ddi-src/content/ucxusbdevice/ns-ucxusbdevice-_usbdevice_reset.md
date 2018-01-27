---
UID: NS:ucxusbdevice._USBDEVICE_RESET
title: _USBDEVICE_RESET
author: windows-driver-content
description: Contains parameters for a request to reset the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_RESET callback function.
old-location: buses\_usbdevice_reset.htm
old-project: usbref
ms.assetid: 4C07239D-89AE-4A9F-B7EB-CFFE6D47F10B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses._usbdevice_reset, ucxusbdevice/P_USBDEVICE_RESET, _USBDEVICE_RESET, P_USBDEVICE_RESET, *PUSBDEVICE_RESET, ucxusbdevice/_USBDEVICE_RESET, USBDEVICE_RESET, USBDEVICE_RESET structure [Buses], P_USBDEVICE_RESET structure pointer [Buses]
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ucxusbdevice.h
apiname: 
-	USBDEVICE_RESET
product: Windows
targetos: Windows
req.typenames: *PUSBDEVICE_RESET, USBDEVICE_RESET
req.product: Windows 10 or later.
---

# _USBDEVICE_RESET structure


## -description


Contains parameters for a request to reset the specified device.  This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_reset.md">EVT_UCX_USBDEVICE_RESET</a> callback function.


## -syntax


````
typedef struct _USBDEVICE_RESET {
#ifdef __cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
  UCXENDPOINT           DefaultEndpoint;
  ULONG                 EndpointsToDisableCount;
  UCXENDPOINT           *EndpointsToDisable;
} USBDEVICE_RESET, *P_USBDEVICE_RESET;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field DefaultEndpoint

The default endpoint for the USB hub or device.


### -field EndpointsToDisableCount

The number of endpoints to disable. 


### -field EndpointsToDisable

A pointer to an array of handles to endpoints to disable. 


## -see-also

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_reset.md">EVT_UCX_USBDEVICE_RESET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_RESET structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

