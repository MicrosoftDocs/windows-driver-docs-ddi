---
UID: NF:hidpi.HidP_MaxDataListLength
title: HidP_MaxDataListLength function (hidpi.h)
description: The HidP_MaxDataListLength routine returns the maximum number of HIDP_DATA structures that HidP_GetData can return for a specified type of HID report and a specified top-level collection.
old-location: hid\hidp_maxdatalistlength.htm
tech.root: hid
ms.date: 04/30/2018
keywords: ["HidP_MaxDataListLength function"]
ms.keywords: HidP_MaxDataListLength, HidP_MaxDataListLength routine [Human Input Devices], hid.hidp_maxdatalistlength, hidfunc_2c103c6f-6177-47b3-9d52-9e15c97d758d.xml, hidpi/HidP_MaxDataListLength
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
 - HidP_MaxDataListLength
 - hidpi/HidP_MaxDataListLength
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Hidparse.lib
 - Hidparse.dll
api_name:
 - HidP_MaxDataListLength
---

# HidP_MaxDataListLength function


## -description

The <b>HidP_MaxDataListLength</b> routine returns the maximum number of <a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_data">HIDP_DATA</a> structures that <a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getdata">HidP_GetData</a> can return for a specified type of HID report and a specified <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>.

## -parameters

### -param ReportType [in]


Specifies a <a href="/windows-hardware/drivers/ddi/hidpi/ne-hidpi-_hidp_report_type">HIDP_REPORT_TYPE</a> enumerator value that indicates the report type.

### -param PreparsedData [in]


Pointer to a top-level collection's <a href="/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.

## -returns

If successful, <b>HidP_MaxDataListLength</b> returns the maximum number of <a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_data">HIDP_DATA</a> structures that <a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getdata">HidP_GetData</a> might return for a specified type of HID report and a specified <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>. Otherwise, the routine returns zero, which indicates that either the report type or the preparsed data is not valid.

## -remarks

User-mode applications or kernel-mode drivers call <b>HidP_MaxDataListLength</b> to determine the maximum number of  <a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_data">HIDP_DATA</a> structures that <b>HidP_GetData</b> can return.

For more information, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/hidpi/ns-hidpi-_hidp_data">HIDP_DATA</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getdata">HidP_GetData</a>



<a href="/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setdata">HidP_SetData</a>



<a href="/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">_HIDP_PREPARSED_DATA</a>
