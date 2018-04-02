---
UID: NC:d3dkmddi.DXGKCB_QUERYMONITORINTERFACE
title: DXGKCB_QUERYMONITORINTERFACE
author: windows-driver-content
description: The DxgkCbQueryMonitorInterface function returns a pointer to a DXGK_MONITOR_INTERFACE structure.
old-location: display\dxgkcbquerymonitorinterface.htm
old-project: display
ms.assetid: 0c23e72d-3eb9-4511-a386-1dcc2f4910b7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKCB_QUERYMONITORINTERFACE, DpFunctions_6d1b7fa2-c5ab-4fd0-8a60-740c5415777c.xml, DxgkCbQueryMonitorInterface, DxgkCbQueryMonitorInterface callback function [Display Devices], d3dkmddi/DxgkCbQueryMonitorInterface, display.dxgkcbquerymonitorinterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: Dispmprt.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkCbQueryMonitorInterface
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_QUERYMONITORINTERFACE callback


## -description


The <b>DxgkCbQueryMonitorInterface</b> function returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561949">DXGK_MONITOR_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to obtain other interfaces that provide access to monitor descriptors, modes, and frequency ranges.


## -parameters




### -param hAdapter [in]

[in] A handle that represents a display adapter. The VidPN manager provided this handle to the display miniport driver in a call to <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a>, <a href="https://msdn.microsoft.com/96e96366-6306-4d20-8752-e942f2ed4069">DxgkDdiIsSupportedVidPn</a>, <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>, or <a href="https://msdn.microsoft.com/979b86e9-f3ff-4022-8c00-b6afc2b1f747">DxgkDdiCommitVidPn</a>.


### -param MonitorInterfaceVersion [in]

[in] A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561979">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that specifies the version of the monitor interface being requested.


### -param ppMonitorInterface [out]

[out] A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561949">DXGK_MONITOR_INTERFACE</a> structure.


## -returns



<b>DxgkCbQueryMonitorInterface</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.</i>h. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor Interface</a>
 

 

