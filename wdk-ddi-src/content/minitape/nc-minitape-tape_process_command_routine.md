---
UID: NC:minitape.TAPE_PROCESS_COMMAND_ROUTINE
title: TAPE_PROCESS_COMMAND_ROUTINE (minitape.h)
description: TAPE_PROCESS_COMMAND_ROUTINE handles the device-specific aspects of an IOCTL request.
old-location: storage\tapeminicreatepartition.htm
tech.root: storage
ms.assetid: 6675d840-8b13-44ef-bbdb-84d683240175
ms.date: 03/29/2018
ms.keywords: "(*TAPE_PROCESS_COMMAND_ROUTINE), (*TAPE_PROCESS_COMMAND_ROUTINE) routine [Storage Devices], TAPE_PROCESS_COMMAND_ROUTINE, minitape/(*TAPE_PROCESS_COMMAND_ROUTINE), storage.tapeminicreatepartition, tapemini_34ae90ec-7f62-45f3-91e4-d64acfdbd797.xml"
ms.topic: callback
f1_keywords:
 - "minitape/(*TAPE_PROCESS_COMMAND_ROUTINE)"
req.header: minitape.h
req.include-header: Minitape.h
req.target-type: Desktop
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
- UserDefined
api_location:
- minitape.h
api_name:
- (*TAPE_PROCESS_COMMAND_ROUTINE)
product:
- Windows
targetos: Windows
req.typenames: 
---

# TAPE_PROCESS_COMMAND_ROUTINE callback function


## -description


<i>TAPE_PROCESS_COMMAND_ROUTINE</i> handles the device-specific aspects of an IOCTL request.


## -parameters




### -param MinitapeExtension [in, out]

Pointer to the driver-specific minitape extension. This is <b>NULL</b> if the miniclass driver did not request a minitape extension when it initialized.


### -param CommandExtension [in, out]

Pointer to the command extension. This is <b>NULL</b> if the miniclass driver did not request a command extension when it initialized.


### -param CommandParameters [in, out]

Pointer to a buffer allocated by the caller that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ns-ntddtape-_tape_create_partition">TAPE_CREATE_PARTITION</a> structure.


### -param Srb [in, out]

Pointer to an SRB allocated and partially filled in by the tape class driver. <i>TAPE_PROCESS_COMMAND_ROUTINE</i> must fill in the CDB in the SRB. 

<ul>
<li>
<b>Cdb</b> - Pointer to the SCSI CDB for the command. Clear the CDB with <b>TapeClassZeroMemory</b> before filling it in.

</li>
<li>
<b>CdbLength</b> - Specifies the number of bytes in the CDB.

</li>
</ul>
<i>TAPE_PROCESS_COMMAND_ROUTINE</i> might also fill in the following members in the SRB:

<ul>
<li>
<b>DataBuffer</b> - Pointer to the data buffer to be transferred. Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/nf-minitape-tapeclassallocatesrbbuffer">TapeClassAllocateSrbBuffer</a> to allocate a <b>DataBuffer</b> of length greater than or equal to <b>DataTransferLength</b>.

</li>
<li>
<b>DataTransferLength</b> - Specifies the number of bytes to be transferred in the SRB. This member is set by <b>TapeClassAllocateSrbBuffer</b>.

</li>
<li>
<b>TimeOutValue</b> - Specifies a time-out value for this command, overriding the default time-out value from the tape class driver's device extension.

</li>
<li>
<b>SrbFlags</b> - Specifies a flag for this command. The tape miniclass driver must set SRB_FLAGS_DATA_OUT if the SRB is sending data to the tape drive. This member can be zero if the SRB is requesting data from the tape drive or if no data is being transferred by the command.

</li>
</ul>

### -param CallNumber [in]

Specifies the number of times <i>TAPE_PROCESS_COMMAND_ROUTINE</i> has been called to process a given tape command. <i>CallNumber</i> is zero the first time this routine is called and is incremented for each subsequent call until the miniclass driver returns a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/ne-minitape-_tape_status">TAPE_STATUS</a> value that indicates the command is complete.


### -param StatusOfLastCommand [in, optional]

Specifies the status of the last command. In the first call to <i>TAPE_PROCESS_COMMAND_ROUTINE</i> to process a given request, <i>StatusOfLastCommand </i>is TAPE_STATUS_SUCCESS. In subsequent calls, <i>StatusOfLastCommand </i>is either TAPE_STATUS_SUCCESS or an error status if an error occurred and the tape miniclass driver set RETURN_ERRORS in <i>RetryFlags</i> in the previous call. 


### -param RetryFlags [in, out]

Pointer to a variable that specifies what action the tape class driver should take when a tape device reports an error.

The low-order word specifies the number of retries to perform in the event of a SCSI command failure. The default is zero (no retries).

The high-order word contains flags that specify how the tape class driver should return control if an error occurs:

<ul>
<li>
If RETURN_ERRORS and IGNORE_ERRORS are clear (the default) the tape class driver returns a failure status to the original requester.

</li>
<li>
If the miniclass driver sets RETURN_ERRORS, the tape class driver calls <i>TAPE_PROCESS_COMMAND_ROUTINE</i> with <i>StatusOfLastCommand</i> set to a failure status.

</li>
<li>
If the miniclass driver sets IGNORE_ERRORS, the tape class driver converts a failure status to success and calls <i>TAPE_PROCESS_COMMAND_ROUTINE</i> with <i>StatusOfLastCommand </i>set to success.

</li>
</ul>

## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>TAPE_STATUS_SEND_SRB_AND_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
Indicates to the tape class driver that the SRB has been filled in and is ready to be sent to the target device. By default, the tape class driver calls <i>TAPE_PROCESS_COMMAND_ROUTINE</i> again only if the SRB succeeds. A miniclass driver can modify the default behavior by setting <i>RetryFlags</i> before returning from <i>TAPE_PROCESS_COMMAND_ROUTINE</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>TAPE_STATUS_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
Directs the tape class driver to increment <i>CallNumber</i> and call <i>TAPE_PROCESS_COMMAND_ROUTINE</i> again without sending an SRB to the tape device. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>TAPE_STATUS_CHECK_TEST_UNIT_READY</b></dt>
</dl>
</td>
<td width="60%">
Directs the tape class driver to fill in an SRB for the TEST UNIT READY command and send the SRB to the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>TAPE_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
Any other return code indicates to the tape class driver that the command is complete and indicates success, failure, or warning. Possible completion return values for this routine include, but are not limited to:

<dl>
<dd>
TAPE_STATUS_SUCCESS

</dd>
<dd>
TAPE_STATUS_INSUFFICIENT_RESOURCES

</dd>
<dd>
TAPE_STATUS_INVALID_DEVICE_REQUEST

</dd>
<dd>
TAPE_STATUS_INVALID_PARAMETER

</dd>
<dd>
TAPE_STATUS_IO_DEVICE_ERROR

</dd>
<dd>
TAPE_STATUS_MEDIA_WRITE_PROTECTED

</dd>
<dd>
TAPE_STATUS_NOT_IMPLEMENTED

</dd>
</dl>
</td>
</tr>
</table>
 




## -remarks



The following functions can be assigned to this callback placeholder:

<h3><a id="CreatePartition"></a><a id="createpartition"></a><a id="CREATEPARTITION"></a>CreatePartition</h3>
<i>CreatePartition</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_create_partition">IOCTL_TAPE_CREATE_PARTITION</a> request. This routine is required. <i>CreatePartition</i> creates a partition on a tape by filling in the CDB in an SRB passed by the tape class driver. Creating a partition typically requires a series of SRBs to complete the operation. After <i>CreatePartition</i> fills in a given SRB and returns, the tape class driver sends the SRB to the target device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>TapeMiniCreatePartition</i> again.

<i>CreatePartition</i> must fill in the following members in the SRB before returning to the tape class driver:

If the tape miniclass driver stores partition information in the minitape extension, <i>CreatePartition</i> updates the extension before returning to the tape class driver with TAPE_STATUS_SUCCESS.

<h3><a id="Erase"></a><a id="erase"></a><a id="ERASE"></a>Erase</h3>
<i>Erase</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_erase">IOCTL_TAPE_ERASE</a> request. This routine is required. <i>Erase</i> erases a tape by filling in the CDB in an SRB passed by the tape class driver. Erasing a tape typically requires one SRB to complete the operation. After <i>Erase</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>Erase</i> again. <i>Erase</i> then returns TAPE_STATUS_SUCCESS.

<h3><a id="GetDriveParameters"></a><a id="getdriveparameters"></a><a id="GETDRIVEPARAMETERS"></a>GetDriveParameters</h3>
<i>GetDriveParameters</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_get_drive_params">IOCTL_TAPE_GET_DRIVE_PARAMS</a> request. This routine is required. <i>GetDriveParameters</i> gets tape drive parameters by filling in the CDB in an SRB passed by the tape class driver. Getting drive parameters typically requires a series of SRBs to complete the operation. After <i>GetDriveParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the target device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>GetDriveParameters</i> again. 

<h3><a id="GetMediaParameters"></a><a id="getmediaparameters"></a><a id="GETMEDIAPARAMETERS"></a>GetMediaParameters</h3>
<i>GetMediaParameters</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_get_media_params">IOCTL_TAPE_GET_MEDIA_PARAMS</a> request. This routine is required. <i>GetMediaParameters</i> gets tape media parameters by filling in the CDB in an SRB passed by the tape class driver. Getting media parameters typically requires more than one SRB to complete the operation, starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

After <i>GetMediaParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls GetMediaParameters again. 

<h3><a id="GetMediaTypes"></a><a id="getmediatypes"></a><a id="GETMEDIATYPES"></a>GetMediaTypes</h3>
<i>GetMediaTypes</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddstor/ni-ntddstor-ioctl_storage_get_media_types_ex">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request. This routine is required. <i>GetMediaTypes</i> gets information about the media types supported by a tape device by filling in the CDB in an SRB passed by the tape class driver. Getting media types typically requires more than one SRB to complete the operation, starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

<h3><a id="GetPosition"></a><a id="getposition"></a><a id="GETPOSITION"></a>GetPosition</h3>
<i>GetPosition</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_get_position">IOCTL_TAPE_GET_POSITION</a> request. This routine is required. <i>GetPosition</i> reads the position of a tape by filling in the CDB in an SRB passed by the tape class driver. Reading tape position typically requires more than one SRB to complete the operation, often starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

<h3><a id="GetStatus"></a><a id="getstatus"></a><a id="GETSTATUS"></a>GetStatus</h3>
<i>GetStatus</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_get_status">IOCTL_TAPE_GET_STATUS</a> request. This routine is required. <i>GetStatus</i> reads the status of a tape device, typically by directing the tape class driver to issue a test unit ready command. 

If a device indicates whether a drive needs cleaning in sense data (as opposed to reporting the need for cleaning as an error, which a miniclass driver would handle in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/nc-minitape-tape_error_routine">TapeMiniTapeError</a> routine), <i>GetStatus</i> fills in the CDB in the SRB passed by the tape class driver to obtain the sense data and, if necessary, returns TAPE_STATUS_REQUIRES_CLEANING.

<h3><a id="Prepare"></a><a id="prepare"></a><a id="PREPARE"></a>Prepare</h3>
<i>Prepare</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_prepare">IOCTL_TAPE_PREPARE</a> request. This routine is required. <i>Prepare</i> prepares a tape by filling in the CDB in an SRB passed by the tape class driver. If the device supports the requested operation, preparing a tape typically requires one SRB. After <i>Prepare</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>Prepare</i> again.

<h3><a id="SetDriveParameters"></a><a id="setdriveparameters"></a><a id="SETDRIVEPARAMETERS"></a>SetDriveParameters</h3>
<i>SetDriveParameters</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_set_drive_params">IOCTL_TAPE_SET_DRIVE_PARAMS</a> request. This routine is required. <i>SetDriveParameters</i> sets parameters for a tape device by filling in the CDB in an SRB passed by the tape class driver. Setting parameters typically involves a series of SRBs to complete the operation. After <i>SetDriveParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>SetDriveParameters</i> again.

<h3><a id="SetMediaParameters"></a><a id="setmediaparameters"></a><a id="SETMEDIAPARAMETERS"></a>SetMediaParameters</h3>
<i>SetMediaParameters</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_set_media_params">IOCTL_TAPE_SET_MEDIA_PARAMS</a> request. This routine is required. <i>SetMediaParameters</i> sets the block size of a tape by filling in the CDB in an SRB passed by the tape class driver. Setting the block size typically requires more than one SRB to complete the operation, starting with a test unit ready which the miniclass driver requests by returning TAPE_STATUS_CHECK_TEST_UNIT_READY the first time the tape class driver calls the routine. 

After <i>SetMediaParameters</i> fills in a given SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>SetMediaParameters</i> again. 

<h3><a id="SetPosition"></a><a id="setposition"></a><a id="SETPOSITION"></a>SetPosition</h3>
<i>SetPosition</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_set_position">IOCTL_TAPE_SET_POSITION</a> request. This routine is required. <i>SetPosition</i> sets the position of a tape by filling in the CDB in an SRB passed by the tape class driver. Setting the position typically requires one SRB. After <i>SetPosition</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>SetPosition</i> again. <i>SetPosition</i> then returns TAPE_STATUS_SUCCESS.

<h3><a id="WriteMarks"></a><a id="writemarks"></a><a id="WRITEMARKS"></a>WriteMarks</h3>
<i>WriteMarks</i> handles the device-specific aspects of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddtape/ni-ntddtape-ioctl_tape_write_marks">IOCTL_TAPE_WRITE_MARKS</a> request. This routine is required. <i>WriteMarks</i> writes marks to a tape by filling in the CDB in an SRB passed by the tape class driver. Writing marks typically takes one SRB to complete the operation. After <i>WriteMarks</i> fills in the SRB and returns, the tape class driver sends the SRB to the device and, depending on the result of the SRB and the value of <i>RetryFlags</i>, calls <i>WriteMarks</i> again. <i>WriteMarks</i> then returns TAPE_STATUS_SUCCESS. 

<h3><a id="PreProcessReadWrite"></a><a id="preprocessreadwrite"></a><a id="PREPROCESSREADWRITE"></a>PreProcessReadWrite</h3>
<i>PreProcessReadWrite</i> is an optional, special-purpose routine that performs any device-specific operations required before read and write operations. Most tape miniclass drivers do not need this routine. The activities of the <i>PreProcessReadWrite</i> routine are device specific. The routine can use the information passed to it by the class driver to implement special preprocessing for reads and writes. If a drive has limited capabilities, the driver may need this routine to maintain coherent state, for example.

If a tape miniclass driver sets a non-<b>NULL</b> entry point for this routine in the TAPE_INIT_DATA_EX structure it passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/nf-minitape-tapeclassinitialize">TapeClassInitialize</a> from its <b>DriverEntry</b> routine, the tape class driver calls it before each read and write operation on the tape device. The class driver does not expect any information back from this routine.

<h3><a id="WMIOperations"></a><a id="wmioperations"></a><a id="WMIOPERATIONS"></a>WMIOperations</h3>
<i>WMIOperations</i> is the common entry point for all WMI calls from the tape class driver. A minidriver that supports WMI should set the function pointer member, <b>WMIOperations</b>, in the structure TAPE_INIT_DATA_EX to point to the minidriver's <i>TAPE_PROCESS_COMMAND_ROUTINE</i> routine. The minidriver should do this in its DriverEntry routine before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/nf-minitape-tapeclassinitialize">TapeClassInitialize</a>. If a minidriver does not support WMI operations, it should set TapeWMIOperations field to <b>NULL</b>.

The tape class driver assigns values to the members of TAPE_WMI_OPERATIONS structure, and passes this structure to minidriver's <i>WMIOperations</i> routine in the <i>CommandParameters</i> parameter. As with other minidriver routines, <i>WMIOperations</i> fills, creates, and initializes the SCSI request blocks (SRB) and the command descriptor blocks (CDB) required to implement the indicated WMI method, and returns control to tape class driver. The tape class driver then calls the port driver to execute the request. 

The minidriver returns the WMI data in the buffer pointed to by the <b>DataBuffer</b> member of the TAPE_WMI_OPERATIONS structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/ne-minitape-_tape_status">TAPE_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/nf-minitape-tapeclassallocatesrbbuffer">TapeClassAllocateSrbBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/minitape/nf-minitape-tapeclasszeromemory">TapeClassZeroMemory</a>
 

 

