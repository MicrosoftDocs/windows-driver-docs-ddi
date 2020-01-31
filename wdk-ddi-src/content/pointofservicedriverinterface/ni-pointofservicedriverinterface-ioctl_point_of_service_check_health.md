---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
title: IOCTL_POINT_OF_SERVICE_CHECK_HEALTH (pointofservicedriverinterface.h)
description: This I/O control function checks the device health.
old-location: pos\ioctl_point_of_service_check_health.htm
tech.root: pos
ms.assetid: b11be48b-e791-4599-80da-2446791f3816
ms.date: 02/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_CHECK_HEALTH, IOCTL_POINT_OF_SERVICE_CHECK_HEALTH control, IOCTL_POINT_OF_SERVICE_CHECK_HEALTH control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_CHECK_HEALTH, pos.ioctl_point_of_service_check_health
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_CHECK_HEALTH"
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
- IOCTL_POINT_OF_SERVICE_CHECK_HEALTH
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_CHECK_HEALTH IOCTL

## -description

This I/O control function checks the device health.

## -ioctlparameters

### -input-buffer

Pointer to the input buffer, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicecommontypes/ne-pointofservicecommontypes-driverunifiedposhealthchecklevel">UnifiedPosHealthCheckLevel</a> variable.

### -input-buffer-length

Size of the input buffer, in bytes. Set to sizeof(<i>UnifiedPosHealthCheckLevel</i>).

### -output-buffer

Pointer to a buffer that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_posstringtype">PosStringType</a> followed by the contents of the health string.

### -output-buffer-length

Size of the output buffer, in bytes. Set to sizeof(<i>PosStringType</i>) + enough room to hold the health string.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

## -remarks

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following is a common error value:

- STATUS_NOT_SUPPORTED: The driver does not provide health strings.
