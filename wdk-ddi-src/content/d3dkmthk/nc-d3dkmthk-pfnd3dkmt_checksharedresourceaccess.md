---
UID: NC:d3dkmthk.PFND3DKMT_CHECKSHAREDRESOURCEACCESS
title: PFND3DKMT_CHECKSHAREDRESOURCEACCESS (d3dkmthk.h)
description: The D3DKMTCheckSharedResourceAccess function determines if a process can access a shared resource.
old-location: display\d3dkmtchecksharedresourceaccess.htm
ms.assetid: ca1861d3-a838-4b4a-9304-e75dcca04f0d
ms.date: 05/10/2018
keywords: ["PFND3DKMT_CHECKSHAREDRESOURCEACCESS callback function"]
ms.keywords: D3DKMTCheckSharedResourceAccess, D3DKMTCheckSharedResourceAccess callback function [Display Devices], OpenGL_Functions_b9ffd997-0bfe-47ad-a769-c2ed8148fe4b.xml, PFND3DKMT_CHECKSHAREDRESOURCEACCESS, PFND3DKMT_CHECKSHAREDRESOURCEACCESS callback, d3dkmthk/D3DKMTCheckSharedResourceAccess, display.d3dkmtchecksharedresourceaccess
f1_keywords:
 - "d3dkmthk/D3DKMTCheckSharedResourceAccess"
 - "D3DKMTCheckSharedResourceAccess"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCheckSharedResourceAccess is supported beginning with the Windows 7 operating system.
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmthk.h
api_name:
- D3DKMTCheckSharedResourceAccess
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DKMT_CHECKSHAREDRESOURCEACCESS callback function


## -description


The <b>D3DKMTCheckSharedResourceAccess</b> function determines if a process can access a shared resource. 


## -parameters




### -param Arg1

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checksharedresourceaccess">D3DKMT_CHECKSHAREDRESOURCEACCESS</a> structure that specifies parameters to determine if a process can access a shared resource. 


## -returns



<b>D3DKMTCheckSharedResourceAccess</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The shared resource can be accessed by the process.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_checksharedresourceaccess">D3DKMT_CHECKSHAREDRESOURCEACCESS</a>
 

 

