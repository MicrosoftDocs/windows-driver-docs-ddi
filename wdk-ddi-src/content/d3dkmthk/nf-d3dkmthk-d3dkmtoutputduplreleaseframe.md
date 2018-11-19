---
UID: NF:d3dkmthk.D3DKMTOutputDuplReleaseFrame
title: D3DKMTOutputDuplReleaseFrame function
author: windows-driver-content
description: Indicates that the driver has finished processing the duplicated desktop image.
old-location: display\d3dkmtoutputduplreleaseframe.htm
ms.assetid: 07bbc201-0320-4f26-be0a-27c06763813f
ms.date: 05/10/2018
ms.keywords: D3DKMTOutputDuplReleaseFrame, D3DKMTOutputDuplReleaseFrame callback function [Display Devices], PFND3DKMT_OUTPUTDUPLRELEASEFRAME, PFND3DKMT_OUTPUTDUPLRELEASEFRAME callback, d3dkmthk/D3DKMTOutputDuplReleaseFrame, display.d3dkmtoutputduplreleaseframe
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib 
req.dll: Gdi32.dll 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
api_name:
-	D3DKMTOutputDuplReleaseFrame
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOutputDuplReleaseFrame function

## -description

Indicates that the driver has finished processing the duplicated desktop image.

## -parameters

### -param Arg1

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406533">D3DKMT_OUTPUTDUPL_RELEASE_FRAME</a> structure that defines the duplicated desktop image that is to be released.

## -returns

Returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function performed successfully.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
|STATUS_NOT_FOUND|The context of the process could not be found.|
 
This function might also return other NTSTATUS values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406533">D3DKMT_OUTPUTDUPL_RELEASE_FRAME</a>
