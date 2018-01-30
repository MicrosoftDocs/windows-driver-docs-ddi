---
UID: NI:ntddscsi.IOCTL_MINIPORT_PROCESS_SERVICE_IRP
title: IOCTL_MINIPORT_PROCESS_SERVICE_IRP
author: windows-driver-content
description: This IOCTL is used by a user-mode application or kernel-mode driver that requires notification when something of interest happens in the virtual miniport.
old-location: storage\ioctl_miniport_process_service_irp.htm
old-project: storage
ms.assetid: 5d9f695c-9a9f-4af9-8bf6-2096f3278852
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_miniport_process_service_irp, IOCTL_MINIPORT_PROCESS_SERVICE_IRP control code [Storage Devices], IOCTL_MINIPORT_PROCESS_SERVICE_IRP, ntddscsi/IOCTL_MINIPORT_PROCESS_SERVICE_IRP, k307_8997b602-e4ce-4b15-be19-77ba863de295.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
-	Ntddscsi.h
apiname:
-	IOCTL_MINIPORT_PROCESS_SERVICE_IRP
product: Windows
targetos: Windows
req.typenames: "*PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE"
---

# IOCTL_MINIPORT_PROCESS_SERVICE_IRP IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



This IOCTL is used by a user-mode application or kernel-mode driver that requires notification when something of interest happens in the virtual miniport. This IOCTL might be used, for example, when a vendor-specific, time-consuming operation such as device discovery completes.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a user-defined structure. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of all the input data.


### -output-buffer

Updated user-defined structures are returned in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

The length of the buffer.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557410">HwStorProcessServiceRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_MINIPORT_PROCESS_SERVICE_IRP control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

