---
UID: NS:usbfnattach._USBFN_ON_ATTACH
title: "_USBFN_ON_ATTACH"
author: windows-driver-content
description: Describes the detected port type and attach action.
old-location: buses\usbfn_on_attach.htm
old-project: usbref
ms.assetid: 2CD75FA9-F77E-4AC5-870E-69CF05DB9312
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PUSBFN_ON_ATTACH, *PUSBFN_ON_ATTACH, usbfnattach/USBFN_ON_ATTACH, USBFN_ON_ATTACH, PUSBFN_ON_ATTACH structure pointer [Buses], buses.usbfn_on_attach, _USBFN_ON_ATTACH, USBFN_ON_ATTACH structure [Buses], usbfnattach/PUSBFN_ON_ATTACH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnattach.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbfnattach.h
apiname:
-	USBFN_ON_ATTACH
product: Windows
targetos: Windows
req.typenames: "*PUSBFN_ON_ATTACH, USBFN_ON_ATTACH"
req.product: Windows 10 or later.
---

# _USBFN_ON_ATTACH structure


## -description


Describes the detected port type and attach action. 


## -syntax


````
typedef struct _USBFN_ON_ATTACH {
  USBFN_PORT_TYPE     PortType;
  USBFN_ATTACH_ACTION AttachAction;
} USBFN_ON_ATTACH, *PUSBFN_ON_ATTACH;
````


## -struct-fields




### -field PortType

Detected port type defined by one of the <a href="..\usbfnbase\ne-usbfnbase-_usbfn_port_type.md">USBFN_PORT_TYPE</a>-typed values.


### -field AttachAction

The operation that must be performed depending on the port type. This value is defined in the <a href="..\usbfnattach\ne-usbfnattach-_usbfn_attach_action.md">USBFN_ATTACH_ACTION</a> enumeration.


## -see-also

<a href="..\usbfnattach\nc-usbfnattach-usbfn_get_attach_action.md">USBFN_GET_ATTACH_ACTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_ON_ATTACH structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

