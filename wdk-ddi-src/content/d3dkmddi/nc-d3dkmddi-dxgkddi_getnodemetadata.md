---
UID: NC:d3dkmddi.DXGKDDI_GETNODEMETADATA
title: DXGKDDI_GETNODEMETADATA
author: windows-driver-content
description: From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.
old-location: display\dxgkddigetnodemetadata.htm
old-project: display
ms.assetid: ECE54E1C-5291-43AF-8A71-BD95DE5DF0A6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddigetnodemetadata, DxgkDdiGetNodeMetadata callback function [Display Devices], DxgkDdiGetNodeMetadata, DXGKDDI_GETNODEMETADATA, DXGKDDI_GETNODEMETADATA, d3dkmddi/DxgkDdiGetNodeMetadata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dkmddi.h
apiname:
-	DxgkDdiGetNodeMetadata
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_GETNODEMETADATA callback


## -description


From a provided adapter handle, returns the engine type and friendly name of an engine on a specified GPU node. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later display miniport drivers.


## -prototype


````
DXGKDDI_GETNODEMETADATA DxgkDdiGetNodeMetadata;

NTSTATUS APIENTRY DxgkDdiGetNodeMetadata(
  _In_  const HANDLE                  hAdapter,
  _In_        UINT                    NodeOrdinal,
  _Out_       DXGKARG_GETNODEMETADATA *pGetNodeMetadata
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle that identifies a display adapter. The DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param NodeOrdinalAndAdapterIndex


### -param pGetNodeMetadata [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265405">DXGKARG_GETNODEMETADATA</a> structure that contains the engine type and friendly name of the engine specified by the <i>NodeOrdinal</i> parameter.


#### - NodeOrdinal [in]

An index of a node for which engine information will be obtained. This node is within the physical adapter defined by the <i>hAdapter</i> parameter.


## -returns




      Returns one of the following values:

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

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getnodemetadata.md">DxgkDdiGetNodeMetadata</a> successfully retrieved the engine information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller-provided <i>hAdapter</i> or <i>pGetNodeMetadata</i> parameters are invalid, or the caller-provided value of <i>NodeOrdinal</i> is greater than or equal to the number of nodes on the adapter.

</td>
</tr>
</table>
 

If the <i>hAdapter</i> and <i>pGetNodeMetadata</i> parameters are valid, and <i>NodeOrdinal</i> has a value in the range of 0 to (number of nodes - 1), all calls to this function must be successful.




## -remarks



For more information on how to implement this function, see <a href="https://msdn.microsoft.com/822FEB3E-A39D-4B33-BD9D-F3166EF99AF8">Enumerating GPU engine capabilities</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265405">DXGKARG_GETNODEMETADATA</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_GETNODEMETADATA callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

