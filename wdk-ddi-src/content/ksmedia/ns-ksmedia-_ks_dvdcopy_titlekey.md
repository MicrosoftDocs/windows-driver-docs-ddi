---
UID: NS:ksmedia._KS_DVDCOPY_TITLEKEY
title: _KS_DVDCOPY_TITLEKEY (ksmedia.h)
description: The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_titlekey.htm
tech.root: stream
ms.assetid: 8f85bc55-d05b-4075-9ae5-ba5a5516eeb4
ms.date: 04/23/2018
keywords: ["KS_DVDCOPY_TITLEKEY structure"]
ms.keywords: "*PKS_DVDCOPY_TITLEKEY, KS_DVDCOPY_TITLEKEY, KS_DVDCOPY_TITLEKEY structure [Streaming Media Devices], PKS_DVDCOPY_TITLEKEY, PKS_DVDCOPY_TITLEKEY structure pointer [Streaming Media Devices], _KS_DVDCOPY_TITLEKEY, dvdref_58692699-8652-436a-92d5-2284c4d30265.xml, ksmedia/KS_DVDCOPY_TITLEKEY, ksmedia/PKS_DVDCOPY_TITLEKEY, stream.ks_dvdcopy_titlekey"
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
req.typenames: KS_DVDCOPY_TITLEKEY, *PKS_DVDCOPY_TITLEKEY
f1_keywords:
 - _KS_DVDCOPY_TITLEKEY
 - ksmedia/_KS_DVDCOPY_TITLEKEY
 - PKS_DVDCOPY_TITLEKEY
 - ksmedia/PKS_DVDCOPY_TITLEKEY
 - KS_DVDCOPY_TITLEKEY
 - ksmedia/KS_DVDCOPY_TITLEKEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_DVDCOPY_TITLEKEY
---

# _KS_DVDCOPY_TITLEKEY structure


## -description

The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process.

## -struct-fields

### -field KeyFlags

Title key flags settings that provide Copyrighted Material flag (CPM), Copy Guard Management System (CGMS) and Copyright Protection System (CP_SEC) copyright protection flags from the DVD drive. The following CGMS flags are defined:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_DVD_CGMS_RESERVED_MASK

</td>
<td>
Specifies the mask of all defined CPM, CGMS and CP_SEC flags (that is, all the other flags listed here).

</td>
</tr>
<tr>
<td>
KS_DVD_CGMS_COPY_PROTECT_MASK

</td>
<td>
Specifies the mask of all defined CGMS flags.

</td>
</tr>
<tr>
<td>
KS_DVD_CGMS_COPY_PERMITTED

</td>
<td>
Indicates that the content protected by CGMS can be copied.

</td>
</tr>
<tr>
<td>
KS_DVD_CGMS_COPY_ONCE

</td>
<td>
Indicates that the content protected by CGMS can be copied only a single time. As part of the copy process, this flag should be cleared, and the KS_DVD_CGMS_NO_COPY flags must be set to prevent subsequent copying.

</td>
</tr>
<tr>
<td>
KS_DVD_CGMS_NO_COPY

</td>
<td>
Indicates that the content protected by CGMS cannot be copied.

</td>
</tr>
<tr>
<td>
KS_DVD_COPYRIGHT_MASK

</td>
<td>
Specifies the mask of all defined CPM flags (KS_DVD_NOT_COPYRIGHTED and KS_DVD_COPYRIGHTED).

</td>
</tr>
<tr>
<td>
KS_DVD_NOT_COPYRIGHTED

</td>
<td>
Indicates that the content marked by CPM is not copyrighted.

</td>
</tr>
<tr>
<td>
KS_DVD_COPYRIGHTED

</td>
<td>
Indicates that the content marked by CPM is copyrighted.

</td>
</tr>
<tr>
<td>
KS_DVD_SECTOR_PROTECT_MASK

</td>
<td>
The mask of all defined sector protection flags.

</td>
</tr>
<tr>
<td>
KS_DVD_SECTOR_NOT_PROTECTED

</td>
<td>
Indicates that the sector is not protected (encrypted).

</td>
</tr>
<tr>
<td>
KS_DVD_SECTOR_PROTECTED

</td>
<td>
Indicates that the sector is protected (encrypted).

</td>
</tr>
</table>

### -field ReservedNT

Reserved. Do not use.

### -field TitleKey

Specifies the current title key.

### -field Reserved

Reserved. Do not use.

## -remarks

The KS_DVDCOPY_TITLEKEY structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-dvdcopy-title-key">KSPROPERTY_DVDCOPY_TITLE_KEY</a> property.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/dvd-copyright-protection">DVD Copyright Protection</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-dvdcopy-title-key">KSPROPERTY_DVDCOPY_TITLE_KEY</a>

