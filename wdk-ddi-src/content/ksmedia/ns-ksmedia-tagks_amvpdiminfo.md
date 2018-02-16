---
UID: NS:ksmedia.tagKS_AMVPDIMINFO
title: tagKS_AMVPDIMINFO
author: windows-driver-content
description: The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.
old-location: stream\ks_amvpdiminfo.htm
old-project: stream
ms.assetid: 5b8126ee-ba47-4eaf-887a-764e17a20e03
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ks_amvpdiminfo, KS_AMVPDIMINFO, PKS_AMVPDIMINFO, dvdref_4c6b6231-a3ef-49a5-8b27-c7ba0062c53a.xml, KS_AMVPDIMINFO structure [Streaming Media Devices], *PKS_AMVPDIMINFO, ksmedia/KS_AMVPDIMINFO, PKS_AMVPDIMINFO structure pointer [Streaming Media Devices], tagKS_AMVPDIMINFO, ksmedia/PKS_AMVPDIMINFO
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
-	ksmedia.h
apiname:
-	KS_AMVPDIMINFO
product: Windows
targetos: Windows
req.typenames: "*PKS_AMVPDIMINFO, KS_AMVPDIMINFO"
---

# tagKS_AMVPDIMINFO structure


## -description


The KS_AMVPDIMINFO structure is used to describe the dimensions of a video port.


## -syntax


````
typedef struct tagKS_AMVPDIMINFO {
  DWORD dwFieldWidth;
  DWORD dwFieldHeight;
  DWORD dwVBIWidth;
  DWORD dwVBIHeight;
  RECT  rcValidRegion;
} KS_AMVPDIMINFO, *PKS_AMVPDIMINFO;
````


## -struct-fields




### -field dwFieldWidth

Specifies the field width.


### -field dwFieldHeight

Specifies the field height.


### -field dwVBIWidth

Specifies the VBI data width.


### -field dwVBIHeight

Specifies the VBI data height.


### -field rcValidRegion

Describes a valid rectangle for data cropping.


## -remarks



This structure is used by the <a href="..\ksmedia\ns-ksmedia-tagks_amvpdatainfo.md">KS_AMVPDATAINFO</a> structure.




## -see-also

<a href="..\ksmedia\ns-ksmedia-tagks_amvpdatainfo.md">KS_AMVPDATAINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_AMVPDIMINFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

