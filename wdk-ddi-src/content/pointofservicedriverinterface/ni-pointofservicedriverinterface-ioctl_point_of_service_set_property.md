---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_SET_PROPERTY
title: IOCTL_POINT_OF_SERVICE_SET_PROPERTY
author: windows-driver-content
description: This I/O control function sets the specified property on the device.
old-location: pos\ioctl_point_of_service_set_property.htm
old-project: pos
ms.assetid: 8907a99f-37b0-4c09-b92a-ac720328020e
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: pos.ioctl_point_of_service_set_property, IOCTL_POINT_OF_SERVICE_SET_PROPERTY control code, IOCTL_POINT_OF_SERVICE_SET_PROPERTY, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_SET_PROPERTY
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
-	IOCTL_POINT_OF_SERVICE_SET_PROPERTY
product: Windows
targetos: Windows
req.typenames: PosPropertyId
---

# IOCTL_POINT_OF_SERVICE_SET_PROPERTY IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


This I/O control function sets the specified property on the device.


## -ioctlparameters




### -input-buffer


<a href="..\pointofservicedriverinterface\ne-pointofservicedriverinterface-_pospropertyid.md">PosPropertyId</a> of the property to set followed by the value of the property. The encoding for the type follows the property ID in the byte stream.


### -input-buffer-length

Set to sizeof(<i>PosPropertyId</i>) + the size of the property value.


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values (other return values may be returned as defined by your property callback implementation):




#### -STATUS_ACCESS_DENIED

The device is currently claimed by another client.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>


The client must successfully call <a href="..\pointofservicedriverinterface\ni-pointofservicedriverinterface-ioctl_point_of_service_claim_device.md">IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE</a> before using this IOCTL.



