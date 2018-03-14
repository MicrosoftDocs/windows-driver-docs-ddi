---
UID: NS:d3dkmthk._D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE
title: "_D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE"
author: windows-driver-content
description: Indicates an escape type that is to be activated or deactivated.
old-location: display\d3dkmt_activate_specific_diag_escape.htm
old-project: display
ms.assetid: e3c61b33-2e10-42cf-b9e8-fe70a43573e8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE, D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE structure [Display Devices], _D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE, d3dkmthk/D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE, display.d3dkmt_activate_specific_diag_escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
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
-	D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE
product: Windows
targetos: Windows
req.typenames: D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE
---

# _D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE structure


## -description


Indicates an escape type that is to be activated or deactivated.


## -syntax


````
typedef struct _D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE {
  D3DKMT_ESCAPETYPE Type;
  BOOL              Activate;
} D3DKMT_ACTIVATE_SPECIFIC_DIAG_ESCAPE;
````


## -struct-fields




### -field Type

The <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_escape.md">D3DKMT_ESCAPETYPE</a> escape type  that needs to be activated or deactivated.


### -field Activate

If <b>TRUE</b>, the escape type is to be activated. If <b>FALSE</b>, the escape type is to be deactivated.


## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_escape.md">D3DKMT_ESCAPETYPE</a>



 

 


