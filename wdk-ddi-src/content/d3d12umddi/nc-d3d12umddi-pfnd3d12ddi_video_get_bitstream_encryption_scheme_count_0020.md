---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020
author: windows-driver-content
description: The pfnGetBitstreamEncryptionSchemeCount callback function retrieves the number of encryption schemes supported for a decode profile.
old-location: display\pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count.htm
old-project: display
ms.assetid: BD3DFB48-9470-45CC-93BC-A918FD43DC3F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_video_get_decode_bitstream_encryption_scheme_count, pfnGetBitstreamEncryptionSchemeCount callback function [Display Devices], pfnGetBitstreamEncryptionSchemeCount, PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020, PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020, d3d12umddi/pfnGetBitstreamEncryptionSchemeCount
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d12umddi.h
apiname:
-	pfnGetBitstreamEncryptionSchemeCount
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 callback


## -description


The <i>pfnGetBitstreamEncryptionSchemeCount</i> callback function retrieves the number of encryption schemes supported for a decode profile.


## -prototype


````
PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 pfnGetBitstreamEncryptionSchemeCount;

UINT APIENTRY* pfnGetBitstreamEncryptionSchemeCount(
   D3D12DDI_HDEVICE hDrvDevice,
   UINT             NodeIndex,
   REFGUID          DecodeProfile
)
{ ... }
````


## -parameters




### -param D3D12DDI_HDEVICE



### -param NodeIndex

The physical adapter of the device to which this operation applies.


### -param DecodeProfile

The decode profile GUID to retrieve the count of supported encryption GUIDs.


#### - hDrvDevice

The handle of the device.


## -returns


This function retrieves the number of encryption schemes supported for a decode profile.


