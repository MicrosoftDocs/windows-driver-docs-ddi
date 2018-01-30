---
UID: NC:dispmprt.DXGKDDI_QUERY_CHILD_STATUS
title: DXGKDDI_QUERY_CHILD_STATUS
author: windows-driver-content
description: The DxgkDdiQueryChildStatus function returns the status of an individual child device of a display adapter.
old-location: display\dxgkddiquerychildstatus.htm
old-project: display
ms.assetid: 478e0c52-4324-4062-8e1e-381808b0f481
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddiquerychildstatus, DxgkDdiQueryChildStatus callback function [Display Devices], DxgkDdiQueryChildStatus, DXGKDDI_QUERY_CHILD_STATUS, DXGKDDI_QUERY_CHILD_STATUS, dispmprt/DxgkDdiQueryChildStatus, DmFunctions_3da69961-14d3-4bf8-9427-9c47d9bbfb89.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkDdiQueryChildStatus
product: Windows
targetos: Windows
req.typenames: "*PSYMBOL_INFO_EX, SYMBOL_INFO_EX"
---

# DXGKDDI_QUERY_CHILD_STATUS callback


## -description


The <i>DxgkDdiQueryChildStatus</i> function returns the status of an individual child device of a display adapter.


## -prototype


````
DXGKDDI_QUERY_CHILD_STATUS DxgkDdiQueryChildStatus;

NTSTATUS* DxgkDdiQueryChildStatus(
  _In_    const PVOID              MiniportDeviceContext,
  _Inout_       PDXGK_CHILD_STATUS ChildStatus,
  _In_          BOOLEAN            NonDestructiveOnly
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ChildStatus [in, out]

A pointer to a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_status.md">DXGK_CHILD_STATUS</a> structure. The caller supplies ChildStatus-&gt;Type and ChildStatus-&gt;ChildUid. On return, the remaining structure member (a union) receives the requested status.


### -param NonDestructiveOnly [in]

A BOOLEAN value that specifies whether the display miniport driver is permitted to determine the requested status in a way that causes visual artifacts. If the caller sets this parameter to <b>TRUE</b>, then the display miniport driver is not permitted to cause artifacts. If the caller sets this parameter to <b>FALSE</b>, then the display miniport driver is permitted to cause artifacts.


## -returns


<i>DxgkDdiQueryChildStatus </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.



## -remarks


During initialization, the display port driver calls <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> to get a list of devices that are children of the display adapter represented by <i>MiniportDeviceContext</i>. Then for each child that has an HPD awareness value of <b>HpdAwarenessPolled</b> or <b>HpdAwarenessInterruptible</b>, the display port driver calls <i>DxgkDdiQueryChildStatus</i> to determine whether the child currently has hardware (for example a monitor) connected to it.

<i>DxgkDdiQueryChildStatus</i> must perform the following actions:
<ul>
<li>
If ChildStatus-&gt;Type is equal to <b>StatusConnection</b>, return a Boolean value in ChildStatus-&gt;HotPlug.Connected. Return <b>TRUE</b> if the child device identified by ChildStatus-&gt;ChildUid has external hardware connected to it; otherwise return <b>FALSE</b>.

</li>
<li>
If ChildStatus-&gt;Type is equal to <b>StatusRotation</b>, return (in ChildStatus-&gt;Rotation.Angle) the angle of rotation for the display connected to the child device identified by ChildStatus-&gt;ChildUid.

</li>
</ul><i>DxgkDdiQueryChildStatus</i> should be made pageable.



## -see-also

<a href="..\dispmprt\ns-dispmprt-_dxgk_child_status.md">DXGK_CHILD_STATUS</a>

<a href="..\dispmprt\ne-dispmprt-_dxgk_child_status_type.md">DXGK_CHILD_STATUS_TYPE</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_QUERY_CHILD_STATUS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

