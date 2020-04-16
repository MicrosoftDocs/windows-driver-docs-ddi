---
UID: NS:d3dkmddi._DXGK_GPUENGINETOPOLOGY
title: _DXGK_GPUENGINETOPOLOGY (d3dkmddi.h)
description: The DXGK_GPUENGINETOPOLOGY structure describes the graphics processing unit (GPU)-engine topology that a driver can support.
old-location: display\dxgk_gpuenginetopology.htm
ms.assetid: 8ed224eb-c1f6-4793-ae32-36f96d3af9ab
ms.date: 05/10/2018
keywords: ["_DXGK_GPUENGINETOPOLOGY structure"]
ms.keywords: DXGK_GPUENGINETOPOLOGY, DXGK_GPUENGINETOPOLOGY structure [Display Devices], DmStructs_21e5ab51-877b-4b52-9762-cbaf3e82d2f0.xml, _DXGK_GPUENGINETOPOLOGY, d3dkmddi/DXGK_GPUENGINETOPOLOGY, display.dxgk_gpuenginetopology
f1_keywords:
 - "d3dkmddi/DXGK_GPUENGINETOPOLOGY"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGK_GPUENGINETOPOLOGY
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_GPUENGINETOPOLOGY
---

# _DXGK_GPUENGINETOPOLOGY structure


## -description


The DXGK_GPUENGINETOPOLOGY structure describes the graphics processing unit (GPU)-engine topology that a driver can support.


## -struct-fields




### -field NbAsymetricProcessingNodes

[out] The number of parallel engines that the GPU supports. If the driver does not set the <b>MultiEngineAware</b> bit-field flag in the <b>SchedulingCaps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure, the Microsoft DirectX graphics kernel subsystem ignores the setting of <b>NbAsymetricProcessingNodes</b>.


### -field Reserved

[out] An array of 32-bit values that are reserved for future use. The <b>DXGK_MAX_ASYMETRICAL_PROCESSING_NODES</b> constant, which is defined as 64, indicates the maximum number of asymmetrical processing nodes that the driver can signal.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>
 

 

