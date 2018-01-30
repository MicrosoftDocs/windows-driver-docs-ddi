---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
title: IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
author: windows-driver-content
description: This I/O control function retrieves the device authentication type.
old-location: pos\ioctl_point_of_service_msr_retrieve_device_authentication.htm
old-project: pos
ms.assetid: 6f086416-ab50-46fc-933e-a3d48c7dbf4c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pos.ioctl_point_of_service_msr_retrieve_device_authentication, IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION control code, IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
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
-	IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION
product: Windows
targetos: Windows
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_MSR_RETRIEVE_DEVICE_AUTHENTICATION IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


This I/O control function retrieves the device authentication type.


## -ioctlparameters




### -input-buffer

Not used with this operation; set to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -output-buffer

Pointer to a buffer that receives a <a href="..\pointofservicedriverinterface\ns-pointofservicedriverinterface-_msr_retrieve_device_authentication_data.md">MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA</a>.


### -output-buffer-length

Size of the output buffer, in bytes. Set to sizeof(<b>MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA</b>).


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>.


## -remarks


<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>


