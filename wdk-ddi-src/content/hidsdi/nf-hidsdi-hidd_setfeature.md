---
UID: NF:hidsdi.HidD_SetFeature
title: HidD_SetFeature function (hidsdi.h)
description: The HidD_SetFeature routine sends a feature report to a top-level collection.
old-location: hid\hidd_setfeature.htm
tech.root: hid
ms.date: 04/28/2022
keywords: ["HidD_SetFeature function"]
ms.keywords: HidD_SetFeature, HidD_SetFeature routine [Human Input Devices], hid.hidd_setfeature, hidfunc_f34ed05a-c8c1-44e3-ab94-a8df000aac7d.xml, hidsdi/HidD_SetFeature
req.header: hidsdi.h
req.include-header: Hidsdi.h
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_SetFeature
 - hidsdi/HidD_SetFeature
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_SetFeature
---

# HidD_SetFeature function

## -description

The **HidD_SetFeature** routine sends a feature report to a [top-level collection](/windows-hardware/drivers/hid/top-level-collections).

## -parameters

### -param HidDeviceObject [in]

An open handle to a top-level collection.

### -param ReportBuffer [in]

Pointer to a caller-allocated feature report buffer that the caller uses to specify a HID report ID.

For more information about this parameter, see the [Remarks](#remarks) section.

### -param ReportBufferLength [in]

The size of the report buffer in bytes. The report buffer must be large enough to hold the feature report plus one additional byte that specifies a nonzero report ID. If report ID is not used, the ID value is zero.

## -returns

If **HidD_SetFeature** succeeds, it returns **TRUE**; otherwise, it returns **FALSE**. Use **[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)** to get extended error information.

## -remarks

Before it calls the **HidD_SetFeature** routine, the caller must do the following:

- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) includes report IDs, the caller must set the first byte of the _ReportBuffer_ parameter to a nonzero report ID.
- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) does not include report IDs, the caller must set the first byte of the _ReportBuffer_ parameter to zero.
- The feature report is referenced by the _ReportBuffer_ parameter. Depending on the report ID, the caller prepares the report by calling one of the following functions:
    - [HidP_SetData](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setdata)
    - [HidP_SetScaledUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setscaledusagevalue)
    - [HidP_SetUsages](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusages)
    - [HidP_SetUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevalue)
    - [HidP_SetUsageValueArray](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_setusagevaluearray)

For an example of how to prepare and a HID report and send it to a [top-level collection](/windows-hardware/drivers/hid/top-level-collections), see the [HClient](/samples/microsoft/windows-driver-samples/hclient-sample-application/) sample application.

Only user-mode applications can call **HidD_SetFeature**. Kernel-mode drivers can use an [IOCTL_HID_SET_OUTPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report) request.

## -see-also

- [Sending HID Reports](/windows-hardware/drivers/hid/sending-hid-reports)
- [Interpreting HID Reports](/windows-hardware/drivers/hid/interpreting-hid-reports)
- [HidD_GetFeature](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getfeature)
- [HidD_GetInputReport](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getinputreport)
- [HidD_SetOutputReport](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setoutputreport)
- [IOCTL_HID_GET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature)
- [IOCTL_HID_GET_INPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report)
- [IOCTL_HID_SET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature)
- [IOCTL_HID_SET_OUTPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report)
