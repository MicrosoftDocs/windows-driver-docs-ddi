---
UID: NS:d3dkmddi._DXGKARG_CONTROLINTERRUPT2
title: "_DXGKARG_CONTROLINTERRUPT2"
author: windows-driver-content
description: The DXGKARG_CONTROLINTERRUPT2 structure is used in DxgkDdi_ControlInterrupt2 calls to describe the state of interrupts.
old-location: display\dxgkarg_controlinterrupt2.htm
old-project: display
ms.assetid: 881F93B2-999F-4E3A-A71D-731946E8AA97
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKARG_CONTROLINTERRUPT2, DXGKARG_CONTROLINTERRUPT2 structure [Display Devices], DXGKARG_CONTROLINTTERUPT2, DXGKARG_CONTROLINTTERUPT2 structure [Display Devices], _DXGKARG_CONTROLINTERRUPT2, d3dkmddi/DXGKARG_CONTROLINTERRUPT2, display.dxgkarg_controlinterrupt2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later versions of the Windows operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_CONTROLINTTERUPT2
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_CONTROLINTERRUPT2
---

# _DXGKARG_CONTROLINTERRUPT2 structure


## -description


The DXGKARG_CONTROLINTERRUPT2 structure is used in <a href="https://msdn.microsoft.com/library/windows/hardware/mt667971">DxgkDdi_ControlInterrupt2</a> calls to describe the state of interrupts. 


## -struct-fields




### -field InterruptType

 


### -field InterruptState

Indicates whether  interrupts are enabled for the driver.


### -field CrtcVsyncState

Indicates whether VSYNCs are enabled if interrupts are also enabled for the driver.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt667971">DxgkDdi_ControlInterrupt2</a>
 

 

