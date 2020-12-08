---
UID: NS:ksmedia._KS_DVDCOPY_REGION
title: _KS_DVDCOPY_REGION (ksmedia.h)
description: The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions.
old-location: stream\ks_dvdcopy_region.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KS_DVDCOPY_REGION structure"]
ms.keywords: "*PKS_DVDCOPY_REGION, KS_DVDCOPY_REGION, KS_DVDCOPY_REGION structure [Streaming Media Devices], PKS_DVDCOPY_REGION, PKS_DVDCOPY_REGION structure pointer [Streaming Media Devices], _KS_DVDCOPY_REGION, dvdref_ff087f30-2337-4b0f-8ae1-8a42cacaa5ae.xml, ksmedia/KS_DVDCOPY_REGION, ksmedia/PKS_DVDCOPY_REGION, stream.ks_dvdcopy_region"
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
targetos: Windows
req.typenames: KS_DVDCOPY_REGION, *PKS_DVDCOPY_REGION
f1_keywords:
 - _KS_DVDCOPY_REGION
 - ksmedia/_KS_DVDCOPY_REGION
 - PKS_DVDCOPY_REGION
 - ksmedia/PKS_DVDCOPY_REGION
 - KS_DVDCOPY_REGION
 - ksmedia/KS_DVDCOPY_REGION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DVDCOPY_REGION
---

# _KS_DVDCOPY_REGION structure


## -description

The KS_DVDCOPY_REGION structure is used to describe the copy control region according to language restrictions.

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

For more information, see <a href="/windows-hardware/drivers/stream/dvd-copyright-protection">DVD Copyright Protection</a> and <a href="/windows-hardware/drivers/stream/dvd-regionalization">DVD Regionalization</a>.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-dvdcopy-region">KSPROPERTY_DVDCOPY_REGION</a>
