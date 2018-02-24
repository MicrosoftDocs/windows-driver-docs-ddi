---
UID: NC:d3dkmddi.DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS
title: DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS
author: windows-driver-content
description: The pfnGetNumDescriptors function returns the number of descriptors in a monitor descriptor set.
old-location: display\dxgk_monitordescriptorset_interface_pfngetnumdescriptors.htm
old-project: display
ms.assetid: 7bfcef0b-1371-4e3b-b5dc-c4c548625c8f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_monitordescriptorset_interface_pfngetnumdescriptors, pfnGetNumDescriptors callback function [Display Devices], pfnGetNumDescriptors, DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS, DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS, d3dkmddi/pfnGetNumDescriptors, VidPnFunctions_c2c4ad34-be07-4bd8-8576-e91b4549ca95.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	pfnGetNumDescriptors
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS callback


## -description


The <b>pfnGetNumDescriptors</b> function returns the number of descriptors in a monitor descriptor set.


## -prototype


````
DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS pfnGetNumDescriptors;

NTSTATUS APIENTRY pfnGetNumDescriptors(
  _In_  const D3DKMDT_HMONITORDESCRIPTORSET hMonitorDescriptorSet,
  _Out_       SIZE_T CONST                  *pNumMonitorDescriptors
)
{ ... }
````


## -parameters




### -param hMonitorDescriptorSet [in]

[in] A handle to a monitor descriptor set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset.md">pfnGetMonitorDescriptorSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor interface</a>.


### -param pNumMonitorDescriptors [out]

[out] A SIZE_T-typed variable that receives the number of descriptors in the set.


## -returns



The <b>pfnGetNumDescriptors</b> function returns one of the following values.

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_MONITOR_DESCRIPTORSET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hMonitorDescriptorSet</i> was invalid.

</td>
</tr>
</table>
 



