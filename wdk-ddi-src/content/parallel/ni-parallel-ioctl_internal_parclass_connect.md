---
UID: NI:parallel.IOCTL_INTERNAL_PARCLASS_CONNECT
title: IOCTL_INTERNAL_PARCLASS_CONNECT
author: windows-driver-content
description: The IOCTL_INTERNAL_PARCLASS_CONNECT request returns information about a parallel port and the callback routines that the system-supplied bus driver for parallel ports provides to operate the parallel port.
old-location: parports\ioctl_internal_parclass_connect.htm
old-project: parports
ms.assetid: 77dc31a1-a50c-4727-b730-1785e5d4a355
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: parports.ioctl_internal_parclass_connect, IOCTL_INTERNAL_PARCLASS_CONNECT control code [Parallel Ports], IOCTL_INTERNAL_PARCLASS_CONNECT, parallel/IOCTL_INTERNAL_PARCLASS_CONNECT, cisspd_03b94b78-be74-4421-bb08-0860d6d8dca5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: parallel.h
req.include-header: Parallel.h
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
-	parallel.h
apiname:
-	IOCTL_INTERNAL_PARCLASS_CONNECT
product: Windows
targetos: Windows
req.typenames: "*LPRILGBATOKEN, RILGBATOKEN"
---

# IOCTL_INTERNAL_PARCLASS_CONNECT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_INTERNAL_PARCLASS_CONNECT</b> request returns information about a parallel port and the callback routines that the system-supplied bus driver for parallel ports provides to operate the parallel port.

For more information, see <a href="https://msdn.microsoft.com/c05a1a1e-308a-4b9f-af43-761c4c14d6af">Connecting to a Parallel Device</a>.


## -ioctlparameters




### -input-buffer

A <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. 


### -input-buffer-length

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. 


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure that the client allocates to output information.


### -output-buffer-length

The size of a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a PARCLASS_INFORMATION structure. Otherwise, the <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices or to the following value:




#### -STATUS_BUFFER_TOO_SMALL

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a PARCLASS_INFORMATION structure.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parclass_disconnect.md">IOCTL_INTERNAL_PARCLASS_DISCONNECT</a>



<a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_PARCLASS_CONNECT control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

