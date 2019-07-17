---
UID: NF:hidpi.HidP_GetSpecificValueCaps
title: HidP_GetSpecificValueCaps function (hidpi.h)
description: The HidP_GetSpecificValueCaps routine returns a value capability array that describes all HID control values that meet a specified selection criteria.
old-location: hid\hidp_getspecificvaluecaps.htm
tech.root: hid
ms.assetid: 0860733c-d28c-4916-a743-d5f6256cfca0
ms.date: 04/30/2018
ms.keywords: HidP_GetSpecificValueCaps, HidP_GetSpecificValueCaps routine [Human Input Devices], hid.hidp_getspecificvaluecaps, hidfunc_627cf175-fa12-4082-9d13-8ec454be4a74.xml, hidpi/HidP_GetSpecificValueCaps
ms.topic: function
f1_keywords:
 - "hidpi/HidP_GetSpecificValueCaps"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hidparse.lib
- Hidparse.dll
api_name:
- HidP_GetSpecificValueCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetSpecificValueCaps function


## -description


The <b>HidP_GetSpecificValueCaps</b> routine returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/value-capability-arrays">value capability array</a> that describes all HID control values that meet a specified selection criteria.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param UsagePage [in]

Specifies a usage page as a search criteria. If <i>UsagePage</i> is nonzero, only values that specify this usage page are returned.


### -param LinkCollection [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a> as a search criteria. If <i>LinkCollection</i> is nonzero, only values that are part of this link collection are returned.


### -param Usage [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">HID usage</a> as a search criteria. If <i>Usage</i> is nonzero, only values that specify this usage will be returned.


### -param ValueCaps [out]

Pointer to a caller-allocated buffer in which the routine returns a value capability array for the specified report type.


### -param ValueCapsLength [in, out]

Specifies the length on input, in array elements, of the buffer provided at <i>ValueCaps</i>. On output, this parameter is set to the number of elements that routine actually returns.


### -param PreparsedData [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


## -returns



<b>HidP_GetSpecificValueCaps</b> returns one of the following status values:

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
The routine successfully returned the capability data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HIDP_STATUS_INVALID_PREPARSED_DATA</b></dt>
</dl>
</td>
<td width="60%">
The preparsed data is not valid.

</td>
</tr>
</table>
 




## -remarks



The required size of the <i>ValueCaps</i> buffer is specified by the <b>Number</b><i>Xxx</i><b>ValueCaps </b>members of a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.

When calling <b>HidP_GetSpecificValueCaps</b>, specifying zero for <i>UsagePage</i>, <i>Usage</i>, and <i>LinkCollection</i> is equivalent to calling <b>HidP_GetValueCaps</b>.

For more information about a collection's capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/obtaining-collection-information">Obtaining Collection Information</a>.

See also <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/ns-hidpi-_hidp_value_caps">HIDP_VALUE_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidpi/nf-hidpi-hidp_getvaluecaps">HidP_GetValueCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

