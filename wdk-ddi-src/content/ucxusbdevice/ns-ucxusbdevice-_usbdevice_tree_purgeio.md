---
UID: NS:ucxusbdevice._USBDEVICE_TREE_PURGEIO
title: "_USBDEVICE_TREE_PURGEIO"
author: windows-driver-content
description: This structure provides the handle for the Universal Serial Bus (USB) device tree to purge I/O for.
old-location: buses\_usbdevice_tree_purgeio.htm
old-project: usbref
ms.assetid: 47C442F5-7D16-4E73-8D05-82D63D5265C1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ucxusbdevice/P_USBDEVICE_TREE_PURGEIO, *PUSBDEVICE_TREE_PURGEIO, P_USBDEVICE_TREE_PURGEIO, USBDEVICE_TREE_PURGEIO structure [Buses], ucxusbdevice/_USBDEVICE_TREE_PURGEIO, P_USBDEVICE_TREE_PURGEIO structure pointer [Buses], buses._usbdevice_tree_purgeio, USBDEVICE_TREE_PURGEIO, _USBDEVICE_TREE_PURGEIO
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
-	USBDEVICE_TREE_PURGEIO
product: Windows
targetos: Windows
req.typenames: USBDEVICE_TREE_PURGEIO, *PUSBDEVICE_TREE_PURGEIO
req.product: Windows 10 or later.
---

# _USBDEVICE_TREE_PURGEIO structure


## -description


This structure provides the handle for the Universal Serial Bus (USB) device tree to purge I/O for.


## -syntax


````
typedef struct __USBDEVICE_TREE_PURGEIO {
#if _cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
} USBDEVICE_TREE_PURGEIO, *P_USBDEVICE_TREE_PURGEIO;
````


## -struct-fields




#### - Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


## -see-also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_purgeio.md">USBDEVICE_PURGEIO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_TREE_PURGEIO structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

