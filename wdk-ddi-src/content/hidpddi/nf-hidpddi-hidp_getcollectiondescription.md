---
UID: NF:hidpddi.HidP_GetCollectionDescription
title: HidP_GetCollectionDescription function (hidpddi.h)
description: Fills a device description block with collection description and the corresponding report ID information for the specified report descriptor.
old-location: hid\hidp_getcollectiondescription.htm
tech.root: hid
ms.assetid: F8FD0C10-115D-4ACF-8C7F-127D342EA9CD
ms.date: 04/30/2018
ms.keywords: HidP_GetCollectionDescription, HidP_GetCollectionDescription function [Human Input Devices], hid.hidp_getcollectiondescription, hidpddi/HidP_GetCollectionDescription
ms.topic: function
req.header: hidpddi.h
req.include-header: Hidpddi.h
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
- HidP_GetCollectionDescription
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetCollectionDescription function


## -description


Fills a device description
    block with collection description and the corresponding 
    report ID information for the specified report descriptor. 
    A HID minidriver generally does not need to call this function. Instead, it returns the report descriptor to Hidclass driver in response to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541147">IOCTL_HID_GET_REPORT_DESCRIPTOR</a>.


## -parameters




### -param ReportDesc [in]

A pointer to a UCHAR array that contains the raw report descriptor.


### -param DescLength [in]

The length of the report descriptor array.


### -param PoolType [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>-value that indicates the pool type from which memory for the linked list is allocated. This includes each <a href="https://msdn.microsoft.com/library/windows/hardware/mt740161">HIDP_COLLECTION_DESC</a> array element of <a href="https://msdn.microsoft.com/library/windows/hardware/mt740162">HIDP_DEVICE_DESC</a>, each <a href="https://msdn.microsoft.com/library/windows/hardware/ff539679">HIDP_PREPARSED_DATA</a> in each <b>HIDP_COLLECTION_DESC</b>, each <a href="https://msdn.microsoft.com/library/windows/hardware/mt740165">HIDP_REPORT_IDS</a> array element of <b>HIDP_DEVICE_DESC</b>.


### -param DeviceDescription [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt740162">HIDP_DEVICE_DESC</a> structure that is populated with device description block filled in
                         collection descriptors as linked lists. This is a caller-allocated structure. However, its <a href="https://msdn.microsoft.com/library/windows/hardware/mt740161">HIDP_COLLECTION_DESC</a> array elements and <a href="https://msdn.microsoft.com/library/windows/hardware/mt740165">HIDP_REPORT_IDS</a> array elements are allocated by this function.


## -returns



<b>HidP_GetCollectionDescription</b> can return one of these values: <b>TRUE</b> if it successfully fills the device description block. Otherwise, it returns <b>FALSE</b>.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>
</td>
<td width="60%">
Successfully parsed
                                      the report descriptor and allocated the
                                      memory blocks necessary to describe the
                                      device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_NO_DATA_DETECTED</dt>
</dl>
</td>
<td width="60%">
Failed to find top-level collections
                                      in the report descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_COULD_NOT_INTERPRET       </dt>
</dl>
</td>
<td width="60%">
An error was detected in the report 
                                      descriptor. See the error code in
                                      <b>Dbg</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt740162">HIDP_DEVICE_DESC</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_BUFFER_TOO_SMALL</dt>
</dl>
</td>
<td width="60%">
Found the end of the report descriptor
                                      when it expected more data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>
</td>
<td width="60%">
Failed to allocate memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_ILLEGAL_INSTRUCTION</dt>
</dl>
</td>
<td width="60%">
Failed to parse an an item in the report 
                                      descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt> HIDP_STATUS_INVALID_REPORT_TYPE</dt>
</dl>
</td>
<td width="60%">
Report ID of 0 was found in the
                                      descriptor.

</td>
</tr>
</table>
 




## -remarks



    For a raw report descriptor that is specified by the <i>ReportDesc</i> parameter, <i>HidP_GetCollectionDescription</i> fills in the <i>DeviceDescription</i>
    block with a caller-allocated linked list of collection descriptors and the corresponding 
    Report ID information that is described by the given report descriptor. 
    The memory for the collection information and the ReportID information is
    allocated based on the <i>PoolType</i> value.




