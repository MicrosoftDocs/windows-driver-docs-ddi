---
UID: NS:ks.KSMULTIPLE_ITEM
title: KSMULTIPLE_ITEM
author: windows-driver-content
description: The KSMULTIPLE_ITEM structure is a generic header for property data that can contain multiple entries.
old-location: stream\ksmultiple_item.htm
old-project: stream
ms.assetid: f8a15cb0-92c5-4637-934e-021fa7969208
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSMULTIPLE_ITEM, *PKSMULTIPLE_ITEM, KSMULTIPLE_ITEM
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
req.alt-api: KSMULTIPLE_ITEM
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
req.typenames: *PKSMULTIPLE_ITEM, KSMULTIPLE_ITEM
---

# KSMULTIPLE_ITEM structure



## -description
The KSMULTIPLE_ITEM structure is a generic header for property data that can contain multiple entries.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Count;
} KSMULTIPLE_ITEM, *PKSMULTIPLE_ITEM;
````


## -struct-fields

### -field Size

Specifies the size in bytes of this header and the property data that follows.


### -field Count

Specifies the number of buffers that follow this header.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/23c020e8-b778-4784-9dc0-21920557e1c1">Kernel Streaming Property Sets</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSMULTIPLE_ITEM structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

