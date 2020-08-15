---
UID: NC:hidclass.PHIDP_GETCAPS
title: PHIDP_GETCAPS (hidclass.h)
description: The HidP_GetCaps routine returns a top-level collection's HIDP_CAPS structure.
old-location: hid\hidp_getcaps.htm
tech.root: hid
ms.assetid: a43baab5-26d9-43f7-bc13-3b0864769e68
ms.date: 04/30/2018
keywords: ["PHIDP_GETCAPS callback function"]
ms.keywords: HidP_GetCaps, HidP_GetCaps callback function [Human Input Devices], PHIDP_GETCAPS, PHIDP_GETCAPS callback, hid.hidp_getcaps, hidfunc_420188e5-e357-43cc-b195-dea7637fd3c9.xml, hidpi/HidP_GetCaps
f1_keywords:
 - "hidclass/HidP_GetCaps"
 - "HidP_GetCaps"
req.header: hidclass.h
req.include-header: Hidclass.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- hidpi.h
api_name:
- HidP_GetCaps
targetos: Windows
req.typenames: 
---

# PHIDP_GETCAPS callback function


## -description


The <b>HidP_GetCaps</b> routine returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.


## -parameters




### -param PreparsedData 
[in]
Pointer to a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


### -param Capabilities 
[out]
Pointer to a caller-allocated buffer that the routine uses to return a collection's HIDP_CAPS structure.


## -returns



<b>HidP_GetCaps</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_SUCCESS </b></dt>
</dl>
</td>
<td width="60%">
The routine successfully returned the collection capability information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The specified preparsed data is invalid.

</td>
</tr>
</table>
 




## -remarks



For more information about a collection's capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/obtaining-collection-information">Obtaining Collection Information</a>.

See also <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">HidD_GetPreparsedData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_collection_descriptor">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_collection_information">IOCTL_HID_GET_COLLECTION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

