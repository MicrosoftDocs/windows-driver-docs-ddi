---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES
title: IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES
author: windows-driver-content
description: This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of the silo driver's capabilities.
old-location: storage\ioctl_ehstor_driver_report_capabilities.htm
old-project: storage
ms.assetid: AD78ABAD-5DCF-4E1A-B521-8063B5BEA6A6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES, IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES, storage.ioctl_ehstor_driver_report_capabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
-	EhStorIoctl.h
api_name:
-	IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES IOCTL


## -description


This IOCTL is used to inform the enhanced storage (EHSTOR) class driver of the silo  driver's capabilities.  The silo driver sends this IOCTL with a <a href="https://msdn.microsoft.com/32bb774f-b1eb-4198-8e4c-febcac83153d">SILO_DRIVER_CAPABILITES</a> structure that indicates whether authentication and banding are supported along with a list of EHSTOR IOCTLs it will handle.


## -ioctlparameters




### -input-buffer

The input buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> must contain a structure of type <a href="https://msdn.microsoft.com/32bb774f-b1eb-4198-8e4c-febcac83153d">SILO_DRIVER_CAPABILITES</a>. This structure is followed immediately by a list of which redirected IOCTLs the silo driver will handle.


### -input-buffer-length

The length of the buffer.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>The silo driver's capabilities were registered with the EHSTOR class driver.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer length supplied is of incorrect size.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>A capability parameter is incorrect.</td>
</tr>
<tr>
<td>STATUS_INSUFFICIENT_RESOURCES</td>
<td>The IOCTL redirection list cannot be copied.</td>
</tr>
<tr>
<td>STATUS_NOT_SUPPORTED</td>
<td>The sending device is not a silo device.</td>
</tr>
</table>
 


## -remarks



This IOCTL is used by the Trusted Computing Group (TCG) standard authentication silo driver in Windows 8. On device initialization, the TCG silo driver will notify the EHSTOR class driver (EhStorClass.sys) of its capabilities by sending a <b>IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</b> request with a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464118">SILO_DRIVER_CAPABILITIES</a> structure.

Silo device objects exist outside the storage device stack. Any EHSTOR request intended for a silo driver must be explicitly forwarded to it. This is the case for all band management IOCTLs. Band management  requests are made on a file object representing a physical drive. These requests are sent down the storage device stack. If the silo driver has registered support for the IOCTL, the EHSTOR class driver will redirect the request to the silo driver.

IOCTL requests supported by a silo driver are included in an array following <a href="https://msdn.microsoft.com/library/windows/hardware/hh464118">SILO_DRIVER_CAPABILITIES</a> in the system buffer. The size of the information in the system buffer should be specified as <b>sizeof</b>(SILO_DRIVER_CAPABILITIES) + (<b>sizeof</b>(ULONG) * <i>RedirectedIoctlListCount</i>).

 A vendor supplied non-TCG authentication silo driver must notify the EHSTOR class driver of its capabilities using this IOCTL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464118">SILO_DRIVER_CAPABILITIES</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES control code%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

