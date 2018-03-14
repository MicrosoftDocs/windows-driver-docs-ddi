---
UID: NC:d3dkmddi.DXGKDDI_QUERYVIDPNHWCAPABILITY
title: DXGKDDI_QUERYVIDPNHWCAPABILITY
author: windows-driver-content
description: The DxgkDdiQueryVidPnHWCapability function requests that the display miniport driver report the capabilities of the hardware on a functional VidPn path.
old-location: display\dxgkddiqueryvidpnhwcapability.htm
old-project: display
ms.assetid: 41af9528-4497-41aa-a65d-70352aa85f8c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_QUERYVIDPNHWCAPABILITY, DmFunctions_2e9dffd4-d8af-49f9-86d4-7a67e18df2dc.xml, DxgkDdiQueryVidPnHWCapability, DxgkDdiQueryVidPnHWCapability callback function [Display Devices], d3dkmddi/DxgkDdiQueryVidPnHWCapability, display.dxgkddiqueryvidpnhwcapability
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiQueryVidPnHWCapability
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_QUERYVIDPNHWCAPABILITY callback


## -description


The <i>DxgkDdiQueryVidPnHWCapability</i> function requests that the display miniport driver report the capabilities of the hardware on a functional VidPn path.


## -prototype


````
DXGKDDI_QUERYVIDPNHWCAPABILITY DxgkDdiQueryVidPnHWCapability;

NTSTATUS APIENTRY DxgkDdiQueryVidPnHWCapability(
  _In_    const HANDLE                         i_hAdapter,
  _Inout_       DXGKARG_QUERYVIDPNHWCAPABILITY *io_pVidPnHWCaps
)
{ ... }
````


## -parameters




### -param i_hAdapter [in]

[in] A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param io_pVidPnHWCaps [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryvidpnhwcapability.md">DXGKARG_QUERYVIDPNHWCAPABILITY</a> structure that describes the hardware capabilities of a functional VidPN.


## -returns



<i>DxgkDdiQueryVidPnHwCapability </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



For more information on how to process this function, see <a href="https://msdn.microsoft.com/fb7939bb-ff7e-4ba8-b801-ac10010c44b7">Querying VidPN Hardware Capabilities</a>.

<i>DxgkDdiQueryInterface</i> should be made pageable.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryvidpnhwcapability.md">DXGKARG_QUERYVIDPNHWCAPABILITY</a>



 

 


