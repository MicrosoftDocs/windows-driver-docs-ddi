---
UID: NE:ucxroothub._CONTROLLER_TYPE
title: "_CONTROLLER_TYPE"
author: windows-driver-content
description: This enumeration specifies if the USB host controller is an eXtensible Host Controller Interface (xHCI) controller.
old-location: buses\_controller_type.htm
old-project: usbref
ms.assetid: E7DFBFFA-C65B-4757-8DB8-202760D6D3C6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ucxroothub/ControllerTypeXhci, ucxroothub/ControllerTypeSoftXhci, CONTROLLER_TYPE, _CONTROLLER_TYPE, _CONTROLLER_TYPE enumeration [Buses], ucxroothub/_CONTROLLER_TYPE, ControllerTypeSoftXhci, ControllerTypeXhci, buses._controller_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxroothub.h
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
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxroothub.h
apiname:
-	CONTROLLER_TYPE
product: Windows
targetos: Windows
req.typenames: CONTROLLER_TYPE
req.product: Windows 10 or later.
---

# _CONTROLLER_TYPE enumeration


## -description


This enumeration specifies if the USB host controller is an eXtensible Host Controller Interface (xHCI) controller.


## -syntax


````
typedef enum _CONTROLLER_TYPE { 
  ControllerTypeXhci,
  ControllerTypeSoftXhci
} CONTROLLER_TYPE;
````


## -enum-fields




### -field ControllerTypeXhci

Indicates the USB host controller is an xHCI controller.


### -field ControllerTypeSoftXhci

Indicates the USB host controller is software an xHCI controller.


## -see-also

<a href="..\ucxroothub\ns-ucxroothub-_roothub_info.md">ROOTHUB_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20CONTROLLER_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

