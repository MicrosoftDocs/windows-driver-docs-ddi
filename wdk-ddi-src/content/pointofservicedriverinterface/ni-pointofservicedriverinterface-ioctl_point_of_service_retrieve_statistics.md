---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS
title: IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS (pointofservicedriverinterface.h)
description: This I/O control function returns unified point of service (UPOS) standard information about a device such as its category, manufacturer, and firmware revision number.
old-location: pos\ioctl_point_of_service_retrieve_statistics.htm
tech.root: pos
ms.assetid: 8c63ef41-e4dd-4b34-a897-c9bec13f4211
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS, IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS control, IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS, pos.ioctl_point_of_service_retrieve_statistics
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS
 - pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS
---

# IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS IOCTL


## -description

This I/O control function returns unified point of service (UPOS) standard information about a device such as its category, manufacturer, and firmware revision number.

## -ioctlparameters

### -input-buffer

[in] Not used with this operation; set to **NULL**.

### -input-buffer-length

Not used with this operation; set to **0** (zero).

### -output-buffer

Pointer to the [PosStatisticsHeader](./ns-pointofservicedriverinterface-_posstatisticsheader.md) structure that contains the statistics.

### -output-buffer-length

Size of the output buffer in bytes. Set to sizeof(*PosStatisticsHeader*).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns **TRUE** if successful; otherwise, returns **FALSE**.

## -remarks

To get extended error information, call [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). The following list shows common error values:

- STATUS_BUFFER_OVERFLOW: The output buffer is not large enough to hold the statistics.

- STATUS_NOT_SUPPORTED: Statistic reporting is not supported.