---
UID: NS:ksmedia._KS_DVDCOPY_REGION
title: "_KS_DVDCOPY_REGION"
author: windows-driver-content
description: The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions.
old-location: stream\ks_dvdcopy_region.htm
old-project: stream
ms.assetid: 159a8dd0-6efa-4f2c-921c-c427e1cf59ec
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: dvdref_ff087f30-2337-4b0f-8ae1-8a42cacaa5ae.xml, KS_DVDCOPY_REGION structure [Streaming Media Devices], *PKS_DVDCOPY_REGION, _KS_DVDCOPY_REGION, ksmedia/KS_DVDCOPY_REGION, ksmedia/PKS_DVDCOPY_REGION, PKS_DVDCOPY_REGION structure pointer [Streaming Media Devices], PKS_DVDCOPY_REGION, stream.ks_dvdcopy_region, KS_DVDCOPY_REGION
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
-	KS_DVDCOPY_REGION
product: Windows
targetos: Windows
req.typenames: "*PKS_DVDCOPY_REGION, KS_DVDCOPY_REGION"
---

# _KS_DVDCOPY_REGION structure


## -description


The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions.


## -syntax


````
typedef struct _KS_DVDCOPY_REGION {
  UCHAR Reserved;
  UCHAR RegionData;
  UCHAR Reserved2[2];
} KS_DVDCOPY_REGION, *PKS_DVDCOPY_REGION;
````


## -struct-fields




### -field Reserved

Reserved. Do not use.


### -field RegionData

Specifies the region code for the nationality or language, as described in the following table:
<table>
<tr>
<th>Numeric Code</th>
<th>Description</th>
</tr>
<tr>
<td>
1

</td>
<td>
North America

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Japan, European Union, Middle East, Egypt, South Africa and Greenland

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Southeast Asia (including Hong Kong SAR)

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Central/South America, Australia, New Zealand and the Caribbean

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Africa, Northwest Asia (including Korea)

</td>
</tr>
<tr>
<td>
6

</td>
<td>
China

</td>
</tr>
</table> 


### -field Reserved2

Reserved. Do not use.


## -remarks


The KS_DVDCOPY_REGION structure is used by the KSPROPERTY_DVDCOPY_REGION property.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a> and <a href="https://msdn.microsoft.com/931441c8-9521-43c9-86f1-dbf75d36e190">DVD Regionalization</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565146">KSPROPERTY_DVDCOPY_REGION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPY_REGION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

