---
UID: NS:ksmedia._KS_DVDCOPY_TITLEKEY
title: _KS_DVDCOPY_TITLEKEY (ksmedia.h)
description: The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process.
tech.root: stream
ms.date: 03/10/2023
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
 - _KS_DVDCOPY_TITLEKEY
 - PKS_DVDCOPY_TITLEKEY
 - KS_DVDCOPY_TITLEKEY
---

## -description

The KS_DVDCOPY_TITLEKEY structure is used to describe the title key information for the DVD copyright protection authentication process.

## -struct-fields

### -field KeyFlags

Title key flags settings that provide Copyrighted Material flag (CPM), Copy Guard Management System (CGMS) and Copyright Protection System (CP_SEC) copyright protection flags from the DVD drive. The following CGMS flags are defined:

| Flag | Meaning |
|---|---|
| KS_DVD_CGMS_RESERVED_MASK | Specifies the mask of all defined CPM, CGMS and CP_SEC flags (that is, all the other flags listed here). |
| KS_DVD_CGMS_COPY_PROTECT_MASK | Specifies the mask of all defined CGMS flags. |
| KS_DVD_CGMS_COPY_PERMITTED | Indicates that the content protected by CGMS can be copied. |
| KS_DVD_CGMS_COPY_ONCE | Indicates that the content protected by CGMS can be copied only a single time. As part of the copy process, this flag should be cleared, and the KS_DVD_CGMS_NO_COPY flags must be set to prevent subsequent copying. |
| KS_DVD_CGMS_NO_COPY | Indicates that the content protected by CGMS cannot be copied. |
| KS_DVD_COPYRIGHT_MASK | Specifies the mask of all defined CPM flags (KS_DVD_NOT_COPYRIGHTED and KS_DVD_COPYRIGHTED). |
| KS_DVD_NOT_COPYRIGHTED | Indicates that the content marked by CPM is not copyrighted. |
| KS_DVD_COPYRIGHTED | Indicates that the content marked by CPM is copyrighted. |
| KS_DVD_SECTOR_PROTECT_MASK | The mask of all defined sector protection flags. |
| KS_DVD_SECTOR_NOT_PROTECTED | Indicates that the sector is not protected (encrypted). |
| KS_DVD_SECTOR_PROTECTED | Indicates that the sector is protected (encrypted). |

### -field ReservedNT

Reserved. Do not use.

### -field TitleKey

Specifies the current title key.

### -field Reserved

Reserved. Do not use.

## -remarks

The KS_DVDCOPY_TITLEKEY structure is used by the [KSPROPERTY_DVDCOPY_TITLE_KEY](/windows-hardware/drivers/stream/ksproperty-dvdcopy-title-key) property.

For more information, see [DVD Copyright Protection](/windows-hardware/drivers/stream/dvd-copyright-protection).

## -see-also

[KSPROPERTY_DVDCOPY_TITLE_KEY](/windows-hardware/drivers/stream/ksproperty-dvdcopy-title-key)
