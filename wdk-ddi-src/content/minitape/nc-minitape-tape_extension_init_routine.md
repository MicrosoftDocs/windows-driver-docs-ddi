---
UID: NC:minitape.TAPE_EXTENSION_INIT_ROUTINE
title: TAPE_EXTENSION_INIT_ROUTINE
author: windows-driver-content
description: ExtensionInit initializes an optional, driver-specific context area. This routine is called by TapeClassInitialize when the tape miniclass driver is loaded. This routine is optional.
old-location: storage\tapeminiextensioninit.htm
old-project: storage
ms.assetid: 4837b9c2-a3c1-4574-8f5b-4bf7c7d037a0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.tapeminiextensioninit, (*TAPE_EXTENSION_INIT_ROUTINE) routine [Storage Devices], (*TAPE_EXTENSION_INIT_ROUTINE), TAPE_EXTENSION_INIT_ROUTINE, TAPE_EXTENSION_INIT_ROUTINE, minitape/(*TAPE_EXTENSION_INIT_ROUTINE), tapemini_858bcb61-472e-45c4-8438-060eb61f1c4a.xml
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
-	(*TAPE_EXTENSION_INIT_ROUTINE)
product: Windows
targetos: Windows
req.typenames: *PPROCESSOR_NUMBER, PROCESSOR_NUMBER
---

# TAPE_EXTENSION_INIT_ROUTINE callback


## -description


<i>ExtensionInit</i> initializes an optional, driver-specific context area. This routine is called by <a href="..\minitape\nf-minitape-tapeclassinitialize.md">TapeClassInitialize</a> when the tape miniclass driver is loaded. This routine is optional.


## -prototype


````
TAPE_EXTENSION_INIT_ROUTINE (*TAPE_EXTENSION_INIT_ROUTINE);

VOID (*TAPE_EXTENSION_INIT_ROUTINE)(
  _In_ PVOID                   MinitapeExtension,
  _In_ PINQUIRYDATA            InquiryData,
  _In_ PMODE_CAPABILITIES_PAGE ModeCapabilitiesPage
)
{ ... }
````


## -parameters




### -param MinitapeExtension [in]

Pointer to a buffer of the size requested by the tape miniclass driver when it initialized.


### -param InquiryData [in]

Pointer to the SCSI inquiry data for the tape device.


### -param ModeCapabilitiesPage [in]

Pointer to a buffer that contains low-level information for the tape device. The format of this page is defined by the QIC 157 standard and is subject to change. This is <b>NULL</b> if the device does not support a mode capabilities page. 


## -returns


None



## -remarks


A tape miniclass driver requests a minitape extension by specifying a nonzero value for <b>MinitapeExtensionSize</b> in the <a href="..\minitape\ns-minitape-_tape_init_data_ex.md">TAPE_INIT_DATA_EX</a> structure it passes to <a href="..\minitape\nf-minitape-tapeclassinitialize.md">TapeClassInitialize</a> from its <b>DriverEntry</b> routine. A miniclass driver defines the structure and contents of the minitape extension and typically uses it to store inquiry data for the devices it supports.

The tape class driver allocates the minitape extension and supplies it subsequently in calls to to the tape miniclass driver's routines that handle the device-specific aspects of device-control requests and to the miniclass driver's optional <a href="..\minitape\nc-minitape-tape_error_routine.md">TapeMiniTapeError</a> routine.

<i>ExtensionInit</i> initializes the minitape extension, and the miniclass driver uses this area to maintain run-time state for its device. The tape class driver passes <i>InquiryData</i> and a <i>ModeCapabilitiesPage</i> to this routine because those structures contain information that a tape miniclass driver might want to store in the minitape extension.



## -see-also

<a href="..\minitape\ne-minitape-_tape_status.md">TAPE_STATUS</a>

<a href="..\minitape\nf-minitape-tapeclassinitialize.md">TapeClassInitialize</a>

<a href="..\minitape\ns-minitape-_tape_init_data_ex.md">TAPE_INIT_DATA_EX</a>

<a href="..\minitape\nc-minitape-tape_error_routine.md">TapeMiniTapeError</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552656">DriverEntry of Tape Miniclass Driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_EXTENSION_INIT_ROUTINE routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

