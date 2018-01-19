---
UID: NS:ks.KSPROPERTY_SERIALHDR
title: KSPROPERTY_SERIALHDR
author: windows-driver-content
description: The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties.
old-location: stream\ksproperty_serialhdr.htm
old-project: stream
ms.assetid: 164c34ce-603f-447b-8bd7-14b1c19e9baa
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_SERIALHDR, KSPROPERTY_SERIALHDR, *PKSPROPERTY_SERIALHDR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_SERIALHDR
req.alt-loc: ks.h
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
req.typenames: KSPROPERTY_SERIALHDR, *PKSPROPERTY_SERIALHDR
---

# KSPROPERTY_SERIALHDR structure



## -description
The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties.



## -syntax

````
typedef struct {
  GUID  PropertySet;
  ULONG Count;
} KSPROPERTY_SERIALHDR, *PKSPROPERTY_SERIALHDR;
````


## -struct-fields

### -field PropertySet

Specifies the GUID of the property set contained in the serialized buffer.


### -field Count

Specifies the count of serialized properties to follow.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksproperty_serial.md">KSPROPERTY_SERIAL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_SERIALHDR structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

