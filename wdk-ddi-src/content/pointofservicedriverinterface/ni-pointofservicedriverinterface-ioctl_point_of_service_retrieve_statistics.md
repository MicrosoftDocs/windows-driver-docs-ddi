---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS
title: IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS (pointofservicedriverinterface.h)
description: This I/O control function returns unified point of service (UPOS) standard information about a device such as its category, manufacturer, and firmware revision number.
old-location: pos\ioctl_point_of_service_retrieve_statistics.htm
tech.root: pos
ms.assetid: 8c63ef41-e4dd-4b34-a897-c9bec13f4211
ms.date: 02/23/2018
keywords: ["IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS, IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS control, IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS, pos.ioctl_point_of_service_retrieve_statistics
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS"
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
- IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_RETRIEVE_STATISTICS IOCTL


## -description


This I/O control function returns unified point of service (UPOS) standard information about a device such as its category, manufacturer, and firmware revision number.


## -ioctlparameters




### -input-buffer

[in] Not used with this operation; set to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -output-buffer

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posstatisticsheader">PosStatisticsHeader</a> structure that contains the statistics.


### -output-buffer-length

Size of the output buffer in bytes. Set to sizeof(<i>PosStatisticsHeader</i>).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

## -remarks

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values:

- STATUS_BUFFER_OVERFLOW: The output buffer is not large enough to hold the statistics.

- STATUS_NOT_SUPPORTED: Statistic reporting is not supported.
