---
UID: NE:ks.__unnamed_enum_38
title: KSOBJECTTYPE (ks.h)
description: The KSOBJECTTYPE enumeration lists different types of kernel streaming objects.
old-location: stream\ksobjecttype.htm
tech.root: stream
ms.assetid: ab30d24f-4f14-4a84-a6e1-1a2506b4ba87
ms.date: 04/23/2018
ms.keywords: KSOBJECTTYPE, KSOBJECTTYPE enumeration [Streaming Media Devices], KsObjectTypeDevice, KsObjectTypeFilter, KsObjectTypeFilterFactory, KsObjectTypePin, ks-struct_b8010334-0906-4d4b-8c65-b3919b7b8257.xml, ks/KSOBJECTTYPE, ks/KsObjectTypeDevice, ks/KsObjectTypeFilter, ks/KsObjectTypeFilterFactory, ks/KsObjectTypePin, stream.ksobjecttype
f1_keywords:
 - "ks/KSOBJECTTYPE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSOBJECTTYPE
product:
- Windows
targetos: Windows
req.typenames: KSOBJECTTYPE
---

# KSOBJECTTYPE enumeration


## -description


The KSOBJECTTYPE enumeration lists different types of kernel streaming objects.


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetfilterfromfileobject">KsGetFilterFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetobjectfromfileobject">KsGetObjectFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetobjecttypefromfileobject">KsGetObjectTypeFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-ksgetpinfromfileobject">KsGetPinFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpinfileobject">KsPinGetConnectedPinFileObject</a>
 

 

