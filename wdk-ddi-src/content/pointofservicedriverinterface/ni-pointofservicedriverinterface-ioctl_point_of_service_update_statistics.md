---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
title: IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS (pointofservicedriverinterface.h)
description: This I/O control function sets the specified statistic to the value in the input buffer.
old-location: pos\ioctl_point_of_service_update_statistics.htm
tech.root: pos
ms.assetid: 94c8d49a-5136-49f3-a313-74c032502f1f
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS, IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS control, IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS, pos.ioctl_point_of_service_update_statistics
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS"
 - "IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS"
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pointofservicedriverinterface.h
api_name:
- IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS IOCTL

## -description

This I/O control function sets the specified statistic to the value in the input buffer.

## -ioctlparameters

### -input-buffer

[PosStatisticsHeader](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posstatisticsheader) where *PosStatisticsHeader.EntryCount* is set to the number of statistics to update.

This structure is then followed by a corresponding number of [PosValueStatisticsEntry](https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posvaluestatisticsentry) structures that contain the name of a statistic and the corresponding value to which it will be updated.

### -input-buffer-length

The sizeof(*PosStatisticsHeader*) + *PosStatisticsHeader.EntryCount* * sizeof(*PosValueStatisticsEntry*).

### -output-buffer

Not used with this operation; set to **NULL**.

### -output-buffer-length

Not used with this operation; set to **0** (zero).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](https://docs.microsoft.com/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following is a common error value:

- STATUS_NOT_SUPPORTED: Statistic updating or reporting is not supported.
