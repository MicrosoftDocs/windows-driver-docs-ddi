---
UID: NF:hidsdi.HidD_SetOutputReport
title: HidD_SetOutputReport function (hidsdi.h)
description: The HidD_SetOutputReport routine sends an output report to a top-level collection.
old-location: hid\hidd_setoutputreport.htm
tech.root: hid
ms.date: 04/28/2022
keywords: ["HidD_SetOutputReport function"]
ms.keywords: HidD_SetOutputReport, HidD_SetOutputReport routine [Human Input Devices], hid.hidd_setoutputreport, hidfunc_eb711fe9-fdf1-4757-90c1-6c4e115f3805.xml, hidsdi/HidD_SetOutputReport
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
 - HidD_SetOutputReport
 - hidsdi/HidD_SetOutputReport
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_SetOutputReport
---

# HidD_SetOutputReport function

## -description

The **HidD_SetOutputReport** routine sends an output report to a [top-level collection](/windows-hardware/drivers/hid/top-level-collections).

## -parameters

### -param HidDeviceObject [in]

An open handle to a top-level collection.

### -param ReportBuffer [in]

Pointer to a caller-allocated output report buffer that the caller uses to specify a report ID.

For more information about this parameter, see the [Remarks](#remarks) section.

### -param ReportBufferLength [in]

The size of the report buffer in bytes. The report buffer must be large enough to hold the output report plus one additional byte that specifies a nonzero report ID. If report ID is not used, the ID value is zero.

## -returns

If **HidD_SetOutputReport** succeeds, it returns **TRUE**; otherwise, it returns **FALSE**. Use **[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)** to get extended error information.

## -remarks

The correct _ReportBufferLength_ is specified by the _OutputReportByteLength_ member of a top-level collection's [HIDP_CAPS](../hidpi/ns-hidpi-_hidp_caps.md) structure returned from [HidP_GetCaps](../hidpi/nf-hidpi-hidp_getcaps.md) call.

Before it calls the **HidD_SetOutputReport** routine, the caller must do the following:

- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) includes report IDs, the caller must set the first byte of the *ReportBuffer* parameter to a nonzero report ID.
- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) does not include report IDs, the caller must set the first byte of the *ReportBuffer* parameter to zero.
- The output report is referenced by the *ReportBuffer* parameter. Depending on the report ID, the caller prepares the report by calling one of the following functions:
    - [HidP_SetData](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setdata)
    - [HidP_SetScaledUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setscaledusagevalue)
    - [HidP_SetUsages](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusages)
    - [HidP_SetUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevalue)
    - [HidP_SetUsageValueArray](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevaluearray)

For an example of how to prepare and a HID report and send it to a [top-level collection](/windows-hardware/drivers/hid/top-level-collections), see the [HClient](/samples/microsoft/windows-driver-samples/hclient-sample-application/) sample application.

Only user-mode applications can call **HidD_SetOutputReport**. Kernel-mode drivers can use an [IOCTL_HID_SET_OUTPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report) request.

## -see-also

- [Sending HID Reports](/windows-hardware/drivers/hid/sending-hid-reports)
- [Interpreting HID Reports](/windows-hardware/drivers/hid/interpreting-hid-reports)
- [HidD_GetFeature](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getfeature)
- [HidD_GetInputReport](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getinputreport)
- [HidD_SetFeature](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setfeature)
- [HIDP_CAPS](../hidpi/ns-hidpi-_hidp_caps.md)
- [HidP_GetCaps](../hidpi/nf-hidpi-hidp_getcaps.md)
- [IOCTL_HID_GET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature)
- [IOCTL_HID_GET_INPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report)
- [IOCTL_HID_SET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature)
- [IOCTL_HID_SET_OUTPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report)
