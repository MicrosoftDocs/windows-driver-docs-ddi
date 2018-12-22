---
UID: NS:d3dkmthk._D3DKMT_OUTPUTDUPLPRESENTFLAGS
title: "_D3DKMT_OUTPUTDUPLPRESENTFLAGS"
description: Describes options for a Desktop Duplication API swapchain present operation.
old-location: display\d3dkmt_outputduplpresentflags.htm
ms.assetid: d80bcf24-4d53-4ec9-897d-d3243c7fda25
ms.date: 05/10/2018
ms.keywords: D3DKMT_OUTPUTDUPLPRESENTFLAGS, D3DKMT_OUTPUTDUPLPRESENTFLAGS structure [Display Devices], _D3DKMT_OUTPUTDUPLPRESENTFLAGS, d3dkmthk/D3DKMT_OUTPUTDUPLPRESENTFLAGS, display.d3dkmt_outputduplpresentflags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_OUTPUTDUPLPRESENTFLAGS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OUTPUTDUPLPRESENTFLAGS
---

# _D3DKMT_OUTPUTDUPLPRESENTFLAGS structure


## -description


Describes options for a <a href="https://msdn.microsoft.com/523FBFAD-5D78-4EE3-A3B7-8FD5BA39DC46">Desktop Duplication API</a> swapchain present operation.


## -struct-fields




### -field ProtectedContentBlankedOut

Specifies whether the desktop image might contain protected content that was already blanked out (black) in the desktop image.

<b>TRUE</b> if protected content was already blanked out; otherwise, <b>FALSE</b>.

The application can use this information to notify the remote user that some of the desktop content might be protected and therefore not visible.


### -field RemoteSession

Specifies if the present operation is directed to a remote session

<b>TRUE</b> if the present operation is directed to a remote session; otherwise, <b>FALSE</b>.

If <b>TRUE</b>, the present operation will go through a GDI path.


### -field FullScreenPresent

Specifies if the present operation is to the full screen.

<b>TRUE</b> if the present operation is to the full screen; otherwise, <b>FALSE</b>.


### -field PresentIndirect

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.




### -field Value

A 32-bit value that identifies the DDA present options.

