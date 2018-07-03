---
UID: NI:pcivirt.IOCTL_SRIOV_PROXY_QUERY_LUID
title: IOCTL_SRIOV_PROXY_QUERY_LUID
author: windows-driver-content
description: This request supplies the local unique identifier of the SR_IOV device implementing the interface.
old-location: pci\ioctl-sriov-proxy-query-luid.htm
old-project: PCI
ms.assetid: 9f10ed34-f718-4c35-9b6f-29554bf30a0f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_SRIOV_PROXY_QUERY_LUID, IOCTL_SRIOV_PROXY_QUERY_LUID control code [Buses], PCI.ioctl-sriov-proxy-query-luid, pcivirt/IOCTL_SRIOV_PROXY_QUERY_LUID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pcivirt.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	IOCTL_SRIOV_PROXY_QUERY_LUID
product:
- Windows
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
---

# IOCTL_SRIOV_PROXY_QUERY_LUID IOCTL


##  Major Code: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

## -description


This request supplies the local unique
identifier of the SR_IOV device implementing the interface.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer

A pointer to a <a href="https://msdn.microsoft.com/8db09aa8-240d-40b6-a28c-77158aff6c39">SRIOV_PROXY_QUERY_LUID_OUTPUT</a> structure that is filled with the identifier.


### -output-buffer-length

The size of the <a href="https://msdn.microsoft.com/8db09aa8-240d-40b6-a28c-77158aff6c39">SRIOV_PROXY_QUERY_LUID_OUTPUT</a> structure


### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks



This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

This IOCTL request originates in the user mode and  is handled by the physical function (PF) driver in order to supply the local unique
identifier of the physical device.  This request is only required for SR-IOV devices doing direct assignment. 

Before sending this request, the user mode application must obtain a handle to the PCI Express SR-IOV device by querying for GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

In this example, the PF driver generates a unique identifier by calling <a href="..\ntddk\nf-ntddk-zwallocatelocallyuniqueid.md">ZwAllocateLocallyUniqueId</a>  and stores it in the device context. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
   
    case IOCTL_SRIOV_PROXY_QUERY_LUID:

        status = WdfRequestRetrieveOutputBuffer(Request,
                                                sizeof(LUID),
                                                &amp;luid,
                                                NULL);
        if (!NT_SUCCESS(status))
        {
            break;
        }

        RtlCopyMemory(luid, &amp;deviceContext-&gt;Luid, sizeof(LUID));
        WdfRequestSetInformation(Request, sizeof(LUID));
        status = STATUS_SUCCESS;
        break;
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/8db09aa8-240d-40b6-a28c-77158aff6c39">SRIOV_PROXY_QUERY_LUID_OUTPUT</a>



 

 


