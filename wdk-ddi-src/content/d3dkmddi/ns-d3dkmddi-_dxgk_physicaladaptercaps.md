---
UID: NS:d3dkmddi._DXGK_PHYSICALADAPTERCAPS
title: _DXGK_PHYSICALADAPTERCAPS
author: windows-driver-content
description: The DXGK_PHYSICALADAPTERCAPS structure is used to report details of a physical adapter.
old-location: display\dxgk_physicaladaptercaps.htm
old-project: display
ms.assetid: 8D075473-605F-4B75-BB02-5B182EEB3B5F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_PHYSICALADAPTERCAPS, Flags.MovePagingSupported, Flags.IoMmuSupported, _DXGK_PHYSICALADAPTERCAPS, d3dkmddi/DXGK_PHYSICALADAPTERCAPS, DXGK_PHYSICALADAPTERCAPS structure [Display Devices], Flags.GpuMmuSupported, display.dxgk_physicaladaptercaps, Flags.VPRPagingContextRequired
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGK_PHYSICALADAPTERCAPS
product: Windows
targetos: Windows
req.typenames: DXGK_PHYSICALADAPTERCAPS
---

# _DXGK_PHYSICALADAPTERCAPS structure


## -description


The <b>DXGK_PHYSICALADAPTERCAPS</b> structure is used to report details of a physical adapter.


## -syntax


````
typedef struct _DXGK_PHYSICALADAPTERCAPS {
  WORD                      NumExecutionNodes;
  WORD                      PagingNodeIndex;
  HANDLE                    DxgkPhysicalAdapterHandle;
  DXGK_PHYSICALADAPTERFLAGS Flags;
  UINT                      VPRPagingNode;
} DXGK_PHYSICALADAPTERCAPS;
````


## -struct-fields




### -field NumExecutionNodes

The number of execution nodes in the physical adapter.


### -field PagingNodeIndex

Index of the paging node for the physical adapter.


### -field DxgkPhysicalAdapterHandle

Handle, which is passed to the kernel mode driver as <b>DXGKRNL_INTERFACE::DeviceHandle</b> in <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>. 


### -field Flags

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="Flags.IoMmuSupported"></a><a id="flags.iommusupported"></a><a id="FLAGS.IOMMUSUPPORTED"></a><dl>
<dt><b>Flags.IoMmuSupported</b></dt>
<dt><b>TRUE</b></dt>
</dl>
</td>
<td width="60%">
The adapter supports <i>IoMmu</i>.

</td>
</tr>
<tr>
<td width="40%"><a id="Flags.GpuMmuSupported"></a><a id="flags.gpummusupported"></a><a id="FLAGS.GPUMMUSUPPORTED"></a><dl>
<dt><b>Flags.GpuMmuSupported</b></dt>
<dt><b>TRUE</b></dt>
</dl>
</td>
<td width="60%">
The adapter supports <i>GpuMmu</i>.

</td>
</tr>
<tr>
<td width="40%"><a id="Flags.MovePagingSupported"></a><a id="flags.movepagingsupported"></a><a id="FLAGS.MOVEPAGINGSUPPORTED"></a><dl>
<dt><b>Flags.MovePagingSupported</b></dt>
<dt><b>TRUE</b></dt>
</dl>
</td>
<td width="60%">
The adapter supports move paging.

</td>
</tr>
<tr>
<td width="40%"><a id="Flags.VPRPagingContextRequired"></a><a id="flags.vprpagingcontextrequired"></a><a id="FLAGS.VPRPAGINGCONTEXTREQUIRED"></a><dl>
<dt><b>Flags.VPRPagingContextRequired</b></dt>
<dt><b>TRUE</b></dt>
</dl>
</td>
<td width="60%">
The adapter requires the index of the VPR paging node.

</td>
</tr>
</table> 


### -field VPRPagingNode

Index of the node to be used for move paging in  the VPR.

