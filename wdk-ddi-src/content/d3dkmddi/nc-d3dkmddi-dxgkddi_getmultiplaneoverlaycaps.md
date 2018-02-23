---
UID: NC:d3dkmddi.DXGKDDI_GETMULTIPLANEOVERLAYCAPS
title: DXGKDDI_GETMULTIPLANEOVERLAYCAPS
author: windows-driver-content
description: Called to retrieve multiplane overlay capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support multiple planes.
old-location: display\dxgkddi_getmultiplaneoverlaycaps.htm
old-project: display
ms.assetid: 17A9B769-D280-491D-844E-A9B2C66D2207
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.dxgkddi_getmultiplaneoverlaycaps, DXGKDDI_GETMULTIPLANEOVERLAYCAPS callback function [Display Devices], DXGKDDI_GETMULTIPLANEOVERLAYCAPS, d3dkmddi/DXGKDDI_GETMULTIPLANEOVERLAYCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKDDI_GETMULTIPLANEOVERLAYCAPS
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_GETMULTIPLANEOVERLAYCAPS callback


## -description


Called to retrieve multiplane overlay capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support multiple planes. 


## -prototype


````
NTSTATUS APIENTRY DXGKDDI_GETMULTIPLANEOVERLAYCAPS(
  _In_ const HANDLE                            hAdapter,
  _In_ const PDXGKARG_GETMULTIPLANEOVERLAYCAPS pGetMultiPlaneOverlayCaps
);
````


## -parameters




### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.


### -param pGetMultiPlaneOverlayCaps [in]

A pointer to a DXGKARG_GETMULTIPLANEOVERLAYCAPS structure that receives the driver capabilities.


## -returns



DXGKDDI_GETMULTIPLANEOVERLAYCAPS returns the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
If the routine has been successfully completed.

</td>
</tr>
</table>
 




## -remarks



This function is called at PASSIVE_LEVEL.

The multiplane overlay capabilities are allowed to change due to display configuration changes.

For WDDM 2.2 drivers, this DDI is used to retrieve the multiplane overlay capabilities rather than the user mode DDIs. 




