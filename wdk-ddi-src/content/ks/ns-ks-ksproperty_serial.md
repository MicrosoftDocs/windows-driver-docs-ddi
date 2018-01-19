---
UID: NS:ks.KSPROPERTY_SERIAL
title: KSPROPERTY_SERIAL
author: windows-driver-content
description: The KSPROPERTY_SERIAL structure is a header that is included for each property that follows a KSPROPERTY_SERIALHDR structure.
old-location: stream\ksproperty_serial.htm
old-project: stream
ms.assetid: 751bf70d-0602-487a-82c7-efca075b8968
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_SERIAL, *PKSPROPERTY_SERIAL, KSPROPERTY_SERIAL
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
req.alt-api: KSPROPERTY_SERIAL
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
req.typenames: *PKSPROPERTY_SERIAL, KSPROPERTY_SERIAL
---

# KSPROPERTY_SERIAL structure



## -description
The KSPROPERTY_SERIAL structure is a header that is included for each property that follows a KSPROPERTY_SERIALHDR structure.



## -syntax

````
typedef struct {
  KSIDENTIFIER PropTypeSet;
  ULONG        Id;
  ULONG        PropertyLength;
} KSPROPERTY_SERIAL, *PKSPROPERTY_SERIAL;
````


## -struct-fields

### -field PropTypeSet

A structure of type <a href="..\ks\ns-ks-ksidentifier.md">KSIDENTIFIER</a> that specifies the type of property data. This is the same information obtained from querying Basic Support.


### -field Id

Specifies the identifier for this property.


### -field PropertyLength

Specifies the length, in bytes, of the following property data. This does not include any alignment buffering that may be appended to the property data before the next property in the serialization.


## -remarks
A KSPROPERTY_SERIAL structure is followed by the property data, with the start of each property on FILE_LONG_ALIGNMENT. Note that the serial header structure itself is also defined to be on FILE_LONG_ALIGNMENT.


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksproperty_serialhdr.md">KSPROPERTY_SERIALHDR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_SERIAL structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

