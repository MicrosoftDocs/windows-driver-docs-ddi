---
UID: NS:ucxusbdevice._USBDEVICE_PURGEIO
title: "_USBDEVICE_PURGEIO"
author: windows-driver-content
description: The USBDEVICE_PURGEIO structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.
old-location: buses\_usbdevice_purgeio.htm
old-project: UsbRef
ms.assetid: 5E45A5A0-59EE-4A72-9CCA-DD1C9A406EB5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PUSBDEVICE_PURGEIO, ,, B, C, D, E, G, I, O, P, P_USBDEVICE_PURGEIO, P_USBDEVICE_PURGEIO structure pointer [Buses], R, S, U, USBDEVICE_PURGEIO, USBDEVICE_PURGEIO structure [Buses], V, _, _USBDEVICE_PURGEIO, buses._usbdevice_purgeio, ucxusbdevice/P_USBDEVICE_PURGEIO, ucxusbdevice/_USBDEVICE_PURGEIO"
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
-	USBDEVICE_PURGEIO
product: Windows
targetos: Windows
req.typenames: USBDEVICE_PURGEIO, *PUSBDEVICE_PURGEIO
req.product: Windows 10 or later.
---

# _USBDEVICE_PURGEIO structure


## -description


The <b>USBDEVICE_PURGEIO</b> structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for.


## -syntax


````
typedef struct _USBDEVICE_PURGEIO {
#if 
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} USBDEVICE_PURGEIO, *P_USBDEVICE_PURGEIO;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field OnSuspend

 




## -see-also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_tree_purgeio.md">USBDEVICE_TREE_PURGEIO</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_startio.md">USBDEVICE_STARTIO</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_abortio.md">USBDEVICE_ABORTIO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBDEVICE_PURGEIO structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

