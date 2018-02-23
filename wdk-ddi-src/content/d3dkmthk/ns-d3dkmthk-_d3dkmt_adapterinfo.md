---
UID: NS:d3dkmthk._D3DKMT_ADAPTERINFO
title: "_D3DKMT_ADAPTERINFO"
author: windows-driver-content
description: Supplies configuration information about a graphics adapter.
old-location: display\d3dkmt_adapterinfo.htm
old-project: display
ms.assetid: 4b780fb7-f6d4-4248-882c-d0cc96106724
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.d3dkmt_adapterinfo, D3DKMT_ADAPTERINFO, d3dkmthk/D3DKMT_ADAPTERINFO, _D3DKMT_ADAPTERINFO, D3DKMT_ADAPTERINFO structure [Display Devices]
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
-	D3DKMT_ADAPTERINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_ADAPTERINFO
---

# _D3DKMT_ADAPTERINFO structure


## -description


Supplies configuration information about a graphics adapter.


## -syntax


````
typedef struct _D3DKMT_ADAPTERINFO {
  D3DKMT_HANDLE hAdapter;
  LUID          AdapterLuid;
  ULONG         NumOfSources;
  BOOL          bPresentMoveRegionsPreferred;
} D3DKMT_ADAPTERINFO;
````


## -struct-fields




### -field hAdapter

A handle to the adapter.


### -field AdapterLuid

A LUID that serves as an identifier for the adapter.


### -field NumOfSources

The number of video present sources supported by the adapter.


### -field bPresentMoveRegionsPreferred

If <b>TRUE</b>, the adapter prefers move regions.

