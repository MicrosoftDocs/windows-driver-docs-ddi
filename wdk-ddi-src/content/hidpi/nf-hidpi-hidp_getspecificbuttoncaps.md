---
UID: NF:hidpi.HidP_GetSpecificButtonCaps
title: HidP_GetSpecificButtonCaps function (hidpi.h)
description: The HidP_GetSpecificButtonCaps routine returns a button capability array that describes all HID control buttons in a top-level collection that meet a specified selection criteria.
old-location: hid\hidp_getspecificbuttoncaps.htm
tech.root: hid
ms.assetid: 923693a2-cb46-4f74-bb1b-cd7bb07014e8
ms.date: 04/30/2018
keywords: ["HidP_GetSpecificButtonCaps function"]
ms.keywords: HidP_GetSpecificButtonCaps, HidP_GetSpecificButtonCaps routine [Human Input Devices], hid.hidp_getspecificbuttoncaps, hidfunc_dd31da1d-fb42-4ac9-a15e-4c6585785c20.xml, hidpi/HidP_GetSpecificButtonCaps
f1_keywords:
 - "hidpi/HidP_GetSpecificButtonCaps"
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
- HidP_GetSpecificButtonCaps
product:
- Windows
targetos: Windows
req.typenames: 
---

# HidP_GetSpecificButtonCaps function


## -description


The <b>HidP_GetSpecificButtonCaps</b> routine returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/button-capability-arrays">button capability array</a> that describes all HID control buttons in a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a> that meet a specified selection criteria.


## -parameters




### -param ReportType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that identifies the report type.


### -param UsagePage [in]

Specifies a usage page as a search criteria. If <i>UsagePage</i> is nonzero, only buttons that specify this usage page are returned.


### -param LinkCollection [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/link-collections">link collection</a> as a search criteria. If <i>LinkCollection</i> is nonzero, only buttons that are part of this link collection are returned.


### -param Usage [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-usages">HID usage</a> as a search criteria. If <i>Usage</i> is nonzero, only buttons that specify this usage will be returned.


### -param ButtonCaps [out]

Pointer to a caller-allocated buffer in which the routine returns a button capability array for the specified report type.


### -param ButtonCapsLength [in, out]

Specifies the length on input, in array elements, of the buffer provided at <i>ButtonCaps</i>. On output, this parameter is set to the number of elements that the routine actually returned.


### -param PreparsedData [in]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.


## -returns



<b>HidP_GetSpecificButtonCaps</b> returns one of the following status values:

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



The required size of the <i>ButtonCaps</i> array is specified by the <b>Number</b><i>Xxx</i><b>ButtonCaps </b>members of a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_caps">HIDP_CAPS</a> structure.

When calling <b>HidP_GetSpecificButtonCaps</b>, specifying zero for <i>UsagePage</i>, <i>Usage</i>, and <i>LinkCollection</i> is equivalent to calling <b>HidP_GetButtonCaps</b>.

For more information about a collection's capability, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/obtaining-collection-information">Obtaining Collection Information</a>.

See also <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_button_caps">HIDP_BUTTON_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getbuttoncaps">HidP_GetButtonCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getcaps">HidP_GetCaps</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
 

 

