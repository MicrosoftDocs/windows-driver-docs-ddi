---
UID: NI:hidclass.IOCTL_HID_GET_INPUT_REPORT
title: IOCTL_HID_GET_INPUT_REPORT (hidclass.h)
description: The IOCTL_HID_GET_INPUT_REPORT request obtains an input report from a top-level collection.
old-location: hid\ioctl_hid_get_input_report2.htm
tech.root: hid
ms.date: 04/28/2022
keywords: ["IOCTL_HID_GET_INPUT_REPORT IOCTL"]
ms.keywords: IOCTL_HID_GET_INPUT_REPORT, IOCTL_HID_GET_INPUT_REPORT control, IOCTL_HID_GET_INPUT_REPORT control code [Human Input Devices], hid.ioctl_hid_get_input_report2, hidclass/IOCTL_HID_GET_INPUT_REPORT, hidioreq_d9b80227-8a48-439e-80de-3b0e722e3576.xml
req.header: hidclass.h
req.include-header: Hidclass.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_HID_GET_INPUT_REPORT
 - hidclass/IOCTL_HID_GET_INPUT_REPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidclass.h
api_name:
 - IOCTL_HID_GET_INPUT_REPORT
---

# IOCTL_HID_GET_INPUT_REPORT IOCTL

## -description

The IOCTL_HID_GET_INPUT_REPORT request obtains an input report from a [top-level collection](/windows-hardware/drivers/hid/top-level-collections).

For general information about HIDClass devices, see [HID Collections](/windows-hardware/drivers/hid/hid-collections).

## -ioctlparameters

### -input-buffer

The `Parameters.DeviceIoControl.OutputBufferLength` member specifies the size of a requester-allocated output buffer in bytes. The HID class driver uses this buffer to return an input report.

If the collection includes report IDs, the requester must set the first byte of the output buffer to a nonzero report ID. Otherwise, the requester must set the first byte of the output buffer to zero.

**Minidriver handling**

`Irp->UserBuffer` points to a [HID_XFER_PACKET](/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_xfer_packet) structure that the HID class driver uses to input the following members:

### -input-buffer-length

The size of the buffer in bytes. The buffer must be large enough to hold the input report plus one additional byte that specifies a nonzero report ID. If report ID is not used, the ID value is zero.

### -output-buffer

The `Irp->MdlAddress` member points to the requester-allocated output buffer that the HID class driver uses to return the input report. The first byte of the buffer, which the requester uses to input a report ID or zero, is unchanged. The input report -- excluding its report ID, if report IDs are used -- is returned at `((PUCHAR)Irp->MdlAddress + 1)`.

**Minidriver handling**

`((PHID_XFER_PACKET)(Irp->UserBuffer))->reportBuffer` points to the requester-allocated output buffer that the HID minidriver uses to return the input report.

### -output-buffer-length

The size of the output report.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The HID class driver sets the following fields of `Irp->IoStatus`:

- *Information* is set to zero.
- *Status* is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

**Minidriver handling**

HID minidrivers that carry out the I/O to the device set the following fields of `Irp->IoStatus`:

- *Information* is set to the number of bytes transferred from the device.
- *Status* is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

HID minidrivers that call other drivers with this IOCTL to carry out the I/O to their device, should ensure that the *Information* field of the status block is correct and not change the contents of the *Status* field.

## -ReportID

Specifies a report ID associated with a top-level collection.

## -reportBuffer

Points to a requester-allocated output buffer that a HID minidriver uses to return an input report.

## -reportBufferLen

Specifies the size, in bytes, of the output buffer.

## -see-also

- [HidD_GetFeature](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getfeature)
- [HidD_GetInputReport](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getinputreport)
- [HidD_SetFeature](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setfeature)
- [HidD_SetOutputReport](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setoutputreport)
- [IOCTL_HID_GET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature)
- [IOCTL_HID_SET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature)
- [IOCTL_HID_SET_OUTPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report)
