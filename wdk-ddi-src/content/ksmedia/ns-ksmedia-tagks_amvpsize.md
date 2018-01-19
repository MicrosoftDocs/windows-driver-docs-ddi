---
UID: NS:ksmedia.tagKS_AMVPSIZE
title: tagKS_AMVPSIZE
author: windows-driver-content
description: The KS_AMVPSIZE structure is used to describe the dimension of a video port (width by height).
old-location: stream\ks_amvpsize.htm
old-project: stream
ms.assetid: 31430419-8f83-4f46-b398-841895f415d5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKS_AMVPSIZE, *PKS_AMVPSIZE, KS_AMVPSIZE
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
req.alt-api: KS_AMVPSIZE
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
req.typenames: *PKS_AMVPSIZE, KS_AMVPSIZE
---

# tagKS_AMVPSIZE structure



## -description
The KS_AMVPSIZE structure is used to describe the dimension of a video port (width by height).



## -syntax

````
typedef struct tagKS_AMVPSIZE {
  DWORD dwWidth;
  DWORD dwHeight;
} KS_AMVPSIZE, *PKS_AMVPSIZE;
````


## -struct-fields

### -field dwWidth

Specifies the width of the video port, in pixels.


### -field dwHeight

Specifies the height of the video port, in pixels.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566502">KSPROPERTY_VPCONFIG_SCALEFACTOR</a> property.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566502">KSPROPERTY_VPCONFIG_SCALEFACTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AMVPSIZE structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

