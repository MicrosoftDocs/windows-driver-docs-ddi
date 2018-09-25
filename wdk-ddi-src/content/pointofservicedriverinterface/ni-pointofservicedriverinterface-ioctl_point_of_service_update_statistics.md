---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
title: IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
author: windows-driver-content
description: This I/O control function sets the specified statistic to the value in the input buffer.
old-location: pos\ioctl_point_of_service_update_statistics.htm
tech.root: pos
ms.assetid: 94c8d49a-5136-49f3-a313-74c032502f1f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS, IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS control, IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS, pos.ioctl_point_of_service_update_statistics
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pointofservicedriverinterface.h
api_name:
-	IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_UPDATE_STATISTICS IOCTL


## -description


This I/O control function sets the specified statistic to the value in the input buffer.


## -ioctlparameters




### -input-buffer


<a href="https://msdn.microsoft.com/library/windows/hardware/dn772241">PosStatisticsHeader</a> where <i>PosStatisticsHeader.EntryCount</i> is set to the number of statistics to update. This structure is then followed by a corresponding number of <a href="https://msdn.microsoft.com/library/windows/hardware/dn772322">PosValueStatisticsEntry</a> structures that contain the name of a statistic and the corresponding value to which it will be updated.


### -input-buffer-length

The sizeof(<i>PosStatisticsHeader</i>) + <i>PosStatisticsHeader.EntryCount</i> * sizeof(<i>PosValueStatisticsEntry</i>).


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




