---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_GET_PROPERTY
title: IOCTL_POINT_OF_SERVICE_GET_PROPERTY
author: windows-driver-content
description: This I/O control function returns the value of the specified property from the device driver.
old-location: pos\ioctl_point_of_service_get_property.htm
tech.root: pos
ms.assetid: 7d0231b3-4db7-47b3-8208-70d2cd337005
ms.date: 02/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_GET_PROPERTY, IOCTL_POINT_OF_SERVICE_GET_PROPERTY control, IOCTL_POINT_OF_SERVICE_GET_PROPERTY control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_GET_PROPERTY, pos.ioctl_point_of_service_get_property
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
-	IOCTL_POINT_OF_SERVICE_GET_PROPERTY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_GET_PROPERTY IOCTL


## -description


This I/O control function returns the value of the specified property from the device driver. 


## -ioctlparameters




### -input-buffer

Pointer to a buffer that contains the <a href="https://msdn.microsoft.com/library/windows/hardware/dn772239">PosPropertyId</a> for the property you want to get.


### -input-buffer-length

Size, in bytes, of the buffer pointed to by <i>lpInBuffer</i>. Set to sizeof(<i>PosPropertyId</i>).


### -output-buffer

Pointer to a buffer that receives the property value.


### -output-buffer-length

Size, in bytes, of the buffer pointed to by <i>lpOutBuffer</i>. 


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values (other status values may be returned as defined by your GET property callback implementation):




#### -STATUS_ACCESS_DENIED

The calling thread does not have a claim on the device.


#### -STATUS_BUFFER_OVERFLOW

The output buffer is not large enough to contain the output value. The driver will copy as much data into the output buffer as possible.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>




