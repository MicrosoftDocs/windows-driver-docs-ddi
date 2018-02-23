---
UID: NC:minitape.TAPE_ERROR_ROUTINE
title: TAPE_ERROR_ROUTINE
author: windows-driver-content
description: TAPE_ERROR_ROUTINE provides device-specific error handling when an SRB is completed with an error status. This routine is optional.
old-location: storage\tapeminitapeerror.htm
old-project: storage
ms.assetid: a39fac12-f284-4b3a-a9ab-ae75934f810e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.tapeminitapeerror, (*TAPE_ERROR_ROUTINE) routine [Storage Devices], (*TAPE_ERROR_ROUTINE), TAPE_ERROR_ROUTINE, TAPE_ERROR_ROUTINE, minitape/(*TAPE_ERROR_ROUTINE), tapemini_cf0f724e-63c4-4923-a59e-508c45dac6d9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	minitape.h
apiname:
-	(*TAPE_ERROR_ROUTINE)
product: Windows
targetos: Windows
req.typenames: "*PPROCESSOR_NUMBER, PROCESSOR_NUMBER"
---

# TAPE_ERROR_ROUTINE callback


## -description


<i>TAPE_ERROR_ROUTINE</i> provides device-specific error handling when an SRB is completed with an error status. This routine is optional.


## -prototype


````
TAPE_ERROR_ROUTINE (*TAPE_ERROR_ROUTINE);

VOID (*TAPE_ERROR_ROUTINE)(
  _In_    PVOID               MinitapeExtension,
  _In_    PSCSI_REQUEST_BLOCK Srb,
  _Inout_ PTAPE_STATUS        TapeStatus
)
{ ... }
````


## -parameters




### -param MinitapeExtension [in]

Pointer to the driver-specific minitape extension. This is <b>NULL</b> if the miniclass driver did not request a minitape extension when it initialized.


### -param Srb [in]

Pointer to the SRB for the operation that failed.


### -param TapeStatus [in, out]

Pointer to the <a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a> set by the tape class driver. The tape miniclass driver can change the TAPE_STATUS or leave it unchanged.


## -returns



  None.




## -remarks



Most tape miniclass drivers do not provide a <i>TAPE_ERROR_ROUTINE</i> routine because the <a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a> codes set by the tape class driver are appropriate.

For some devices, however, a tape miniclass driver can identify a more appropriate error code than the tape class driver. For example, if the tape class driver returns TAPE_STATUS_BUS_RESET, the tape miniclass driver might be able to determine that the real problem is more accurately represented by TAPE_STATUS_NO_MEDIA for some devices.

A tape miniclass driver optionally specifies an entry point for its <i>TAPE_ERROR_ROUTINE</i> routine in the TAPE_INIT_DATA_EX structure it passes to <a href="..\minitape\nf-minitape-tapeclassinitialize.md">TapeClassInitialize</a> from its <b>DriverEntry</b> routine. For such a miniclass driver, when an error occurs during a read, write, or device-control command, the tape class driver sets an appropriate TAPE_STATUS code and calls the miniclass driver's <i>TAPE_ERROR_ROUTINE</i> routine with the minitape extension, the failed SRB, and the TAPE_STATUS code that would be returned.

<i>TAPE_ERROR_ROUTINE</i> determines whether to alter the status provided by the tape class driver based on the input parameters and its knowledge of the device. If the SRB_STATUS_AUTOSENSE_VALID bit is set in <b>Srb-&gt;SrbStatus</b>, then the SRB contains SCSI sense information at <b>SenseInfoBuffer</b>. The length of the buffer is <b>SenseInfoBufferLength</b>. The <i>TAPE_ERROR_ROUTINE</i> routine should examine this information along with the <b>SrbStatus</b> and <b>ScsiStatus</b> in the SRB to determine whether to change the TAPE_STATUS returned.




## -see-also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>








<a href="..\minitape\ns-minitape-_tape_init_data_ex.md">TAPE_INIT_DATA_EX</a>



<a href="..\minitape\nf-minitape-tapeclassinitialize.md">TapeClassInitialize</a>



<a href="..\minitape\ns-minitape-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>





<a href="..\minitape\ns-minitape-_tape_init_data_ex.md">TAPE_INIT_DATA_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552656">DriverEntry of Tape Miniclass Driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_ERROR_ROUTINE routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

