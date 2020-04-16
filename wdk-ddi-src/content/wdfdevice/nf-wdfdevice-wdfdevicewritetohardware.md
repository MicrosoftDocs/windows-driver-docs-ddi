---
UID: NF:wdfdevice.WdfDeviceWriteToHardware
title: WdfDeviceWriteToHardware function (wdfdevice.h)
description: The WdfDeviceWriteToHardware method is used internally by the framework. Do not use.
old-location: wdf\wdfdevicewritetohardware.htm
tech.root: wdf
ms.assetid: D79F1D98-E326-4401-86B8-2C3D071DF27C
ms.date: 02/26/2018
keywords: ["WdfDeviceWriteToHardware function"]
ms.keywords: PFN_WDFDEVICEWRITETOHARDWARE, WdfDeviceWriteToHardware, WdfDeviceWriteToHardware method, wdf.wdfdevicewritetohardware, wdfdevice/WdfDeviceWriteToHardware, wdfhwaccess/WdfDeviceWriteToHardware
f1_keywords:
 - "wdfdevice/WdfDeviceWriteToHardware"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceWriteToHardware
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceWriteToHardware function


## -description


The <b>WdfDeviceWriteToHardware</b> method is used internally by the framework. Do not use.

Instead, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfhwaccess/">WDF Register/Port Access Functions</a>.


## -parameters




### -param Device [in]


### -param Type [in]


### -param Size [in]


### -param TargetAddress [in]


### -param Value [in]


### -param Buffer [in, optional]


### -param Count [in, optional]


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-writetohardware">WriteToHardware</a>
 

 

