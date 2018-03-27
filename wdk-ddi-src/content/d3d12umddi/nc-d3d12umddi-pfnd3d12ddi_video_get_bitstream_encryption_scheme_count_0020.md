---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
author: windows-driver-content
description: The pfnGetBitstreamEncryptionSchemeCount callback function retrieves the number of encryption schemes supported for a decode profile.
old-location: display\pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count.htm
old-project: display
ms.assetid: BD3DFB48-9470-45CC-93BC-A918FD43DC3F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020, d3d12umddi/pfnGetBitstreamEncryptionSchemeCount, display.pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count, pfnGetBitstreamEncryptionSchemeCount, pfnGetBitstreamEncryptionSchemeCount callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnGetBitstreamEncryptionSchemeCount
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback


## -description


The <i>pfnGetBitstreamEncryptionSchemeCount</i> callback function retrieves the number of encryption schemes supported for a decode profile.


## -parameters




### -param Arg1


### -param NodeIndex

The physical adapter of the device to which this operation applies.


### -param DecodeProfile

The decode profile GUID to retrieve the count of supported encryption GUIDs.


#### - hDrvDevice

The handle of the device.


## -returns



This function retrieves the number of encryption schemes supported for a decode profile.



