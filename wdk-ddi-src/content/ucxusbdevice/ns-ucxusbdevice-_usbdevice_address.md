---
UID: NS:ucxusbdevice._USBDEVICE_ADDRESS
title: "_USBDEVICE_ADDRESS"
author: windows-driver-content
description: Contains parameters for a request to transition the specified device to the Addressed state. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_ADDRESS callback function.
old-location: buses\_usbdevice_address.htm
old-project: UsbRef
ms.assetid: 2CD37F1E-B96A-4D18-A756-2B9E3CB8613B
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: USBDEVICE_ADDRESS structure [Buses], P_USBDEVICE_ADDRESS structure pointer [Buses], *PUSBDEVICE_ADDRESS, ucxusbdevice/P_USBDEVICE_ADDRESS, P_USBDEVICE_ADDRESS, _USBDEVICE_ADDRESS, buses._usbdevice_address, USBDEVICE_ADDRESS, ucxusbdevice/_USBDEVICE_ADDRESS
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
-	USBDEVICE_ADDRESS
product: Windows
targetos: Windows
req.typenames: USBDEVICE_ADDRESS, *PUSBDEVICE_ADDRESS
req.product: Windows 10 or later.
---

# _USBDEVICE_ADDRESS structure


## -description


Contains parameters for a request to transition the specified device to the Addressed state. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_address.md">EVT_UCX_USBDEVICE_ADDRESS</a> callback function. 


## -syntax


````
typedef struct _USBDEVICE_ADDRESS {
#if _cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
  ULONG                 Reserved;
  ULONG                 Address;
} USBDEVICE_ADDRESS, *P_USBDEVICE_ADDRESS;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field Reserved

Do not use.


### -field Address

The address of the specified the USB hub or device. 


## -see-also

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_address.md">EVT_UCX_USBDEVICE_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBDEVICE_ADDRESS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

