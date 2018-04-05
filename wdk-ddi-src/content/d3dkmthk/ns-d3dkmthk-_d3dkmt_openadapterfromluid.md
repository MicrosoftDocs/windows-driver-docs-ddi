---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMLUID
title: "_D3DKMT_OPENADAPTERFROMLUID"
author: windows-driver-content
description: Describes the mapping of the given locally unique identifier (LUID) of a device to a graphics adapter handle.
old-location: display\d3dkmt_openadapterfromluid.htm
old-project: display
ms.assetid: 93f5c1d1-e1df-4536-8b52-db3b4942488c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_OPENADAPTERFROMLUID, D3DKMT_OPENADAPTERFROMLUID structure [Display Devices], _D3DKMT_OPENADAPTERFROMLUID, d3dkmthk/D3DKMT_OPENADAPTERFROMLUID, display.d3dkmt_openadapterfromluid
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_OPENADAPTERFROMLUID
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_OPENADAPTERFROMLUID
---

# _D3DKMT_OPENADAPTERFROMLUID structure


## -description


Describes the mapping of the given locally unique identifier (LUID) of a device to a graphics adapter handle.


## -struct-fields




### -field AdapterLuid

 [in] A LUID that serves as an identifier for the device. <b>LUID</b> is defined in Dxgi.h.


### -field hAdapter

[out] A handle to the graphics adapter for the device that the <b>AdapterLuid</b> member specifies. The adapter handle is returned from a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780247">D3DKMTOpenAdapterFromLuid</a> function.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780247">D3DKMTOpenAdapterFromLuid</a>
 

 

