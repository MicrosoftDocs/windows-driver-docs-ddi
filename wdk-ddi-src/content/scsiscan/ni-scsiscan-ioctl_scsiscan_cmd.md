---
UID: NI:scsiscan.IOCTL_SCSISCAN_CMD
title: IOCTL_SCSISCAN_CMD
author: windows-driver-content
description: Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses.
old-location: image\ioctl_scsiscan_cmd.htm
old-project: image
ms.assetid: af1f4107-f537-4b94-b9b4-c97429878fef
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.ioctl_scsiscan_cmd, IOCTL_SCSISCAN_CMD control code [Imaging Devices], IOCTL_SCSISCAN_CMD, scsiscan/IOCTL_SCSISCAN_CMD, stifnc_da087c9b-101a-47c9-b546-ba887b05dca0.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Scsiscan.h
apiname:
-	IOCTL_SCSISCAN_CMD
product: Windows
targetos: Windows
req.typenames: "*PZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR"
req.product: Windows 10 or later.
---

# IOCTL_SCSISCAN_CMD IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


Creates a customized SCSI control descriptor block (CDB) and sends it to the kernel-mode still image driver for SCSI buses.


## -ioctlparameters




### -input-buffer

Pointer to a <b>SCSISCAN_CMD</b> structure.


### -input-buffer-length

Size of the input buffer.


### -output-buffer

Pointer to a data buffer. Depending on the type of I/O operation, this buffer might supply or receive data.


### -output-buffer-length

Size of the output buffer.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


When the <b>DeviceloControl</b> function is called with the IOCTL_SCSISCAN_CMD I/O control code, the caller must specify the address of a <a href="..\scsiscan\ns-scsiscan-_scsiscan_cmd.md">SCSISCAN_CMD</a> structure as the function's <i>lpInBuffer</i> parameter. This structure specifies the type of operation being requested. The kernel-mode driver constructs a SCSI Request Block (SRB) from the SCSISCAN_CMD structure's contents.

For SCSI commands that involve data transfers, the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> function's <i>lpOutBuffer</i> must point to a data buffer. For read operations, this buffer will receive data read from the device. For write operations, the buffer must contain the data to be written.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

<b>Code example</b>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>SCSISCAN_CMD  Cmd;
UCHAR         SrbStatus;

// Construct the SCSISCAN_CMD structure and
// clear out the sense buffer.
memset(&amp;Cmd, 0, sizeof(Cmd));
memset(SenseBuffer,0, sizeof(SenseBuffer));

Cmd.Size = sizeof(SCSISCAN_CMD);
Cmd.SrbFlags = SRB_FLAGS_DATA_OUT;
Cmd.CdbLength = 6;
Cmd.SenseLength = 18;
Cmd.TransferLength = len;
Cmd.pSrbStatus = &amp;SrbStatus;
Cmd.pSenseBuffer = SenseBuffer;

Cmd.Cdb[0] = 0x0A;
Cmd.Cdb[4] = ((PFOUR_BYTE)&amp;len) -&gt; Byte0;
Cmd.Cdb[3] = ((PFOUR_BYTE)&amp;len) -&gt; Byte1;
Cmd.Cdb[2] = ((PFOUR_BYTE)&amp;len) -&gt; Byte2;
Cmd.Cdb[5] = 0;

DeviceIoControl(
           gb_Scan_Handle,
           (DWORD) IOCTL_SCSISCAN_CMD,
           &amp;Cmd,
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
  else if ((SenseBuffer[2] &amp; 0xf) == SCSI_SENSE_UNIT_ATTENTION)
  {
    fprintf(stderr, "Unit attention.  Retrying request....\n");
    memset(SenseBuffer,0, sizeof(SenseBuffer));
    SrbStatus = 0;
    DeviceIoControl(
      gb_Scan_Handle,
      (DWORD) IOCTL_SCSISCAN_CMD,
      &amp;Cmd,
      sizeof(Cmd),
      buf,
      len,
      amount_written_ptr,
      NULL
      );
    }
  }
}</pre>
</td>
</tr>
</table></span></div>


## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IOCTL_SCSISCAN_CMD control code%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

