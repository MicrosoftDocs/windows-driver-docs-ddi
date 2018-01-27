---
UID: NS:ucxusbdevice._USBDEVICE_ABORTIO
title: _USBDEVICE_ABORTIO
author: windows-driver-content
description: Contains a handle for the Universal Serial Bus (USB) hub or device for which to abort data transfers.
old-location: buses\_usbdevice_abortio.htm
old-project: usbref
ms.assetid: 69720940-4D3E-43E6-B587-427ED2049FCC
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USBDEVICE_ABORTIO, ucxusbdevice/_USBDEVICE_ABORTIO, buses._usbdevice_abortio, USBDEVICE_ABORTIO structure [Buses], *PUSBDEVICE_ABORTIO, USBDEVICE_ABORTIO, P_USBDEVICE_ABORTIO, ucxusbdevice/P_USBDEVICE_ABORTIO, P_USBDEVICE_ABORTIO structure pointer [Buses]
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
-	USBDEVICE_ABORTIO
product: Windows
targetos: Windows
req.typenames: *PUSBDEVICE_ABORTIO, USBDEVICE_ABORTIO
req.product: Windows 10 or later.
---

# _USBDEVICE_ABORTIO structure


## -description


Contains a handle for the Universal Serial Bus (USB) hub or device for which to abort data transfers. 


## -syntax


````
typedef struct _USBDEVICE_ABORTIO {
#if _cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} USBDEVICE_ABORTIO, *P_USBDEVICE_ABORTIO;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_purgeio.md">USBDEVICE_PURGEIO</a>

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_startio.md">USBDEVICE_STARTIO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_ABORTIO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

