---
UID: NI:ntddscsi.IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
title: IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
author: windows-driver-content
description: IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO is the system-defined signature used in conjunction with the IOCTL_SCSI_MINIPORT control code to request that a miniport return endurance data for a target device.
tech.root: storage
ms.assetid: 0ba827cf-f3ad-497a-b36a-171be267db39
ms.author: windowsdriverdev
ms.date: 03/07/2019
ms.topic: ioctl
f1_keywords:
 - "ntddscsi/IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO"
req.header: ntddscsi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.max-support:
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - ntddscsi.h
api_name: 
 - IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO
product:
 - Windows
targetos: Windows
ms.custom: 19H1
---

# IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO SIGNATURE

## -description

IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO is the system-defined signature used in conjunction with the [IOCTL_SCSI_MINIPORT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_miniport) control code to request that a miniport return a target device's endurance information.

## -remarks

For this signature, IOCTL_SCSI_MINIPORT's input buffer will contain a [SRB_IO_CONTROL](ns-ntddscsi-_srb_io_control.md) structure with:

* The **Signature** member is set to IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO

* The **ControlCode** member is set to [IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property)

If the miniport recognizes and supports the IOCTL_MINIPORT_SIGNATURE_ENDURANCE_INFO signature, it should return its device's endurance data in a [STORAGE_ENDURANCE_DATA_DESCRIPTOR](ns-ntddscsi-storage_endurance_data_descriptor.md) structure. Specifically, IOCTL_SCSI_MINIPORT's output buffer will contain an SRB_IO_CONTROL structure, followed immediately by a STORAGE_ENDURANCE_DATA_DESCRIPTOR structure that contains the endurance data.

## -see-also

[IOCTL_SCSI_MINIPORT](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddscsi/ni-ntddscsi-ioctl_scsi_miniport)

[IOCTL_STORAGE_QUERY_PROPERTY](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property)

[STORAGE_ENDURANCE_DATA_DESCRIPTOR](ns-ntddscsi-storage_endurance_data_descriptor.md)
