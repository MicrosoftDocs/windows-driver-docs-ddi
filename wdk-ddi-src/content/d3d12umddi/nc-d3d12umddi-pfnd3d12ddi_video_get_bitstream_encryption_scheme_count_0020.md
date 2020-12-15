---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 (d3d12umddi.h)
description: The pfnGetBitstreamEncryptionSchemeCount callback function retrieves the number of encryption schemes supported for a decode profile.
old-location: display\pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count.htm
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback function"]
ms.keywords: PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020, PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback, d3d12umddi/pfnGetBitstreamEncryptionSchemeCount, display.pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count, pfnGetBitstreamEncryptionSchemeCount, pfnGetBitstreamEncryptionSchemeCount callback function [Display Devices]
f1_keywords:
 - "d3d12umddi/pfnGetBitstreamEncryptionSchemeCount"
 - "pfnGetBitstreamEncryptionSchemeCount"
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
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
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnGetBitstreamEncryptionSchemeCount
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback function


## -description


The <i>pfnGetBitstreamEncryptionSchemeCount</i> callback function retrieves the number of encryption schemes supported for a decode profile.


## -parameters




### -param Arg1

A handle to the display device (graphics context).

### -param NodeIndex

The physical adapter of the device to which this operation applies.


### -param DecodeProfile

The decode profile GUID to retrieve the count of supported encryption GUIDs.




## -returns



This function retrieves the number of encryption schemes supported for a decode profile.



