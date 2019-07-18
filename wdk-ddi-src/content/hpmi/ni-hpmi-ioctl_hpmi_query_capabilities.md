---
UID: NI:hpmi.IOCTL_HPMI_QUERY_CAPABILITIES
title: IOCTL_HPMI_QUERY_CAPABILITIES (hpmi.h)
description: The IOCTL_HPMI_QUERY_CAPABILITIES command is sent to query features supported by HPMI and Windows services requested by HPMI. Windows will issue this IOCL to HPMI once after a new HPMI driver instance is discovered.
old-location: powermeter\ioctl_hpmi_query_capabilities.htm
tech.root: powermeter
ms.assetid: 2CCEDDB4-C91D-4E88-A01F-BB52F1686A95
ms.date: 05/08/2018
ms.keywords: IOCTL_HPMI_QUERY_CAPABILITIES, IOCTL_HPMI_QUERY_CAPABILITIES control, IOCTL_HPMI_QUERY_CAPABILITIES control code [Power Metering and Budgeting Devices], hpmi/IOCTL_HPMI_QUERY_CAPABILITIES, powermeter.ioctl_hpmi_query_capabilities
ms.topic: ioctl
f1_keywords:
 - "hpmi/IOCTL_HPMI_QUERY_CAPABILITIES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hpmi.h
api_name:
- IOCTL_HPMI_QUERY_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HPMI_QUERY_CAPABILITIES IOCTL


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The IOCTL_HPMI_QUERY_CAPABILITIES command is sent to query features supported by HPMI and Windows services requested by HPMI. Windows will issue this IOCL to HPMI once after a new HPMI driver instance is discovered.   

<div class="alert"><b>Important</b>  Preliminary Information</div><div> </div>

## -ioctlparameters




### -input-buffer



The AssociatedIrp.SystemBuffer member of the I/O request packet (IRP) points to an initiator-allocated buffer that is used both as the input buffer and the output buffer for the request. On input, this buffer contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/ns-hpmi-_hpmi_query_capabilities">HPMI_QUERY_CAPABILITIES</a> structure  in which the version is set to a valid value. 


### -input-buffer-length

The Parameters.DeviceIoControl.InputBufferLength member of the IRP's current I/O stack location (IO_STACK_LOCATION) is set to the size in bytes of the buffer that is pointed to by the AssociatedIrp.SystemBuffer member. This size must be greater than or equal to sizeof <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/ns-hpmi-_hpmi_query_capabilities">HPMI_QUERY_CAPABILITIES</a> structure  or the request will fail with an error status of STATUS_INVALID_PARAMETER.


### -output-buffer

If the request completes successfully, the buffer pointed to by the AssociatedIrp.SystemBuffer member contains the requested HPMI capability information. Located at the start of this buffer is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/ns-hpmi-_hpmi_query_capabilities_response">HPMI_QUERY_CAPABILITIES_RESPONSE</a> structure that indicates the type and size of the information in the buffer.


### -output-buffer-length

The Parameters.DeviceIoControl.OutputBufferLength member of the IRP's current I/O stack location is set to the size in bytes of the buffer that is pointed to by the AssociatedIrp.SystemBuffer member. For the request to succeed, this size must be large enough to contain the HPMI capability described in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/ns-hpmi-_hpmi_query_capabilities_response">HPMI_QUERY_CAPABILITIES_RESPONSE</a>. Otherwise, the request will fail with error status STATUS_BUFFER_TOO_SMALL.


### -in-out-buffer

TBD


### -inout-buffer-length

TBD


### -status-block

<b>Irp->IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> code, for example STATUS_INVALID_PARAMETER. 


## -remarks



The <b>IOCTL_HPMI_QUERY_CAPABILITIES</b> request queries the HPMI capabilities or asset information of the power meter. The input <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hpmi/ns-hpmi-_hpmi_query_capabilities">HPMI_QUERY_CAPABILITIES</a> structure value specifies the type of capability information to be returned. The data type and contents of the output buffer vary based on the data requested.

This IOCTL may be issued multiple times, HPMI must respond with same  
information in HPMI_QUERY_CAPABILITIES_RESPONSE, as a response to all  
subsequent IOCTL calls.   




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers">Creating IOCTL Requests in Drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
 

 


