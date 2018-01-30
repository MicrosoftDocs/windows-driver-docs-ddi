---
UID: NC:d3dkmddi.DXGKDDI_CONTROLINTERRUPT
title: DXGKDDI_CONTROLINTERRUPT
author: windows-driver-content
description: The DxgkDdiControlInterrupt function enables or disables the given interrupt type on the graphics hardware.
old-location: display\dxgkddicontrolinterrupt.htm
old-project: display
ms.assetid: d6bef242-bafc-4d9e-a729-d62ccdbd2667
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddicontrolinterrupt, DxgkDdiControlInterrupt callback function [Display Devices], DxgkDdiControlInterrupt, DXGKDDI_CONTROLINTERRUPT, DXGKDDI_CONTROLINTERRUPT, d3dkmddi/DxgkDdiControlInterrupt, DmFunctions_a124d234-9609-4f21-a1f5-c1f4cfa65d9c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkDdiControlInterrupt
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CONTROLINTERRUPT callback


## -description


The <i>DxgkDdiControlInterrupt</i> function enables or disables the given interrupt type on the graphics hardware.


## -prototype


````
DXGKDDI_CONTROLINTERRUPT DxgkDdiControlInterrupt;

NTSTATUS APIENTRY* DxgkDdiControlInterrupt(
  _In_ const HANDLE              hAdapter,
  _In_ const DXGK_INTERRUPT_TYPE InterruptType,
  _In_       BOOLEAN             Enable
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to the adapter object for the graphics processing unit (GPU). The driver returned this handle in the <i>MiniportDeviceContext</i> parameter from a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param InterruptType [in]

[in] A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>-type value that supplies the interrupt type.


### -param EnableInterrupt






#### - Enable [in]

[in] A Boolean value that indicates whether <i>DxgkDdiControlInterrupt</i> enables or disables the specified interrupt type. <b>TRUE</b> indicates that it enables and <b>FALSE</b> indicates that it disables.


## -returns


<i>DxgkDdiControlInterrupt</i> returns one of the following values:
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
The interrupt type was successfully enabled or disabled on the graphics hardware.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
<i>DxgkDdiControlInterrupt</i> does not support enabling or disabling the specified interrupt type.

</td>
</tr>
</table> 



## -remarks


The display miniport driver's <i>DxgkDdiControlInterrupt</i> function can enable or disable the specified interrupt type. However, <i>DxgkDdiControlInterrupt</i> is not required to disable the interrupt type if the driver requires the interrupt type for an internal purpose. A call to <i>DxgkDdiControlInterrupt</i> to enable the specified interrupt type indicates that the operating system requires that the driver call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function to report when the interrupt type is triggered on the graphics hardware.

Currently, the Microsoft DirectX graphics kernel subsystem specifies only the DXGK_INTERRUPT_CRTC_VSYNC interrupt type in the <i>InterruptType</i> parameter. A call to <i>DxgkDdiControlInterrupt</i> to enable the DXGK_INTERRUPT_CRTC_VSYNC interrupt type indicates for the driver to control vertical retrace interrupt. During every vertical retrace period and immediately after the primary surface address specified in the DAC register is latched and scanned out, the interrupt should be triggered and reported. 

The driver must return STATUS_NOT_IMPLEMENTED if an interrupt type other than DXGK_INTERRUPT_CRTC_VSYNC is supplied.

<i>DxgkDdiControlInterrupt</i> should be made pageable.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CONTROLINTERRUPT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

