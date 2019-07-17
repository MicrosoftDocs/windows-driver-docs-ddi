---
UID: NF:hidpi.HidP_GetLinkCollectionNodes
title: HidP_GetLinkCollectionNodes function (hidpi.h)
description: The HidP_GetLinkCollectionNodes routine returns a top-level collection's link collection array.
old-location: hid\hidp_getlinkcollectionnodes.htm
tech.root: hid
ms.assetid: d829b203-8b7f-4504-a9ac-da1f91b3bbd6
ms.date: 04/30/2018
ms.keywords: HidP_GetLinkCollectionNodes, HidP_GetLinkCollectionNodes routine [Human Input Devices], hid.hidp_getlinkcollectionnodes, hidfunc_cbcd531f-dc4d-4a27-96bd-bfa3589af9a7.xml, hidpi/HidP_GetLinkCollectionNodes
ms.topic: function
f1_keywords:
 - "hidpi/HidP_GetLinkCollectionNodes"
req.header: hidpi.h
req.include-header: Hidpi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hidparse.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_GetLinkCollectionNodes
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetLinkCollectionNodes function


## -description


The <b>HidP_GetLinkCollectionNodes</b> routine returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection array</a>.


## -parameters




### -param LinkCollectionNodes [out]

Pointer to a caller-allocated array of HIDP_LINK_COLLECTION_NODE structures in which <b>HidP_GetLinkCollectionNodes</b> returns a top-level collection's link collection array.


### -param LinkCollectionNodesLength [in, out]

Specifies, on input, the length, in array elements, of the <i>LinkCollectionNodes</i> buffer. On output, the routine sets <i>LinkCollectionNodesLength</i> to the number of entries in the array that it set.


### -param PreparsedData [in]

Pointer to the preparsed data of the top-level collection for which this routine returns a link collection array.


## -returns



<b>HidP_GetLinkCollectionNodes</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine successfully returned the specified collection's link collection array.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_BUFFER_TOO_SMALL </b></dt>
</dl>
</td>
<td width="60%">
The <i>LinkCollectionNodes</i> buffer is too small to hold the entire link collection array.

</td>
</tr>
</table>
 




## -remarks



The required length of the <i>LinkCollectionNodes</i> buffer is specified by the <b>NumberLinkCollectionNodes</b> member of a collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.

If <b>HidP_GetLinkCollectionNodes</b> returns the status value HIDP_STATUS_BUFFER_TOO_SMALL, it also sets <i>LinkCollectionNodesLength</i> to the length, in array elements, required to hold the link collection nodes information.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_link_collection_node">HIDP_LINK_COLLECTION_NODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

