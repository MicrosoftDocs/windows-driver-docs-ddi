---
UID: NS:d3dkmddi._DXGK_ENGINESTATUS
title: _DXGK_ENGINESTATUS (d3dkmddi.h)
description: Indicates the progress of a node within an active physical display adapter (engine) specified by a DXGKARG_QUERYENGINESTATUS structure.
old-location: display\dxgk_enginestatus.htm
ms.assetid: e052e3bc-688e-4aa8-b987-88ed6963774a
ms.date: 05/10/2018
ms.keywords: DXGK_ENGINESTATUS, DXGK_ENGINESTATUS structure [Display Devices], _DXGK_ENGINESTATUS, d3dkmddi/DXGK_ENGINESTATUS, display.dxgk_enginestatus
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	D3dkmddi.h
api_name:
-	DXGK_ENGINESTATUS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_ENGINESTATUS
---

# _DXGK_ENGINESTATUS structure


## -description


Indicates the progress of a node within an active physical display adapter (engine) specified by a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451299">DXGKARG_QUERYENGINESTATUS</a> structure.


## -struct-fields




### -field Responsive

The display miniport driver must set this member to a value of 1 if the node and physical adapter are making progress in operations, or to 0 if the node and physical adapter are not responding to queries to report progress.


### -field Reserved

This member is reserved and should be set to zero.


### -field Value

A 32-bit value that specifies the progress of the physical adapter.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451299">DXGKARG_QUERYENGINESTATUS</a>
 

 

