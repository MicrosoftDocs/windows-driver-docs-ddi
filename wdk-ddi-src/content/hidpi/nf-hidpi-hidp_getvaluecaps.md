---
UID: NF:hidpi.HidP_GetValueCaps
title: HidP_GetValueCaps function (hidpi.h)
description: The HidP_GetValueCaps routine returns a value capability array that describes all the HID control values in a top-level collection for a specified type of HID report.
old-location: hid\hidp_getvaluecaps.htm
tech.root: hid
ms.assetid: 74c26072-3b41-4d5c-96a1-d9c5b37ed97a
ms.date: 04/30/2018
keywords: ["HidP_GetValueCaps function"]
ms.keywords: HidP_GetValueCaps, HidP_GetValueCaps routine [Human Input Devices], hid.hidp_getvaluecaps, hidfunc_e600ab99-103c-43dd-b37b-fe35a96b2482.xml, hidpi/HidP_GetValueCaps
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - HidP_GetValueCaps
 - hidpi/HidP_GetValueCaps
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hidparse.lib
 - Hidparse.dll
api_name:
 - HidP_GetValueCaps
---

# HidP_GetValueCaps function


## -description

The <b>HidP_GetValueCaps</b> routine returns a <a href="/windows-hardware/drivers/hid/value-capability-arrays">value capability array</a> that describes all the HID control values in a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> for a specified type of HID report.

## -parameters

### -param ReportType 

[in]
Specifies a <a href="/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.

### -param ValueCaps 

[out]
Pointer to a caller-allocated buffer in which the routine returns a value capability array for the specified report type.

### -param ValueCapsLength 

[in, out]
Specifies the length, on input, in array elements, of the <i>ValueCaps </i>buffer. On output, the routine sets <i>ValueCapsLength</i> to the number of elements that the it actually returns.

### -param PreparsedData 

[in]
Pointer to a top-level collection's <a href="/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.

## -returns

<b>HidP_GetValueCaps</b> returns one of the following status values:

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

The correct length for <i>ValueCapsLength</i> is specified by the <b>Number</b><i>Xxx</i><b>ValueCaps </b>members of a top-level collection's <a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.

For more information about a collection's capability, see <a href="/windows-hardware/drivers/hid/obtaining-collection-information">Obtaining Collection Information</a>.

See also <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a>



<a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_value_caps">HIDP_VALUE_CAPS</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getbuttoncaps">HidP_GetButtonCaps</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>