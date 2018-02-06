---
UID: NS:ks.KSATTRIBUTE
title: KSATTRIBUTE
author: windows-driver-content
description: The KSATTRIBUTE structure defines an additional attribute of a data format or data range that is not covered by the KSDATAFORMAT and KSDATARANGE structures or the extended information based on the format and range specifiers.
old-location: stream\ksattribute.htm
old-project: stream
ms.assetid: 985d9f12-11c6-40e6-9cb6-572196bc04f4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks-struct_02cb064e-813f-4d67-8cf3-a33e05af7421.xml, KSATTRIBUTE, stream.ksattribute, ks/KSATTRIBUTE, ks/PKSATTRIBUTE, PKSATTRIBUTE structure pointer [Streaming Media Devices], PKSATTRIBUTE, KSATTRIBUTE structure [Streaming Media Devices], *PKSATTRIBUTE
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
-	KSATTRIBUTE
product: Windows
targetos: Windows
req.typenames: KSATTRIBUTE, *PKSATTRIBUTE
---

# KSATTRIBUTE structure


## -description


The KSATTRIBUTE structure defines an additional attribute of a data format or data range that is not covered by the <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> and <a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a> structures or the extended information based on the format and range specifiers.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Flags;
  GUID  Attribute;
} KSATTRIBUTE, *PKSATTRIBUTE;
````


## -struct-fields




### -field Size

Specifies the size of the attribute. This is at least the size of the KSATTRIBUTE structure and may be more if there is extended information based on the identifying GUID in the <b>Attribute</b> field.


### -field Flags

Specifies the flags of the attribute. The only used flag is KSATTRIBUTE_REQUIRED; this flag specifies that an attribute is required. If this flag is not set, the attribute is optional. Note that the topmost bit is reserved for internal use in KS.


### -field Attribute

Specifies the unique identifier of the attribute.


## -remarks


Note that KSATTRIBUTE is used in conjunction with data formats and data ranges; attributes on data formats and ranges are taken into consideration when determining if a data format is acceptable to a given pin or if a data range intersects with another data range.



## -see-also

<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>

<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSATTRIBUTE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

