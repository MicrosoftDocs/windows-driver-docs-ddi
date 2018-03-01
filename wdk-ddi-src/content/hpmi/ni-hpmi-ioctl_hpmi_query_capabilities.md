---
UID: NI:hpmi.IOCTL_HPMI_QUERY_CAPABILITIES
title: IOCTL_HPMI_QUERY_CAPABILITIES
author: windows-driver-content
description: The IOCTL_HPMI_QUERY_CAPABILITIES command is sent to query features supported by HPMI and Windows services requested by HPMI. Windows will issue this IOCL to HPMI once after a new HPMI driver instance is discovered.
old-location: powermeter\ioctl_hpmi_query_capabilities.htm
old-project: powermeter
ms.assetid: 2CCEDDB4-C91D-4E88-A01F-BB52F1686A95
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_HPMI_QUERY_CAPABILITIES, IOCTL_HPMI_QUERY_CAPABILITIES control code [Power Metering and Budgeting Devices], hpmi/IOCTL_HPMI_QUERY_CAPABILITIES, powermeter.ioctl_hpmi_query_capabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hpmi.h
req.include-header: Hpmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
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
-	hpmi.h
api_name:
-	IOCTL_HPMI_QUERY_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: HPMI_HINT_BOOL, *PHPMI_HINT_BOOL
---

# IOCTL_HPMI_QUERY_CAPABILITIES IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The IOCTL_HPMI_QUERY_CAPABILITIES command is sent to query features supported by HPMI and Windows services requested by HPMI. Windows will issue this IOCL to HPMI once after a new HPMI driver instance is discovered.   

<div class="alert"><b>Important</b>  Preliminary Information</div><div> </div>

## -ioctlparameters




### -input-buffer



The AssociatedIrp.SystemBuffer member of the I/O request packet (IRP) points to an initiator-allocated buffer that is used both as the input buffer and the output buffer for the request. On input, this buffer contains a <a href="..\hpmi\ns-hpmi-_hpmi_query_capabilities.md">HPMI_QUERY_CAPABILITIES</a> structure  in which the version is set to a valid value. 


### -input-buffer-length

The Parameters.DeviceIoControl.InputBufferLength member of the IRP's current I/O stack location (IO_STACK_LOCATION) is set to the size in bytes of the buffer that is pointed to by the AssociatedIrp.SystemBuffer member. This size must be greater than or equal to sizeof <a href="..\hpmi\ns-hpmi-_hpmi_query_capabilities.md">HPMI_QUERY_CAPABILITIES</a> structure  or the request will fail with an error status of STATUS_INVALID_PARAMETER.


### -output-buffer

If the request completes successfully, the buffer pointed to by the AssociatedIrp.SystemBuffer member contains the requested HPMI capability information. Located at the start of this buffer is a <a href="..\hpmi\ns-hpmi-_hpmi_query_capabilities_response.md">HPMI_QUERY_CAPABILITIES_RESPONSE</a> structure that indicates the type and size of the information in the buffer.


### -output-buffer-length

The Parameters.DeviceIoControl.OutputBufferLength member of the IRP's current I/O stack location is set to the size in bytes of the buffer that is pointed to by the AssociatedIrp.SystemBuffer member. For the request to succeed, this size must be large enough to contain the HPMI capability described in <a href="..\hpmi\ns-hpmi-_hpmi_query_capabilities_response.md">HPMI_QUERY_CAPABILITIES_RESPONSE</a>. Otherwise, the request will fail with error status STATUS_BUFFER_TOO_SMALL.


### -in-out-buffer

TBD


### -inout-buffer-length

TBD


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code, for example STATUS_INVALID_PARAMETER. 


## -remarks



The <b>IOCTL_HPMI_QUERY_CAPABILITIES</b> request queries the HPMI capabilities or asset information of the power meter. The input <a href="..\hpmi\ns-hpmi-_hpmi_query_capabilities.md">HPMI_QUERY_CAPABILITIES</a> structure value specifies the type of capability information to be returned. The data type and contents of the output buffer vary based on the data requested.

This IOCTL may be issued multiple times, HPMI must respond with same  
information in HPMI_QUERY_CAPABILITIES_RESPONSE, as a response to all  
subsequent IOCTL calls.   




## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20IOCTL_HPMI_QUERY_CAPABILITIES control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

