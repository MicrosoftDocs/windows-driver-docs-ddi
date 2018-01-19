---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPLCONTEXTSCOUNT
title: _D3DKMT_OUTPUTDUPLCONTEXTSCOUNT
author: windows-driver-content
description: Specifies the number of current Desktop Duplication API (DDA) clients that are attached to a given video present network (VidPN).
old-location: display\d3dkmt_outputduplcontextscount.htm
old-project: display
ms.assetid: db63b984-73da-4b66-8a5e-06704dd7c031
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_OUTPUTDUPLCONTEXTSCOUNT, D3DKMT_OUTPUTDUPLCONTEXTSCOUNT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_OUTPUTDUPLCONTEXTSCOUNT
req.alt-loc: D3dkmthk.h
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
req.typenames: D3DKMT_OUTPUTDUPLCONTEXTSCOUNT
---

# _D3DKMT_OUTPUTDUPLCONTEXTSCOUNT structure



## -description
Specifies the number of current <a href="https://msdn.microsoft.com/523FBFAD-5D78-4EE3-A3B7-8FD5BA39DC46">Desktop Duplication API</a> (DDA) clients that are attached to a given video present network (VidPN).



## -syntax

````
typedef struct _D3DKMT_OUTPUTDUPLCONTEXTSCOUNT {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           OutputDuplicationCount;
} D3DKMT_OUTPUTDUPLCONTEXTSCOUNT;
````


## -struct-fields

### -field VidPnSourceId

The ID of the video present network (VidPN).


### -field OutputDuplicationCount

The number of current DDA clients that are attached to the VidPN specified by the <b>VidPnSourceId</b> member.


## -remarks
