---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
title: IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
author: windows-driver-content
description: This I/O control function deauthenticates the magnetic stripe reader (MSR).
old-location: pos\ioctl_point_of_service_msr_deauthenticate_device.htm
tech.root: pos
ms.assetid: 796ee8e7-693f-41dd-ad09-cb3c21779ab9
ms.date: 02/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE, IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE control, IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE, pos.ioctl_point_of_service_msr_deauthenticate_device
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pointofservicedriverinterface.h
api_name:
-	IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_MSR_DEAUTHENTICATE_DEVICE IOCTL


## -description


This I/O control function deauthenticates the magnetic stripe reader (MSR).


## -ioctlparameters




### -input-buffer

Pointer to the input buffer, a <a href="https://msdn.microsoft.com/library/windows/hardware/dn772182">MSR_DEAUTHENTICATE_DEVICE</a> variable that contains the challenge token.


### -input-buffer-length

Size of the input buffer, in bytes. Set to <b>sizeof(MSR_DEAUTHENTICATE_DEVICE)</b>.


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns TRUE if successful; otherwise, returns FALSE.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>




