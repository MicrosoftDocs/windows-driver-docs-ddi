---
UID: NF:d3dkmthk.D3DKMTChangeSurfacePointer
title: D3DKMTChangeSurfacePointer function
author: windows-driver-content
description: The D3DKMTChangeSurfacePointer function is for system use only.
old-location: display\d3dkmtchangesurfacepointer.htm
old-project: display
ms.assetid: 3db4e04b-2707-4eb1-a249-2714304246a8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTChangeSurfacePointer, PFND3DKMT_CHANGESURFACEPOINTER, OpenGL_Functions_b34c37f3-53fc-4dd3-a73a-f21c3010e00b.xml, D3DKMTChangeSurfacePointer, display.d3dkmtchangesurfacepointer, D3DKMTChangeSurfacePointer function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMTChangeSurfacePointer
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTChangeSurfacePointer function


## -description


The <b>D3DKMTChangeSurfacePointer</b> function is for system use only.


## -syntax


````
NTSTATUS APIENTRY D3DKMTChangeSurfacePointer(
  _In_ const D3DKMT_CHANGESURFACEPOINTER *pData
);
````


## -parameters




### -param D3DKMT_CHANGESURFACEPOINTER

TBD




#### - pData [in]

For system use only.


## -returns



An opaque NTSTATUS value.




## -remarks



This function is for system use only.



