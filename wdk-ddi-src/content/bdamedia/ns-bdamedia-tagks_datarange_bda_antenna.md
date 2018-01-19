---
UID: NS:bdamedia.tagKS_DATARANGE_BDA_ANTENNA
title: tagKS_DATARANGE_BDA_ANTENNA
author: windows-driver-content
description: The KS_DATARANGE_BDA_ANTENNA structure describes a range of data formats for a BDA antenna stream.
old-location: stream\ks_datarange_bda_antenna.htm
old-project: stream
ms.assetid: 32a396c9-01a5-4e17-bcb5-659f7a88c0ef
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKS_DATARANGE_BDA_ANTENNA, KS_DATARANGE_BDA_ANTENNA, *PKS_DATARANGE_BDA_ANTENNA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_DATARANGE_BDA_ANTENNA
req.alt-loc: bdamedia.h
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
req.typenames: KS_DATARANGE_BDA_ANTENNA, *PKS_DATARANGE_BDA_ANTENNA
---

# tagKS_DATARANGE_BDA_ANTENNA structure



## -description
The KS_DATARANGE_BDA_ANTENNA structure describes a range of data formats for a BDA antenna stream. 



## -syntax

````
typedef struct tagKS_DATARANGE_BDA_ANTENNA {
  KSDATARANGE DataRange;
} KS_DATARANGE_BDA_ANTENNA, *PKS_DATARANGE_BDA_ANTENNA;
````


## -struct-fields

### -field DataRange

KSDATARANGE structure that describes a range of data formats with the <b>MajorFormat</b> member specified as STATIC_KSDATAFORMAT_TYPE_BDA_ANTENNA.


## -remarks
A data range describes a range of data formats. 

Pins of filters specify the data ranges they support to enable stream connections to pins of other filters that also support those data ranges.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556552">BDA Stream Format GUIDs</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksdataformat.md">KSDATARANGE</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATARANGE_BDA_ANTENNA structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

