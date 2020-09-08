---
UID: NI:scsiscan.IOCTL_SCSISCAN_CMD
title: IOCTL_SCSISCAN_CMD (scsiscan.h)
description: Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses.
old-location: image\ioctl_scsiscan_cmd.htm
tech.root: image
ms.assetid: af1f4107-f537-4b94-b9b4-c97429878fef
ms.date: 05/03/2018
keywords: ["IOCTL_SCSISCAN_CMD IOCTL"]
ms.keywords: IOCTL_SCSISCAN_CMD, IOCTL_SCSISCAN_CMD control, IOCTL_SCSISCAN_CMD control code [Imaging Devices], image.ioctl_scsiscan_cmd, scsiscan/IOCTL_SCSISCAN_CMD, stifnc_da087c9b-101a-47c9-b546-ba887b05dca0.xml
req.header: scsiscan.h
req.include-header: Scsiscan.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_SCSISCAN_CMD
 - scsiscan/IOCTL_SCSISCAN_CMD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Scsiscan.h
api_name:
 - IOCTL_SCSISCAN_CMD
---

# IOCTL_SCSISCAN_CMD IOCTL


## -description

Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses.

## -ioctlparameters

### -input-buffer

Pointer to a **SCSISCAN_CMD** structure.

### -input-buffer-length

Size of the input buffer.

### -output-buffer

Pointer to a data buffer. Depending on the type of I/O operation, this buffer might supply or receive data.

### -output-buffer-length

Size of the output buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to STATUS_SUCCESS if the request is successful. Otherwise, **Status** to the appropriate error condition as a [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values) code.

## -remarks

When the **DeviceloControl** function is called with the IOCTL_SCSISCAN_CMD I/O control code, the caller must specify the address of a [SCSISCAN_CMD](https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiscan/ns-scsiscan-_scsiscan_cmd) structure as the function's *lpInBuffer* parameter. This structure specifies the type of operation being requested. The kernel-mode driver constructs a SCSI Request Block (SRB) from the SCSISCAN_CMD structure's contents.

For SCSI commands that involve data transfers, the [DeviceIoControl](https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol) function's *lpOutBuffer* must point to a data buffer. For read operations, this buffer will receive data read from the device. For write operations, the buffer must contain the data to be written.

For more information, see [Accessing Kernel-Mode Drivers for Still Image Devices](https://docs.microsoft.com/windows-hardware/drivers/image/accessing-kernel-mode-drivers-for-still-image-devices).

### Code example

```cpp
SCSISCAN_CMD  Cmd;
UCHAR         SrbStatus;

// Construct the SCSISCAN_CMD structure and
// clear out the sense buffer.
memset(&Cmd, 0, sizeof(Cmd));
memset(SenseBuffer,0, sizeof(SenseBuffer));

Cmd.Size = sizeof(SCSISCAN_CMD);
Cmd.SrbFlags = SRB_FLAGS_DATA_OUT;
Cmd.CdbLength = 6;
Cmd.SenseLength = 18;
Cmd.TransferLength = len;
Cmd.pSrbStatus = &SrbStatus;
Cmd.pSenseBuffer = SenseBuffer;

Cmd.Cdb[0] = 0x0A;
Cmd.Cdb[4] = ((PFOUR_BYTE)&len) -> Byte0;
Cmd.Cdb[3] = ((PFOUR_BYTE)&len) -> Byte1;
Cmd.Cdb[2] = ((PFOUR_BYTE)&len) -> Byte2;
Cmd.Cdb[5] = 0;

DeviceIoControl(
           gb_Scan_Handle,
           (DWORD) IOCTL_SCSISCAN_CMD,
           &Cmd,
           sizeof(Cmd),
           buf,
           len,
           amount_written_ptr,
           NULL
           );

if (SRB_STATUS_SUCCESS != SRB_STATUS(SrbStatus))
{
  fprintf(stderr, "WriteScanner error.\n");
  if (SRB_STATUS_DATA_OVERRUN == SrbStatus)
  {
    fprintf(stderr, "Data over/under run. This is ok.\n");
  }
  else if ((SenseBuffer[2] & 0xf) == SCSI_SENSE_UNIT_ATTENTION)
  {
    fprintf(stderr, "Unit attention.  Retrying request....\n");
    memset(SenseBuffer,0, sizeof(SenseBuffer));
    SrbStatus = 0;
    DeviceIoControl(
      gb_Scan_Handle,
      (DWORD) IOCTL_SCSISCAN_CMD,
      &Cmd,
      sizeof(Cmd),
      buf,
      len,
      amount_written_ptr,
      NULL
      );
    }
  }
}
```

## -see-also

[Creating IOCTL Requests in Drivers](https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-ioctl-requests-in-drivers)

[WdfIoTargetSendInternalIoctlOthersSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously)

[WdfIoTargetSendInternalIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously)

[WdfIoTargetSendIoctlSynchronously](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously)

