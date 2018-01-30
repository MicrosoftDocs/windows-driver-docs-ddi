---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMLUID
title: "_D3DKMT_OPENADAPTERFROMLUID"
author: windows-driver-content
description: Describes the mapping of the given locally unique identifier (LUID) of a device to a graphics adapter handle.
old-location: display\d3dkmt_openadapterfromluid.htm
old-project: display
ms.assetid: 93f5c1d1-e1df-4536-8b52-db3b4942488c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_OPENADAPTERFROMLUID structure [Display Devices], D3DKMT_OPENADAPTERFROMLUID, d3dkmthk/D3DKMT_OPENADAPTERFROMLUID, _D3DKMT_OPENADAPTERFROMLUID, display.d3dkmt_openadapterfromluid
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
-	D3DKMT_OPENADAPTERFROMLUID
product: Windows
targetos: Windows
req.typenames: D3DKMT_OPENADAPTERFROMLUID
---

# _D3DKMT_OPENADAPTERFROMLUID structure


## -description


Describes the mapping of the given locally unique identifier (LUID) of a device to a graphics adapter handle.


## -syntax


````
typedef struct _D3DKMT_OPENADAPTERFROMLUID {
  LUID          AdapterLuid;
  D3DKMT_HANDLE hAdapter;
} D3DKMT_OPENADAPTERFROMLUID;
````


## -struct-fields




### -field AdapterLuid

 [in] A LUID that serves as an identifier for the device. <b>LUID</b> is defined in Dxgi.h.


### -field hAdapter

[out] A handle to the graphics adapter for the device that the <b>AdapterLuid</b> member specifies. The adapter handle is returned from a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromluid.md">D3DKMTOpenAdapterFromLuid</a> function.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenadapterfromluid.md">D3DKMTOpenAdapterFromLuid</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_OPENADAPTERFROMLUID structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

