---
UID: NS:d3dkmthk._D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
title: _D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION (d3dkmthk.h)
description: The D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure describes the shared primary surface that an application is about to lock.
old-location: display\d3dkmt_sharedprimarylocknotification.htm
ms.assetid: 4e7766bb-eb5b-4f79-b9b8-89f7dcb98569
ms.date: 05/10/2018
keywords: ["_D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure"]
ms.keywords: D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION, D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure [Display Devices], OpenGL_Structs_4ec11480-30cb-45a1-a31c-e7432ec45abf.xml, _D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION, d3dkmthk/D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION, display.d3dkmt_sharedprimarylocknotification
f1_keywords:
 - "d3dkmthk/D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
---

# _D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure


## -description


The D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure describes the shared primary surface that an application is about to lock.


## -struct-fields




### -field AdapterLuid

[in] The locally unique identifier (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>) of the graphics adapter on which the GDI shared primary surface exists. 


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which the GDI shared primary surface exists. 


### -field LockRect

[in] A <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-_rectl">RECTL</a> structure that indicates the upper-left and lower-right points of a rectangle on the shared primary surface; the operating system disables all sprites that intersect with this rectangle. If the OpenGL ICD specifies zero for each member of RECTL, the operating system disables all sprites on the shared primary surface.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsharedprimarylocknotification">D3DKMTSharedPrimaryLockNotification</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-_rectl">RECTL</a>
 

 

