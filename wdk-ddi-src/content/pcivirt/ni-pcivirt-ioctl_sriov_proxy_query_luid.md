---
UID: NI:pcivirt.IOCTL_SRIOV_PROXY_QUERY_LUID
title: IOCTL_SRIOV_PROXY_QUERY_LUID (pcivirt.h)
description: This request supplies the local unique identifier of the SR_IOV device implementing the interface.
old-location: pci\ioctl-sriov-proxy-query-luid.htm
tech.root: PCI
ms.date: 07/24/2025
keywords: ["IOCTL_SRIOV_PROXY_QUERY_LUID IOCTL"]
ms.keywords: IOCTL_SRIOV_PROXY_QUERY_LUID, IOCTL_SRIOV_PROXY_QUERY_LUID control code [Buses], PCI.ioctl-sriov-proxy-query-luid, pcivirt/IOCTL_SRIOV_PROXY_QUERY_LUID
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
targetos: Windows
req.typenames: SRIOV_PF_EVENT, *PSRIOV_PF_EVENT
f1_keywords:
 - IOCTL_SRIOV_PROXY_QUERY_LUID
 - pcivirt/IOCTL_SRIOV_PROXY_QUERY_LUID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - IOCTL_SRIOV_PROXY_QUERY_LUID
---

# IOCTL_SRIOV_PROXY_QUERY_LUID IOCTL

## Major Code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

## -description

This request supplies the local unique
identifier of the SR_IOV device implementing the interface.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/ifs/irp-mj-device-control)

### -input-buffer

### -input-buffer-length

### -output-buffer

A pointer to a [SRIOV_PROXY_QUERY_LUID_OUTPUT](ns-pcivirt-_sriov_proxy_query_luid_output.md) structure that is filled with the identifier.

### -output-buffer-length

The size of the [SRIOV_PROXY_QUERY_LUID_OUTPUT](ns-pcivirt-_sriov_proxy_query_luid_output.md) structure

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

This IOCTL request originates in the user mode and  is handled by the physical function (PF) driver in order to supply the local unique
identifier of the physical device.  This request is only required for SR-IOV devices doing direct assignment.

Before sending this request, the user mode application must obtain a handle to the PCI Express SR-IOV device by querying for GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

In this example, the PF driver generates a unique identifier by calling [ZwAllocateLocallyUniqueId](..\ntddk\nf-ntddk-zwallocatelocallyuniqueid.md)  and stores it in the device context.

```cpp
    case IOCTL_SRIOV_PROXY_QUERY_LUID:

        status = WdfRequestRetrieveOutputBuffer(Request,
                                                sizeof(LUID),
                                                &luid,
                                                NULL);
        if (!NT_SUCCESS(status))
        {
            break;
        }

        RtlCopyMemory(luid, &deviceContext->Luid, sizeof(LUID));
        WdfRequestSetInformation(Request, sizeof(LUID));
        status = STATUS_SUCCESS;
        break;

```

## -see-also

- [SRIOV_PROXY_QUERY_LUID_OUTPUT](/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_proxy_query_luid_output)
