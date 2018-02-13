---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
title: IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
author: windows-driver-content
description: This I/O control function gets the type of device, version, and recommended buffer size as specified by the driver.
old-location: pos\ioctl_point_of_service_get_device_basics.htm
old-project: pos
ms.assetid: dca09bfc-97cc-43b8-bf57-3d7c2b0321a9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pos.ioctl_point_of_service_get_device_basics, IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS control code, IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicedriverinterface.h
apiname:
-	IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS
product: Windows
targetos: Windows
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_GET_DEVICE_BASICS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


This I/O control function gets the type of device, version, and recommended buffer size as specified by the driver.


## -ioctlparameters




### -input-buffer

32-bit encoded POS Windows Runtime (WinRT) API version. The top sixteen bits must contain the major version, and the lower sixteen bits must contain the minor version.


### -input-buffer-length

Size of the input buffer, in bytes. Set to sizeof(UINT32).


### -output-buffer

Pointer to a buffer that receives a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posdevicebasicstype.md">PosDeviceBasicsType</a>.


### -output-buffer-length

Size of the output buffer, in bytes. Set to sizeof(<i>PosDeviceBasicsType</i>). 


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values:




#### -STATUS_BUFFER_TOO_SMALL

The output buffer is not large enough to contain the result.


#### -STATUS_INSUFFICIENT_RESOURCES

There is insufficient memory.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>


Provide the version of the POS WinRT API to inform the driver which version of the runtime it is working with. This IOCTL returns the version of the driver in <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_posdevicebasicstype.md">PosDeviceBasicsType</a>, so that you can have the driver version available in the runtime API if you wish to provide it.



