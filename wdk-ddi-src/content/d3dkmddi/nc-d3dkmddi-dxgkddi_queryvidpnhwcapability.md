---
UID: NC:d3dkmddi.DXGKDDI_QUERYVIDPNHWCAPABILITY
title: DXGKDDI_QUERYVIDPNHWCAPABILITY
author: windows-driver-content
description: The DxgkDdiQueryVidPnHWCapability function requests that the display miniport driver report the capabilities of the hardware on a functional VidPn path.
old-location: display\dxgkddiqueryvidpnhwcapability.htm
old-project: display
ms.assetid: 41af9528-4497-41aa-a65d-70352aa85f8c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiqueryvidpnhwcapability, DxgkDdiQueryVidPnHWCapability callback function [Display Devices], DxgkDdiQueryVidPnHWCapability, DXGKDDI_QUERYVIDPNHWCAPABILITY, DXGKDDI_QUERYVIDPNHWCAPABILITY, d3dkmddi/DxgkDdiQueryVidPnHWCapability, DmFunctions_2e9dffd4-d8af-49f9-86d4-7a67e18df2dc.xml
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	d3dkmddi.h
apiname: 
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERYVIDPNHWCAPABILITY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

