---
UID: NS:ksmedia.tagKS_DATAFORMAT_VBIINFOHEADER
title: tagKS_DATAFORMAT_VBIINFOHEADER
author: windows-driver-content
description: The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream.
old-location: stream\ks_dataformat_vbiinfoheader.htm
old-project: stream
ms.assetid: 597b081f-d2ff-4e20-b352-2082f1ef4d45
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKS_DATAFORMAT_VBIINFOHEADER, KS_DATAFORMAT_VBIINFOHEADER, *PKS_DATAFORMAT_VBIINFOHEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_DATAFORMAT_VBIINFOHEADER
req.alt-loc: ksmedia.h
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
req.typenames: KS_DATAFORMAT_VBIINFOHEADER, *PKS_DATAFORMAT_VBIINFOHEADER
---

# tagKS_DATAFORMAT_VBIINFOHEADER structure



## -description
The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream.



## -syntax

````
typedef struct tagKS_DATAFORMAT_VBIINFOHEADER {
  KSDATAFORMAT     DataFormat;
  KS_VBIINFOHEADER VBIInfoHeader;
} KS_DATAFORMAT_VBIINFOHEADER, *PKS_DATAFORMAT_VBIINFOHEADER;
````


## -struct-fields

### -field DataFormat

Specifies the data format being proposed.


### -field VBIInfoHeader

Describes VBI-specific information about the proposed connection.


## -remarks
This structure is used when a connection to a VBI pin is being proposed.


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagks_vbiinfoheader.md">KS_VBIINFOHEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DATAFORMAT_VBIINFOHEADER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

