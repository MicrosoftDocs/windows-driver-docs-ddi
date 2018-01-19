---
UID: NS:ksmedia._KS_DVDCOPY_TITLEKEY
title: _KS_DVDCOPY_TITLEKEY
author: windows-driver-content
description: The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process.
old-location: stream\ks_dvdcopy_titlekey.htm
old-project: stream
ms.assetid: 8f85bc55-d05b-4075-9ae5-ba5a5516eeb4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _KS_DVDCOPY_TITLEKEY, *PKS_DVDCOPY_TITLEKEY, KS_DVDCOPY_TITLEKEY
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
req.alt-api: KS_DVDCOPY_TITLEKEY
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
req.typenames: *PKS_DVDCOPY_TITLEKEY, KS_DVDCOPY_TITLEKEY
---

# _KS_DVDCOPY_TITLEKEY structure



## -description
The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process.



## -syntax

````
typedef struct _KS_DVDCOPY_TITLEKEY {
  ULONG KeyFlags;
  ULONG ReservedNT[2];
  UCHAR TitleKey[6];
  UCHAR Reserved[2];
} KS_DVDCOPY_TITLEKEY, *PKS_DVDCOPY_TITLEKEY;
````


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
The KS_DVDCOPY_TITLEKEY structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565148">KSPROPERTY_DVDCOPY_TITLE_KEY</a> property.

For more information, see <a href="https://msdn.microsoft.com/ff9cf8c8-7c8f-485c-b2ab-7567a5eeb87b">DVD Copyright Protection</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565148">KSPROPERTY_DVDCOPY_TITLE_KEY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPY_TITLEKEY structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

