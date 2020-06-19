---
UID: NI:ntddpar.IOCTL_PAR_QUERY_LOCATION
title: IOCTL_PAR_QUERY_LOCATION (ntddpar.h)
description: The IOCTL_PAR_QUERY_LOCATION request returns the &#0034;LPTn&#0034; or &#0034;LPTn.m&#0034; symbolic link name associated with a parallel device.
old-location: parports\ioctl_par_query_location.htm
tech.root: parports
ms.assetid: a46b1f7f-d624-48f3-a2cf-6828908ba3c1
ms.date: 02/15/2018
keywords: ["IOCTL_PAR_QUERY_LOCATION IOCTL"]
ms.keywords: IOCTL_PAR_QUERY_LOCATION, IOCTL_PAR_QUERY_LOCATION control code [Parallel Ports], cisspd_49c52fd1-3855-4611-aa3b-4fa7c0ec6b16.xml, ntddpar/IOCTL_PAR_QUERY_LOCATION, parports.ioctl_par_query_location
f1_keywords:
 - "ntddpar/IOCTL_PAR_QUERY_LOCATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddpar.h
api_name:
- IOCTL_PAR_QUERY_LOCATION
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_QUERY_LOCATION IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The IOCTL_PAR_QUERY_LOCATION request returns the "LPT<i>n</i>" or "LPT<i>n.m</i>" symbolic link name associated with a parallel device. This request is only supported by Windows XP and later.



<dl>
<dt><a id="For_more_information__see_Device_Stacks_for_ParallelPorts_and_Devices_and_Parallel_Device_Interfaces__Internal_Names__and_Symbolic_Links."></a><a id="for_more_information__see_device_stacks_for_parallelports_and_devices_and_parallel_device_interfaces__internal_names__and_symbolic_links."></a><a id="FOR_MORE_INFORMATION__SEE_DEVICE_STACKS_FOR_PARALLELPORTS_AND_DEVICES_AND_PARALLEL_DEVICE_INTERFACES__INTERNAL_NAMES__AND_SYMBOLIC_LINKS."></a>For more information, see <a href="https://docs.microsoft.com/previous-versions/ff543949(v=vs.85)">Device Stacks for ParallelPorts and Devices</a> and <a href="https://docs.microsoft.com/previous-versions/ff544284(v=vs.85)">Parallel Device Interfaces, Internal Names, and Symbolic Links</a>.</dt>
<dd></dd>
</dl>



## -ioctlparameters




### -input-buffer

The client sets the <b>AssociatedIrp.SystemBuffer</b> member to a pointer to a character buffer for the location information.


### -input-buffer-length

The length of the character buffer.


### -output-buffer

The parallel port bus driver outputs the location information in the buffer pointed to by <b>AssociatedIrp.SystemBuffer</b> as a <b>NULL</b>-terminated character string.


### -output-buffer-length

The client sets the <b>Parameters.DeviceIoControl.OutputBufferLength </b>member to the length of the output buffer that the system-supplied bus driver for parallel ports uses to output the device location information.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request succeeds, the <b>Information</b> member is set to the length, in bytes, of the symbolic link name plus the <b>NULL</b> terminator. Otherwise, <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:




**STATUS_BUFFER_TOO_SMALL**

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than size, in bytes, of the location information and the <b>NULL</b> terminator.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>



 

 


