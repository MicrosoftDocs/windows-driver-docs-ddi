---
UID: NI:ntddpar.IOCTL_PAR_SET_INFORMATION
title: IOCTL_PAR_SET_INFORMATION
author: windows-driver-content
description: The IOCTL_PAR_SET_INFORMATION request resets and initializes a parallel device.
old-location: parports\ioctl_par_set_information.htm
old-project: parports
ms.assetid: a54902d0-aa07-4cd0-8ef1-a3c17dff2ac9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.ioctl_par_set_information, IOCTL_PAR_SET_INFORMATION control code [Parallel Ports], IOCTL_PAR_SET_INFORMATION, ntddpar/IOCTL_PAR_SET_INFORMATION, cisspd_950d6397-7eff-4966-a734-0497f1a84257.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
-	ntddpar.h
apiname: 
-	IOCTL_PAR_SET_INFORMATION
product: Windows
targetos: Windows
req.typenames: *POFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_SET_INFORMATION IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The IOCTL_PAR_SET_INFORMATION request resets and initializes a parallel device.




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\ntddpar\ns-ntddpar-_par_set_information.md">PAR_SET_INFORMATION</a> structure that the client allocates to input set information. The client sets the <b>Init</b> member to PARALLEL_INIT.


### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a PAR_SET_INFORMATION structure. 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to one of the following values:




#### -STATUS_BUFFER_TOO_SMALL

<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of a PAR_SET_INFORMATION structure. 


#### -STATUS_DEVICE_NOT_CONNECTED

The device is not connected.


#### -STATUS_DEVICE_OFF_LINE

The device is offline.


#### -STATUS_DEVICE_PAPER_EMPTY

The device is out of paper.


#### -STATUS_DEVICE_POWERED_OFF

The device is not turned on.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_information.md">IOCTL_PAR_QUERY_INFORMATION</a>

<a href="..\ntddpar\ns-ntddpar-_par_set_information.md">PAR_SET_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_PAR_SET_INFORMATION control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

