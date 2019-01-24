---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX
title: IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX
description: The IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request retrieves information about a USB port and the device that is attached to the port, if there is one.Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.
old-location: buses\ioctl_usb_get_node_connection_information_ex.htm
tech.root: usbref
ms.assetid: d056dd82-815d-42da-8d2a-490474f68782
ms.date: 01/24/2019
ms.keywords: IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX, IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX control, IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX control code [Buses], buses.ioctl_usb_get_node_connection_information_ex, usbioctl/IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX, usbirp_61c188b5-2820-4601-b2de-08bf30109824.xml
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP, Windows Server 2003, and later.
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
-	Usbioctl.h
api_name:
-	IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX IOCTL


## -description



The <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</b> request retrieves information about a USB port and the device that is attached to the port, if there is one.

Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.

<b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer



### -input-buffer-length




### -output-buffer




### -output-buffer-length



### -in-out-buffer

Both input and output buffers point to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure.
On input, the <b>ConnectionIndex</b> member of this structure must contain a number greater than or equal to 1 that indicates the number of the port whose connection information is to be reported. The hub driver returns connection information in the remaining members of <b>USB_NODE_CONNECTION_INFORMATION_EX</b>. 
The IRP, the <b>AssociatedIrp.SystemBuffer</b> member points to the **USB_NODE_CONNECTION_INFORMATION_EX** structure.

On output, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure receives information about the indicated connection from the USB hub driver.



### -inout-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure.




### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.

## -remarks

Here is an example that shows how to get the speed of the hub port by sending this request.

The function specifies the symbolic link to hub device and port index to query. On return, pPortSpeed indicates:
- Port speed
- SPEED_PATHERROR: if unable to open path.
- SPEED_IOCTLERROR: Hub IOCTL failed.

```
void GetPortSpeed(const WCHAR *Path, ULONG PortIndex, UCHAR *pPortSpeed)

{
    if (Path == NULL) { return; }

    HANDLE handle = CreateFile(
                            Path,
                            GENERIC_WRITE | GENERIC_READ,
                            FILE_SHARE_WRITE | FILE_SHARE_READ,
                            NULL,
                            OPEN_EXISTING,
                            NULL,
                            NULL
                        );

    if (handle == INVALID_HANDLE_VALUE)
    {
      *pPortSpeed = SPEED_PATHERROR;
      return;
    }

    PUSB_NODE_CONNECTION_INFORMATION_EX ConnectionInfo =
                    (PUSB_NODE_CONNECTION_INFORMATION_EX)
                    malloc(sizeof(USB_NODE_CONNECTION_INFORMATION_EX));

    ConnectionInfo->ConnectionIndex = PortIndex;

    ULONG bytes = 0;
    BOOL success = DeviceIoControl(handle,
                              IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX,
                              ConnectionInfo,
                              sizeof(USB_NODE_CONNECTION_INFORMATION_EX),
                              ConnectionInfo,
                              sizeof(USB_NODE_CONNECTION_INFORMATION_EX),
                              &bytes,
                              NULL);

    CloseHandle(handle);

    if (success == FALSE)
    {
      *pPortSpeed = SPEED_IOCTLERROR;
      return;
    }

    *pPortSpeed = (UCHAR)ConnectionInfo->Speed;
}

```


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a>
 

 

