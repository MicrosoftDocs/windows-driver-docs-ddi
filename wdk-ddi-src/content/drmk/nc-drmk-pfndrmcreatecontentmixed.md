---
UID: NC:drmk.PFNDRMCREATECONTENTMIXED
title: PFNDRMCREATECONTENTMIXED
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmcreatecontentmixed.htm
old-project: audio
ms.assetid: A4BA818F-126F-4134-AEDA-F983ADFC4A07
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.pfndrmcreatecontentmixed, DRMCreateContentMixed callback function [Audio Devices], DRMCreateContentMixed, PFNDRMCREATECONTENTMIXED, PFNDRMCREATECONTENTMIXED, drmk/DRMCreateContentMixed, DRMCreateContentMixed callback function [Audio Devices], DRMCreateContentMixed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: drmk.h
req.include-header: 
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
-	UserDefined
apilocation:
-	Drmk.h
apiname:
-	DRMCreateContentMixed
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---

# PFNDRMCREATECONTENTMIXED callback


## -description


This callback function is reserved for system use.


## -prototype


````
PFNDRMCREATECONTENTMIXED DRMCreateContentMixed;

NTSTATUS DRMCreateContentMixed(
  _In_  PULONG paContentId,
  _In_  ULONG  cContentId,
  _Out_ PULONG pMixedContentId
)
{ ... }

typedef PFNDRMCREATECONTENTMIXED DRMCreateContentMixed;
````


## -parameters




#### - paContentId [in]

This parameter is reserved for system use.


#### - cContentId [in]

This parameter is reserved for system use.


#### - pMixedContentId [out]

This parameter is reserved for system use.


## -returns


This return value is reserved for system use.


