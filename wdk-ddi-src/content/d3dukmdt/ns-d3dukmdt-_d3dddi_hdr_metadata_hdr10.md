---
UID: NS:d3dukmdt._D3DDDI_HDR_METADATA_HDR10
title: "_D3DDDI_HDR_METADATA_HDR10"
author: windows-driver-content
description: Describes the metadata for HDR10.
old-location: display\d3dddi_hdr_metadata_hdr10.htm
old-project: display
ms.assetid: F7316327-C860-4138-A19B-3326CE9210C0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DDDI_HDR_METADATA_HDR10 structure [Display Devices], display.d3dddi_hdr_metadata_hdr10, D3DDDI_HDR_METADATA_HDR10, _D3DDDI_HDR_METADATA_HDR10, d3dukmdt/D3DDDI_HDR_METADATA_HDR10
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
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
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDI_HDR_METADATA_HDR10
product: Windows
targetos: Windows
req.typenames: D3DDDI_HDR_METADATA_HDR10
---

# _D3DDDI_HDR_METADATA_HDR10 structure


## -description


Describes the metadata for HDR10.


## -syntax


````
typedef struct _D3DDDI_HDR_METADATA_HDR10 {
  UINT16 RedPrimary[2];
  UINT16 GreenPrimary[2];
  UINT16 BluePrimary[2];
  UINT   MaxMasteringLuminance;
  UINT   MinMasteringLuminance;
  UINT16 MaxContentLightLevel;
  UINT16 MaxFrameAverageLightLevel;
} D3DDDI_HDR_METADATA_HDR10;
````


## -struct-fields




### -field RedPrimary

The chromaticity coordinates of the red color primary in the CIE xy color space. Index 0 contains the x coordinate and index 1 contains the y coordinate. Values are normalized to 50,000.


### -field GreenPrimary

The chromaticity coordinates of the green color primary in the CIE xy color space. Index 0 contains the x coordinate and index 1 contains the y coordinate. Values are normalized to 50,000.


### -field BluePrimary

The chromaticity coordinates of the blue color primary in the CIE xy color space. Index 0 contains the x coordinate and index 1 contains the y coordinate. Values are normalized to 50,000.


### -field WhitePoint

The chromaticity coordinates of the white point in the CIE xy color space. Index 0 contains the x coordinate and index 1 contains the y coordinate. Values are normalized to 50,000.


### -field MaxMasteringLuminance

The maximum number of nits of the display used to master the content. Values are normalized to 10,000.


### -field MinMasteringLuminance

The minimum number of nits of the display used to master the content. Values are normalized to 10,000.


### -field MaxContentLightLevel

The maximum content light level (MaxCLL). This is the nit value corresponding to the brightest pixel used anywhere in the content.


### -field MaxFrameAverageLightLevel

The maximum frame average light level (MaxFALL). This is the nit value corresponding to the average luminance of the frame which has the brightest average luminance anywhere in the content.

## -remarks

D3DDDI_HDR_METADATA_HDR10 has equivalent definitions to <a href="https://msdn.microsoft.com/library/windows/desktop/mt732700.aspx">DXGI_HDR_METADATA_HDR10</a>.
