---
UID: NS:d3dkmthk._D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
title: "_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE"
author: windows-driver-content
description: Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.
old-location: display\d3dkmt_opensyncobjectfromnthandle.htm
old-project: display
ms.assetid: 163ce4ed-e81b-4b69-b1a7-4ea2b9e8f437
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmt_opensyncobjectfromnthandle, D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure [Display Devices], _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE, d3dkmthk/D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
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
-	D3dkmthk.h
apiname:
-	D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENSYNCOBJECTFROMNTHANDLE
---

# _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE structure


## -description


Describes information that is required to map an NT process handle to a graphics processing unit (GPU) synchronization object.


## -syntax


````
typedef struct _D3DKMT_OPENSYNCOBJECTFROMNTHANDLE {
  HANDLE        hNtHandle;
  D3DKMT_HANDLE hSyncObject;
} D3DKMT_OPENSYNCOBJECTFROMNTHANDLE;
````


## -struct-fields




#### - hNtHandle

[in] An NT handle to the process.


#### - hSyncObject

[out] A handle of type <b>D3DKMT_HANDLE</b> that represents a kernel-mode handle to the kernel-mode synchronization object.

