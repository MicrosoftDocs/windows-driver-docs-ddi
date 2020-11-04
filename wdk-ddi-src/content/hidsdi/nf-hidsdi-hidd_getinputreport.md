---
UID: NF:hidsdi.HidD_GetInputReport
title: HidD_GetInputReport function (hidsdi.h)
description: The HidD_GetInputReport routine returns an input reports from a top-level collection.
old-location: hid\hidd_getinputreport.htm
tech.root: hid
ms.assetid: 42e0a96b-2b0b-4d22-8c91-14457d02e9c7
ms.date: 06/19/2019
keywords: ["HidD_GetInputReport function"]
ms.keywords: HidD_GetInputReport, HidD_GetInputReport routine [Human Input Devices], hid.hidd_getinputreport, hidfunc_fdcd7a5b-6623-419f-abdf-de19370ee793.xml, hidsdi/HidD_GetInputReport
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_GetInputReport
 - hidsdi/HidD_GetInputReport
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetInputReport
---

# HidD_GetInputReport function

## -description

The **HidD_GetInputReport** routine returns an input reports from a [top-level collection](/windows-hardware/drivers/hid/top-level-collections).

## -parameters

### -param HidDeviceObject

[in]
 Specifies an open handle to a top-level collection.

### -param ReportBuffer

[out]
Pointer to a caller-allocated input report buffer that the caller uses to specify a HID report ID and **HidD_GetInputReport** uses to return the specified input report. 

For more information about this parameter, see the Remarks section.

### -param ReportBufferLength

[in]
Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the input report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

## -returns

**HidD_GetInputReport** returns **TRUE** if it succeeds; otherwise, it returns **FALSE**. Use [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) to get extended error information.

## -remarks

Before it calls the **HidD_GetInputReport** routine, the caller must do the following:

- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) includes report IDs, the caller must set the first byte of the *ReportBuffer* parameter to a nonzero report ID.
- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) does not include report IDs, the caller must set the first byte of the *ReportBuffer* parameter to zero.

The input report is returned in the *ReportBuffer*  parameter. Depending on the report ID, the caller parses the report by calling one of the following functions:

- [HidP_GetButtonCaps](../hidpi/nf-hidpi-hidp_getbuttoncaps.md)
- [HidP_GetData](../hidpi/nf-hidpi-hidp_getdata.md)
- [HidP_GetExtendedAttributes](../hidpi/nf-hidpi-hidp_getextendedattributes.md)
- [HidP_GetScaledUsageValue](../hidpi/nf-hidpi-hidp_getscaledusagevalue.md)
- [HidP_GetSpecificButtonCaps](../hidpi/nf-hidpi-hidp_getspecificbuttoncaps.md)
- [HidP_GetSpecificValueCaps](../hidpi/nf-hidpi-hidp_getspecificvaluecaps.md)
- [HidP_GetUsages](../hidpi/nf-hidpi-hidp_getusages.md)
- [HidP_GetUsagesEx](../hidpi/nf-hidpi-hidp_getusagesex.md)
- [HidP_GetUsageValue](../hidpi/nf-hidpi-hidp_getusagevalue.md)
- [HidP_GetUsageValueArray](../hidpi/nf-hidpi-hidp_getusagevaluearray.md)
- [HidP_GetValueCaps](../hidpi/nf-hidpi-hidp_getvaluecaps.md)

For an example of how to parse a HID report, see the [HClient](/samples/microsoft/windows-driver-samples/hclient-sample-application/)sample application.

Only user-mode applications can call **HidD_GetInputReport**. Kernel-mode drivers can use an [IOCTL_HID_GET_INPUT_REPORT](../hidclass/ni-hidclass-ioctl_hid_get_input_report.md)request.

For more information, see [Interpreting HID Reports](/windows-hardware/drivers/hid/interpreting-hid-reports).

## -see-also

[HidD_GetFeature](./nf-hidsdi-hidd_getfeature.md)

[HidD_SetFeature](./nf-hidsdi-hidd_setfeature.md)

[HidD_SetOutputReport](./nf-hidsdi-hidd_setoutputreport.md)

[IOCTL_HID_GET_FEATURE](../hidclass/ni-hidclass-ioctl_hid_get_feature.md)

[IOCTL_HID_GET_INPUT_REPORT](../hidclass/ni-hidclass-ioctl_hid_get_input_report.md)

[IOCTL_HID_SET_FEATURE](../hidclass/ni-hidclass-ioctl_hid_set_feature.md)

[IOCTL_HID_SET_OUTPUT_REPORT](../hidclass/ni-hidclass-ioctl_hid_set_output_report.md)