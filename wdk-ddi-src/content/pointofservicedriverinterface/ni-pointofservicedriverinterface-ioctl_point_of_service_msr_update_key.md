---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY
title: IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY (pointofservicedriverinterface.h)
description: This I/O control function sets a new encryption key.
old-location: pos\ioctl_point_of_service_msr_update_key.htm
tech.root: pos
ms.assetid: 7ac830d3-6a75-4d82-9123-cd7ad9c2cdea
ms.date: 02/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY, IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY control, IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY, pos.ioctl_point_of_service_msr_update_key
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY"
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
- IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_MSR_UPDATE_KEY IOCTL


## -description


This I/O control function sets a new encryption key.


## -ioctlparameters




### -input-buffer

Pointer to the input buffer, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pointofservicedriverinterface/ns-pointofservicedriverinterface-_msr_update_key">MSR_UPDATE_KEY</a> variable.


### -input-buffer-length

Size of the input buffer, in bytes. Set to <b>sizeof(MSR_UPDATE_KEY)</b>.


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>




