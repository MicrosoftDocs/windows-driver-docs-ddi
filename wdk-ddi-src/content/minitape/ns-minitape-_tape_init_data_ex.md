---
UID: NS:minitape._TAPE_INIT_DATA_EX
title: _TAPE_INIT_DATA_EX (minitape.h)
description: TAPE_INIT_DATA_EX defines values and routines that are specific to a Windows 2000 tape miniclass driver. The tape miniclass DriverEntry routine passes this information to the tape class driver to complete miniclass driver initialization.
old-location: storage\tape_init_data_ex.htm
tech.root: storage
ms.assetid: 438c736e-c9be-4a75-a062-4614ea7fe028
ms.date: 03/29/2018
keywords: ["_TAPE_INIT_DATA_EX structure"]
ms.keywords: "*PTAPE_INIT_DATA_EX, PTAPE_INIT_DATA_EX, PTAPE_INIT_DATA_EX structure pointer [Storage Devices], TAPE_INIT_DATA_EX, TAPE_INIT_DATA_EX structure [Storage Devices], _TAPE_INIT_DATA_EX, minitape/PTAPE_INIT_DATA_EX, minitape/TAPE_INIT_DATA_EX, storage.tape_init_data_ex, structs-tape_69291d6d-0f9e-4b6b-bb66-c40757bb5c69.xml"
f1_keywords:
 - "minitape/TAPE_INIT_DATA_EX"
 - "TAPE_INIT_DATA_EX"
req.header: minitape.h
req.include-header: Minitape.h
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
- minitape.h
api_name:
- TAPE_INIT_DATA_EX
product:
- Windows
targetos: Windows
req.typenames: TAPE_INIT_DATA_EX, *PTAPE_INIT_DATA_EX
---

# _TAPE_INIT_DATA_EX structure


## -description


TAPE_INIT_DATA_EX defines values and routines that are specific to a Windows 2000 tape miniclass driver. The tape miniclass <b>DriverEntry</b> routine passes this information to the tape class driver to complete miniclass driver initialization. 


## -struct-fields




### -field InitDataSize



#### 



##### 


### -field VerifyInquiry

Specifies the entry point of the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_verify_inquiry_routine">TapeMiniVerifyInquiry</a> routine, which determines whether the driver supports a given device. This routine is required.


### -field QueryModeCapabilitiesPage

Directs the tape class driver when <b>TRUE</b> to pass a mode capabilities page to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_verify_inquiry_routine">TapeMiniVerifyInquiry</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_extension_init_routine">TapeMiniExtensionInit</a> routines.


### -field MinitapeExtensionSize

Specifies the size, in bytes, of a driver-specific context area. If this member is nonzero, <b>ExtensionInit </b>must not be <b>NULL</b>. This value is optional and must be set to zero if not used. 


### -field ExtensionInit

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_extension_init_routine">TapeMiniExtensionInit</a> routine, which initializes an optional minitape extension, if any. If <b>MiniTapeExtensionSize</b> is zero, <b>ExtensionInit</b> must be <b>NULL</b>.


### -field DefaultTimeOutValue

Specifies the number of seconds that the tape class driver waits for an SRB request before canceling it. If this value is zero, the tape class driver sets an appropriate default value. The tape class driver always uses the default time-out value for read and write requests. The routines contained in the TAPE_INIT_DATA_EX structure can override the default time-out value for device control requests by setting <b>TimeOutValue</b> in an SRB.


### -field TapeError

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_error_routine">TapeMiniTapeError</a> routine, which augments the error-handling activities of the tape class driver. This routine is optional. If one is not used, <b>TapeError</b> must be set to <b>NULL</b>.


### -field CommandExtensionSize

Specifies the size, in bytes, of a command extension to be allocated before the start of each tape command. A tape miniclass driver uses the command extension to store context during the processing of tape commands. Its size and internal structure are defined by the tape miniclass driver. A command extension is optional. If one is not used, <b>CommandExtensionSize</b> must be set to zero.


### -field CreatePartition

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniCreatePartition</a> routine, which creates a partition on a tape. This routine is required.


### -field Erase

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniErase</a> routine, which erases a tape. This routine is required.


### -field GetDriveParameters

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetDriveParameters</a> routine, which handles requests to get drive parameters. This routine is required.


### -field GetMediaParameters

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetMediaParameters</a> routine, which handles requests to get media parameters. This routine is required.


### -field GetPosition

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetPosition</a> routine, which handles requests to get the position of a tape. This routine is required.


### -field GetStatus

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetStatus</a> routine, which handles requests for status. This routine is required.


### -field Prepare

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniPrepare</a> routine, which prepares a tape device. This routine is required.


### -field SetDriveParameters

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetDriveParameters</a> routine, which sets drive parameters. This routine is required.


### -field SetMediaParameters

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetMediaParameters</a> routine, which sets media parameters. This routine is required.


### -field SetPosition

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetPosition</a> routine, which positions a tape. This routine is required.


### -field WriteMarks

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniWriteMarks</a> routine, which writes marks to tape. This routine is required.


### -field PreProcessReadWrite

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniPreProcessReadWrite</a> routine, which executes device-specific operations before all reads and writes. This routine is optional and is not needed by most drivers. If one is not used, <b>PreProcessReadWrite</b> must be <b>NULL</b>.


### -field TapeGetMediaTypes

Pointer to the tape miniclass driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetMediaTypes</a> routine, which gets a description of each media type supported by a tape device. This routine is required.


### -field MediaTypesSupported

Indicates the number of media types supported by the device.


### -field TapeWMIOperations

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniWMIControl</a> routine. 


### -field Reserved

Reserved. 


## -remarks



A tape miniclass driver's <b>DriverEntry </b>routine calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nf-minitape-tapeclasszeromemory">TapeClassZeroMemory</a> to clear TAPE_INIT_DATA_EX, fills in the required members and any appropriate optional members, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nf-minitape-tapeclassinitialize">TapeClassInitialize</a> with a pointer to this structure.

The names of the tape miniclass driver routines indicated in the member descriptions of this structure are just placeholder names. The prototype for these routines is declared in <i>newtape.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
TAPE_STATUS
(*TAPE_PROCESS_COMMAND_ROUTINE)(
  IN OUT PVOID  MinitapeExtension,
  IN OUT PVOID  CommandExtension,
  IN OUT PVOID  CommandParameters,
  IN OUT PSCSI_REQUEST_BLOCK  Srb,
  IN ULONG  CallNumber,
  IN TAPE_STATUS  StatusOfLastCommand,
  IN OUT PULONG  RetryFlags
  );</pre>
</td>
</tr>
</table></span></div>
The meaning of this prototype's parameters are different for each miniclass driver routine. For detailed information about how these parameters are used see the descriptions for each individual miniclass driver routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-tape-miniclass-driver">DriverEntry of Tape Miniclass Driver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nf-minitape-tapeclassinitialize">TapeClassInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nf-minitape-tapeclasszeromemory">TapeClassZeroMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniCreatePartition</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniErase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_extension_init_routine">TapeMiniExtensionInit</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetDriveParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetMediaParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetMediaTypes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetPosition</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniGetStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniPrepare</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetDriveParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetMediaParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniSetPosition</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_error_routine">TapeMiniTapeError</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_verify_inquiry_routine">TapeMiniVerifyInquiry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniWriteMarks</a>
 

 

