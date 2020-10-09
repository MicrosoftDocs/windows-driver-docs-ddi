---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
title: IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE (pointofservicedriverinterface.h)
description: This I/O control function deauthenticates the magnetic stripe reader (MSR).
old-location: pos\ioctl_point_of_service_msr_deauthenticate_device.htm
tech.root: pos
ms.assetid: 796ee8e7-693f-41dd-ad09-cb3c21779ab9
ms.date: 08/21/2020
keywords: ["IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE IOCTL"]
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE, IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE control, IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE, pos.ioctl_point_of_service_msr_deauthenticate_device
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
 - IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
 - pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
---

# IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE IOCTL


## -description

This I/O control function deauthenticates the magnetic stripe reader (MSR).

## -ioctlparameters

### -input-buffer

Pointer to the input buffer, a [MSR_DEAUTHENTICATE_DEVICE](./ns-pointofservicedriverinterface-_msr_deauthenticate_device.md) variable that contains the challenge token.

### -input-buffer-length

Size of the input buffer, in bytes. Set to **sizeof(MSR_DEAUTHENTICATE_DEVICE)**.

### -output-buffer

Not used with this operation; set to **NULL**.

### -output-buffer-length

Not used with this operation; set to **0** (zero).

### -in-out-buffer

### -inout-buffer-length

### -status-block

Returns TRUE if successful; otherwise, returns FALSE.

To get extended error information, call [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

## -remarks