---
UID: NC:minitape.TAPE_EXTENSION_INIT_ROUTINE
title: TAPE_EXTENSION_INIT_ROUTINE
author: windows-driver-content
description: ExtensionInit initializes an optional, driver-specific context area. This routine is called by TapeClassInitialize when the tape miniclass driver is loaded. This routine is optional.
old-location: storage\tapeminiextensioninit.htm
old-project: storage
ms.assetid: 4837b9c2-a3c1-4574-8f5b-4bf7c7d037a0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "(*TAPE_EXTENSION_INIT_ROUTINE), (*TAPE_EXTENSION_INIT_ROUTINE) routine [Storage Devices], TAPE_EXTENSION_INIT_ROUTINE, minitape/(*TAPE_EXTENSION_INIT_ROUTINE), storage.tapeminiextensioninit, tapemini_858bcb61-472e-45c4-8438-060eb61f1c4a.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	minitape.h
api_name:
-	(*TAPE_EXTENSION_INIT_ROUTINE)
product:
- Windows
targetos: Windows
req.typenames: 
---

# TAPE_EXTENSION_INIT_ROUTINE callback function


## -description


<i>ExtensionInit</i> initializes an optional, driver-specific context area. This routine is called by <a href="https://msdn.microsoft.com/library/windows/hardware/ff567619">TapeClassInitialize</a> when the tape miniclass driver is loaded. This routine is optional.


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



A tape miniclass driver requests a minitape extension by specifying a nonzero value for <b>MinitapeExtensionSize</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567968">TAPE_INIT_DATA_EX</a> structure it passes to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567619">TapeClassInitialize</a> from its <b>DriverEntry</b> routine. A miniclass driver defines the structure and contents of the minitape extension and typically uses it to store inquiry data for the devices it supports.

The tape class driver allocates the minitape extension and supplies it subsequently in calls to to the tape miniclass driver's routines that handle the device-specific aspects of device-control requests and to the miniclass driver's optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff567955">TapeMiniTapeError</a> routine.

<i>ExtensionInit</i> initializes the minitape extension, and the miniclass driver uses this area to maintain run-time state for its device. The tape class driver passes <i>InquiryData</i> and a <i>ModeCapabilitiesPage</i> to this routine because those structures contain information that a tape miniclass driver might want to store in the minitape extension.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552656">DriverEntry of Tape Miniclass Driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567968">TAPE_INIT_DATA_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567975">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567619">TapeClassInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567955">TapeMiniTapeError</a>
 

 

