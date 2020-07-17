---
UID: NS:ksmedia._KS_COPY_MACROVISION
title: _KS_COPY_MACROVISION (ksmedia.h)
description: The KS_COPY_MACROVISION structure specifies the Macrovision level of the data stream.
old-location: stream\ks_copy_macrovision.htm
tech.root: stream
ms.assetid: 86c6ee78-ae4e-4b96-be83-a5960f36a363
ms.date: 04/23/2018
keywords: ["_KS_COPY_MACROVISION structure"]
ms.keywords: "*PKS_COPY_MACROVISION, KS_COPY_MACROVISION, KS_COPY_MACROVISION structure [Streaming Media Devices], PKS_COPY_MACROVISION, PKS_COPY_MACROVISION structure pointer [Streaming Media Devices], _KS_COPY_MACROVISION, dvdref_42184498-7ac6-48d2-9f26-5bf69ececabb.xml, ksmedia/KS_COPY_MACROVISION, ksmedia/PKS_COPY_MACROVISION, stream.ks_copy_macrovision"
f1_keywords:
 - "ksmedia/KS_COPY_MACROVISION"
 - "KS_COPY_MACROVISION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KS_COPY_MACROVISION
product:
- Windows
targetos: Windows
req.typenames: KS_COPY_MACROVISION, *PKS_COPY_MACROVISION
---

# _KS_COPY_MACROVISION structure


## -description


The KS_COPY_MACROVISION structure specifies the Macrovision level of the data stream.


## -struct-fields




### -field MACROVISIONLevel

Specifies the Macrovision level. This must be one of the following values from the KS_COPY_MACROVISION_LEVEL enumeration:

<table>
<tr>
<th>Level</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_MACROVISION_DISABLED

</td>
<td>
Indicates that Macrovision copyright protection should not be in effect.

</td>
</tr>
<tr>
<td>
KS_MACROVISION_LEVEL1

</td>
<td>
Indicates that Macrovision level 1 copyright protection must be in effect.

</td>
</tr>
<tr>
<td>
KS_MACROVISION_LEVEL2

</td>
<td>
Indicates that Macrovision level 2 copyright protection must be in effect.

</td>
</tr>
<tr>
<td>
KS_MACROVISION_LEVEL3

</td>
<td>
Indicates that Macrovision level 3 copyright protection must be in effect.

</td>
</tr>
</table>
 


## -remarks



The KS_COPY_MACROVISION structure is used by the KSPROPERTY_COPY_MACROVISION property.

For additional uses of this structure see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/dvd-copyright-protection">DVD Copyright Protection</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/macrovision">Macrovision</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-copy-macrovision">KSPROPERTY_COPY_MACROVISION</a>
 

 

