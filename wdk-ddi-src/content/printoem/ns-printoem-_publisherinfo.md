---
UID: NS:printoem._PUBLISHERINFO
title: PUBLISHERINFO (printoem.h)
description: The PUBLISHERINFO structure is used as an input parameter to the IPrintOemPS::GetInfo method.
tech.root: print
ms.date: 08/12/2022
keywords: ["PUBLISHERINFO structure"]
ms.keywords: "*PPUBLISHERINFO, PPUBLISHERINFO, PPUBLISHERINFO structure pointer [Print Devices], PUBLISHERINFO, PUBLISHERINFO structure [Print Devices], _PUBLISHERINFO, print.publisherinfo, print_unidrv-pscript_rendering_dbd3e74a-00bd-4c21-80e5-80b788f83bb2.xml, printoem/PPUBLISHERINFO, printoem/PUBLISHERINFO"
req.header: printoem.h
req.include-header: Printoem.h
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
req.typenames: PUBLISHERINFO, *PPUBLISHERINFO
f1_keywords:
 - _PUBLISHERINFO
 - printoem/_PUBLISHERINFO
 - PPUBLISHERINFO
 - printoem/PPUBLISHERINFO
 - PUBLISHERINFO
 - printoem/PUBLISHERINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _PUBLISHERINFO
 - PPUBLISHERINFO
 - PUBLISHERINFO
---

## -description

The **PUBLISHERINFO** structure is used as an input parameter to the [IPrintOemPS::GetInfo](../prcomoem/nf-prcomoem-iprintoemps-getinfo.md) method.

## -struct-fields

### -field dwMode

Is a set of bit flags. The only flag defined is **OEM_MODE_PUBLISHER**, which must be set if a rendering plug-in for Pscript5 is using "publishing mode".

### -field wMinoutlinePPEM

Specifies the minimum font size, in pixels, for which the Pscript5 driver will download TrueType fonts as outline (Type 1) fonts. A font smaller than the minimum setting will be downloaded as a bitmap (Type 3) font.

### -field wMaxbitmapPPEM

Specifies the maximum font size, in pixels, for which the Pscript5 driver will download TrueType fonts as bitmap (Type 3) fonts. A font larger than the maximum setting will be downloaded as an outline (Type 1) font.

## -see-also

[IPrintOemPS::GetInfo](../prcomoem/nf-prcomoem-iprintoemps-getinfo.md)