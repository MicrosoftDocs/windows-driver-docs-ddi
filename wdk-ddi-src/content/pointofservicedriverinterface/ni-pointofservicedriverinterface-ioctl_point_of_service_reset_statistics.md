---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_RESET_STATISTICS
title: IOCTL_POINT_OF_SERVICE_RESET_STATISTICS
author: windows-driver-content
description: This I/O control function resets the specified statistic's value to zero.
old-location: pos\ioctl_point_of_service_reset_statistics.htm
tech.root: pos
ms.assetid: dfa6a460-ea80-4aa4-9948-2fd290f6616b
ms.date: 2/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_RESET_STATISTICS, IOCTL_POINT_OF_SERVICE_RESET_STATISTICS control, IOCTL_POINT_OF_SERVICE_RESET_STATISTICS control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_RESET_STATISTICS, pos.ioctl_point_of_service_reset_statistics
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
-	IOCTL_POINT_OF_SERVICE_RESET_STATISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_RESET_STATISTICS IOCTL


## -description


This I/O control function resets the specified statistic's value to zero.


## -ioctlparameters




### -input-buffer


<a href="https://msdn.microsoft.com/library/windows/hardware/dn772274">PosStringType</a> that names the statistic to reset to zero.


### -input-buffer-length

Size of the string passed in <i>lpInBuffer</i>. Set to sizeof(<i>PosStringType</i>) + the size of the string in bytes.


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

To get extended error information, call <a href="http://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values: 




#### -STATUS_NOT_SUPPORTED

Statistic updating or reporting is not supported.


## -remarks



<h3><a id="Parameters"></a><a id="parameters"></a><a id="PARAMETERS"></a>Parameters</h3>




