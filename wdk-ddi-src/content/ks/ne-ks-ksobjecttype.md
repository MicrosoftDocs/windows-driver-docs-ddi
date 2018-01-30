---
UID: NE:ks.KSOBJECTTYPE
title: KSOBJECTTYPE
author: windows-driver-content
description: The KSOBJECTTYPE enumeration lists different types of kernel streaming objects.
old-location: stream\ksobjecttype.htm
old-project: stream
ms.assetid: ab30d24f-4f14-4a84-a6e1-1a2506b4ba87
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSOBJECTTYPE, KsObjectTypeFilterFactory, ks/KsObjectTypeFilter, stream.ksobjecttype, KsObjectTypePin, ks/KsObjectTypeDevice, ks/KsObjectTypePin, KSOBJECTTYPE enumeration [Streaming Media Devices], ks/KSOBJECTTYPE, ks-struct_b8010334-0906-4d4b-8c65-b3919b7b8257.xml, ks/KsObjectTypeFilterFactory, KsObjectTypeFilter, KsObjectTypeDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSOBJECTTYPE
product: Windows
targetos: Windows
req.typenames: KSOBJECTTYPE
---

# KSOBJECTTYPE enumeration


## -description


The KSOBJECTTYPE enumeration lists different types of kernel streaming objects.


## -syntax


````
typedef enum  { 
  KsObjectTypeDevice         = 0,
  KsObjectTypeFilterFactory  = 1,
  KsObjectTypeFilter         = 2,
  KsObjectTypePin            = 3
} KSOBJECTTYPE;
````


## -enum-fields




### -field KsObjectTypeDevice

Specifies that the object is a device.


### -field KsObjectTypeFilterFactory

Specifies that the object is a filter factory.


### -field KsObjectTypeFilter

Specifies that the object is a filter.


### -field KsObjectTypePin

Specifies that the object is a pin.


## -see-also

<a href="..\ks\nf-ks-kspingetconnectedpinfileobject.md">KsPinGetConnectedPinFileObject</a>

<a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a>

<a href="..\ks\nf-ks-ksgetfilterfromfileobject.md">KsGetFilterFromFileObject</a>

<a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>

<a href="..\ks\nf-ks-ksgetpinfromfileobject.md">KsGetPinFromFileObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSOBJECTTYPE enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

