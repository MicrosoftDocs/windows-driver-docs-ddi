---
UID: NC:d3dkmddi.DXGKDDI_CREATEALLOCATION
title: DXGKDDI_CREATEALLOCATION
author: windows-driver-content
description: The DxgkDdiCreateAllocation function creates allocations of system or video memory.
old-location: display\dxgkddicreateallocation.htm
old-project: display
ms.assetid: a28287d6-4dfa-4db4-92df-bbcd9379a5b2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKDDI_CREATEALLOCATION, DmFunctions_fa00d14b-b5f1-4dde-8283-cc7b71911f76.xml, DxgkDdiCreateAllocation, DxgkDdiCreateAllocation callback function [Display Devices], d3dkmddi/DxgkDdiCreateAllocation, display.dxgkddicreateallocation
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
-	DxgkDdiCreateAllocation
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_CREATEALLOCATION callback


## -description


The <i>DxgkDdiCreateAllocation</i> function creates allocations of system or video memory.


## -prototype


````
DXGKDDI_CREATEALLOCATION DxgkDdiCreateAllocation;

NTSTATUS APIENTRY DxgkDdiCreateAllocation(
  _In_    const HANDLE                   hAdapter,
  _Inout_       DXGKARG_CREATEALLOCATION *pCreateAllocation
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pCreateAllocation [in, out]

[in/out] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure that contains information for creating allocations.


## -returns



<i>DxgkDdiCreateAllocation</i> returns one of the following values:

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

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> successfully created the allocation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters that were passed to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> contained errors that prevented it from completing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> could not allocate memory that was required for it to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver is not compatible with the user-mode display driver that initiated the call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>. 

</td>
</tr>
</table>
 




## -remarks



After the user-mode display driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function, the DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiCreateAllocation</i> function to create the allocations. The display miniport driver must interpret the private data (in the <b>pPrivateDriverData</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure for each allocation) that is passed from the user-mode display driver and must determine the list of parameters that are required to create each allocation through the video memory manager. For more information about how the display miniport driver supplies these parameters to the video memory manager, see <a href="https://msdn.microsoft.com/31bfbfd9-89e5-42fe-90bc-8ff54bac4f8b">Specifying Segments When Creating Allocations</a>. 

The display miniport driver must return an allocation handle, which is typically a pointer to a private driver data structure that contains information about the allocation. The display miniport driver can call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a> function anytime to retrieve the private data for an allocation handle. Therefore, the display miniport driver is not required to maintain a private allocation handle table. In fact, we strongly discourage private handle tables because they could become stale or out of sync with the DirectX graphics kernel subsystem in display-mode-switch scenarios such as fast user switch, hot unplug, and so on.

The user-mode display driver assigns an allocation to either a resource or a device. To determine whether the allocation belongs to a resource, the display miniport driver can check whether the <b>Resource</b> bit-field flag is set in the <b>Flags</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure that the <i>pCreateAllocation</i> parameter of <i>DxgkDdiCreateAllocation</i> points to. If the allocation belongs to a resource, the display miniport driver can (but is not required to) return a resource handle, which is typically a pointer to a private driver data structure that describes the resource. If the DirectX graphics kernel subsystem calls <i>DxgkDdiCreateAllocation</i> to create an additional allocation for an existing resource, the <b>hResource</b> member of DXGKARG_CREATEALLOCATION contains the handle that was returned by the previous <i>DxgkDdiCreateAllocation</i> call for that resource. If necessary, the display miniport driver can change the resource handle during a call to <i>DxgkDdiCreateAllocation</i>. 

If the user-mode display driver places a resource handle in a command buffer, the display miniport driver can retrieve the private data by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a>. The display miniport driver can also enumerate all of the resource's child allocations by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_enumhandlechildren.md">DxgkCbEnumHandleChildren</a> function.

Beginning with Windows 7, if a display miniport driver processes a call to the <i>DxgkDdiCreateAllocation</i> function to create allocations for GDI hardware acceleration, the driver should set the size of the allocation (including the pitch value for CPU visible allocations), <i>pCreateAllocation</i>-&gt;<b>pAllocationInfo</b>-&gt;<b>Size</b>.

The resources that are created in the <i>DxgkDdiCreateAllocation</i> call belong to the adapter and not to the device. The display miniport driver should not reference the device data anywhere within the private allocation and resource data structures. Because of surface sharing, a resource might be in use after the destruction of the device that the user-mode display driver created the resource from. 

<i>DxgkDdiCreateAllocation</i> should be made pageable.

<h3><a id="Allocating_history_buffers"></a><a id="allocating_history_buffers"></a><a id="ALLOCATING_HISTORY_BUFFERS"></a>Allocating history buffers</h3>
Starting in Windows 8.1, when <i>DxgkDdiCreateAllocation</i> is called, the display miniport driver can set the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfoflags.md">DXGK_ALLOCATIONINFOFLAGS</a>.<b>HistoryBuffer</b> member to indicate that the user-mode driver can manage the creation and destruction of history buffers.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfoflags.md">DXGK_ALLOCATIONINFOFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_enumhandlechildren.md">DxgkCbEnumHandleChildren</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CREATEALLOCATION callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

