---
UID: NS:ksmedia.MEDIUM_INFO
title: MEDIUM_INFO
author: windows-driver-content
description: The MEDIUM_INFO structure describes the media loaded into an external device.
old-location: stream\medium_info.htm
old-project: stream
ms.assetid: 1dd7415d-bfbc-4dea-bac9-bc5b8531a47f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: MEDIUM_INFO, *PMEDIUM_INFO, MEDIUM_INFO
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
req.alt-api: MEDIUM_INFO
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
req.typenames: *PMEDIUM_INFO, MEDIUM_INFO
---

# MEDIUM_INFO structure



## -description
The MEDIUM_INFO structure describes the media loaded into an external device.



## -syntax

````
typedef struct {
  BOOL  MediaPresent;
  ULONG MediaType;
  BOOL  RecordInhibit;
} MEDIUM_INFO, *PMEDIUM_INFO;
````


## -struct-fields

### -field MediaPresent

Specifies if media is present in the external device. <b>TRUE</b> if media is loaded, <b>FALSE</b> otherwise.


### -field MediaType

Indicates the type of the media loaded in an external device.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ED_MEDIA_DVC

</td>
<td>
Digital video cassette. For example MiniDV

</td>
</tr>
<tr>
<td>
ED_MEDIA_VHS

</td>
<td>
VHS cassette

</td>
</tr>
<tr>
<td>
ED_MEDIA_HI8

</td>
<td>
Hi-8 cassette

</td>
</tr>
</table>
 


### -field RecordInhibit

Specifies if recording is inhibited on the media. <b>TRUE</b> if recording onto the media is inhibited, <b>FALSE</b> otherwise.


## -remarks
Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.</p>