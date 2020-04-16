---
UID: NS:d3dkmddi._DXGKARG_QUERYENGINESTATUS
title: _DXGKARG_QUERYENGINESTATUS (d3dkmddi.h)
description: Used in a call to the DxgkDdiQueryEngineStatus function to specify a node within an active physical adapter (engine) that is to be queried for its progress.
old-location: display\dxgkarg_queryenginestatus.htm
ms.assetid: f7255c97-5c25-4ee2-988b-ff301878fe7c
ms.date: 05/10/2018
keywords: ["_DXGKARG_QUERYENGINESTATUS structure"]
ms.keywords: "*INOUT_PDXGKARG_QUERYENGINESTATUS, DXGKARG_QUERYENGINESTATUS, DXGKARG_QUERYENGINESTATUS structure [Display Devices], _DXGKARG_QUERYENGINESTATUS, d3dkmddi/DXGKARG_QUERYENGINESTATUS, display.dxgkarg_queryenginestatus"
f1_keywords:
 - "d3dkmddi/DXGKARG_QUERYENGINESTATUS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- DXGKARG_QUERYENGINESTATUS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_QUERYENGINESTATUS
---

# _DXGKARG_QUERYENGINESTATUS structure


## -description


Used in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryenginestatus">DxgkDdiQueryEngineStatus</a> function to specify a node within an active physical adapter (engine) that is to be queried for its progress.


## -struct-fields




### -field NodeOrdinal

[in] An index of a node within the physical adapter defined by   the <b>EngineOrdinal</b> member that is being queried in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryenginestatus">DxgkDdiQueryEngineStatus</a>.


### -field EngineOrdinal

[in] An index that defines the physical adapter in a linked display adapter (LDA) configuration that the node defined by <b>NodeOrdinal</b> belongs to.


### -field EngineStatus

[out] The progress, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_enginestatus">DXGK_ENGINESTATUS</a>, of the node and physical adapter that are specified by the <b>NodeOrdinal</b> and <b>EngineOrdinal</b> members.


## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_enginestatus">DXGK_ENGINESTATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryenginestatus">DxgkDdiQueryEngineStatus</a>
 

 

