---
UID: NC:dispmprt.DXGKDDI_QUERY_INTERFACE
title: DXGKDDI_QUERY_INTERFACE
author: windows-driver-content
description: The DxgkDdiQueryInterface function returns a functional interface that is implemented by the display miniport driver.
old-location: display\dxgkddiqueryinterface.htm
old-project: display
ms.assetid: d8255f36-be3a-4b19-ac8d-8748ac9b6a24
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_QUERY_INTERFACE, DmFunctions_1c8cdcd5-60e2-4d76-ba70-6af3f96f1740.xml, DxgkDdiQueryInterface, DxgkDdiQueryInterface callback function [Display Devices], display.dxgkddiqueryinterface, dispmprt/DxgkDdiQueryInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiQueryInterface
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_QUERY_INTERFACE callback


## -description


The <i>DxgkDdiQueryInterface</i> function returns a functional interface that is implemented by the display miniport driver.


## -prototype


````
DXGKDDI_QUERY_INTERFACE DxgkDdiQueryInterface;

NTSTATUS DxgkDdiQueryInterface(
  _In_ const PVOID            MiniportDeviceContext,
  _In_       PQUERY_INTERFACE QueryInterface
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param QueryInterface [in]

A pointer to a <a href="..\video\ns-video-_query_interface.md">QUERY_INTERFACE</a> structure in which the display miniport driver should return information about the interface it supports.


## -returns



<i>DxgkDdiQueryInterface </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>. If a display miniport driver does not support the requested interface, it must return STATUS_NOT_SUPPORTED. By returning STATUS_NOT_SUPPORTED, the display miniport driver informs the operating system to pass the query on to the next driver.




## -remarks



<i>DxgkDdiQueryInterface</i> exposes a communication mechanism between the display miniport driver and the driver of a child device (for example, a video capture device). A display miniport driver that exposes such a mechanism should implement this function.

<i>DxgkDdiQueryInterface</i> should fill in the members of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure that <i>QueryInterface</i>-&gt;<b>Interface</b> points to as follows:

<ul>
<li>
Set <b>Size</b> to the number of bytes in the INTERFACE structure. This value must not exceed the number of bytes specified by <i>QueryInterface</i>-&gt;<b>Size</b>.

</li>
<li>
Set <b>Version</b> to the version of the interface being returned by the display miniport driver. The display miniport driver should best match the version requested by the child driver in <i>QueryInterface</i>-&gt;<b>Version</b>.

</li>
<li>
Set <b>Context</b> to point to a display miniport driver-defined context for the interface. Typically, a display miniport driver would set <b>Context</b> to the handle to the display adapter's context block that is identified by <i>MiniportDeviceContext</i>.

</li>
<li>
Initialize <b>InterfaceReference</b> and <b>InterfaceDereference</b> to point to the display miniport driver-implemented reference and dereference routines for this interface.

</li>
<li>
Initialize all additional interface-specific members to point to the appropriate routines of the interface being exposed.

</li>
</ul>
<i>DxgkDdiQueryInterface</i> runs at IRQL = PASSIVE_LEVEL and should be made pageable.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\video\ns-video-_query_interface.md">QUERY_INTERFACE</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERY_INTERFACE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

