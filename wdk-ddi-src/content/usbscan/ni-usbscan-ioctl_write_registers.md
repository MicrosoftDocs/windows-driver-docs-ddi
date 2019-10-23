---
UID: NI:usbscan.IOCTL_WRITE_REGISTERS
title: IOCTL_WRITE_REGISTERS (usbscan.h)
description: Writes to USB device registers, using the control pipe.
old-location: image\ioctl_write_registers.htm
tech.root: image
ms.assetid: c7175b39-9db2-4903-bb50-bb0c97fda471
ms.date: 05/03/2018
ms.keywords: IOCTL_WRITE_REGISTERS, IOCTL_WRITE_REGISTERS control, IOCTL_WRITE_REGISTERS control code [Imaging Devices], image.ioctl_write_registers, stifnc_e994c3b6-35b9-4b5f-aaba-72fedeb9e08f.xml, usbscan/IOCTL_WRITE_REGISTERS
ms.topic: ioctl
f1_keywords:
 - "usbscan/IOCTL_WRITE_REGISTERS"
req.header: usbscan.h
req.include-header: Usbscan.h
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
- Usbscan.h
api_name:
- IOCTL_WRITE_REGISTERS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_WRITE_REGISTERS IOCTL

## -description

Writes to USB device registers, using the control pipe.

## -ioctlparameters

### -input-buffer

Pointer to an [IO_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_io_block) structure.

### -input-buffer-length

Size of the input buffer.

### -output-buffer

NULL

### -output-buffer-length

Zero

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) code.

## -remarks

### DeviceIoControl Parameters

When the **DeviceloControl** function is called with the IOCTL_WRITE_REGISTERS I/O control code, the caller must specify the address of an [IO_BLOCK](https://docs.microsoft.com/windows-hardware/drivers/ddi/usbscan/ns-usbscan-_io_block) structure as the function's *lpInBuffer* parameter.

Using the IO_BLOCK contents, the kernel-mode driver creates a [URB](https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb) that contains a [_URB_CONTROL_VENDOR_OR_CLASS_REQUEST](https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_vendor_or_class_request) structure.

The following table indicates the values assigned to _URB_CONTROL_VENDOR_OR_CLASS_REQUEST structure members.

| Structure member | Value sssigned |
| --- | --- |
| **TransferFlags** | 0 |
| **TransferBufferLength** | *pIoBlock*->**uLength** |
| **TransferBuffer** | *pIoBlock*->**pbyData** |
| **TransferBufferMDL** | **NULL** |
| **RequestTypeReservedBits** | 0x40 |
| **Request** | (*pIoBlock*->**uLength** > 1) ? 0x04 : 0x0C |
| **Value** | (SHORT)*pIoBlock*->**uOffset** |
| **Index** | *pIoBlock*->**uIndex** |

For more information, see [Accessing Kernel-Mode Drivers for Still Image Devices](https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices).

```cpp
DWORD             cbRet;
BOOL              bRet;
IO_BLOCK          IoBlock;
OVERLAPPED        overlapped;

IoBlock.uOffset = (BYTE)byOffset;
IoBlock.uLength = (BYTE)byNbOfReg;
IoBlock.pbyData = pbyData;

memset(&overlapped, 0, sizeof(OVERLAPPED));
overlapped.hEvent =
    CreateEvent(NULL,    // pointer to security attributes
                         // WIN95 ignores this parameter
                FALSE,   // automatic reset
                FALSE,   // initialize to not signaled
                NULL);   // pointer to the event-object name

bRet = DeviceIoControl( DeviceHandle,
                        (DWORD) IOCTL_WRITE_REGISTERS,
                        &IoBlock,
                        sizeof(IO_BLOCK),
                        NULL,
                        0,
                        &cbRet,
                        &overlapped);

if( bRet == TRUE )
{
    WaitForSingleObject(overlapped.hEvent, INFINITE);
    // we do not the test, the result is zero
}

CloseHandle(overlapped.hEvent);
```
