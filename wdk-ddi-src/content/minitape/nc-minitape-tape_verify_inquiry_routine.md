---
UID: NC:minitape.TAPE_VERIFY_INQUIRY_ROUTINE
title: TAPE_VERIFY_INQUIRY_ROUTINE
description: TAPE_VERIFY_INQUIRY_ROUTINE determines whether the tape miniclass driver recognizes and supports a given device. This routine is required.
old-location: storage\tapeminiverifyinquiry.htm
tech.root: storage
ms.assetid: ed216b13-546a-4d0c-82db-79c175912556
ms.date: 03/29/2018
ms.keywords: "(*TAPE_VERIFY_INQUIRY_ROUTINE), (*TAPE_VERIFY_INQUIRY_ROUTINE) routine [Storage Devices], TAPE_VERIFY_INQUIRY_ROUTINE, minitape/(*TAPE_VERIFY_INQUIRY_ROUTINE), storage.tapeminiverifyinquiry, tapemini_d8a92eee-8b82-4fac-b568-fbe40c906ec1.xml"
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
-	(*TAPE_VERIFY_INQUIRY_ROUTINE)
product:
- Windows
targetos: Windows
req.typenames: 
---

# TAPE_VERIFY_INQUIRY_ROUTINE callback function


## -description


<i>TAPE_VERIFY_INQUIRY_ROUTINE</i> determines whether the tape miniclass driver recognizes and supports a given device. This routine is required.


## -parameters




### -param InquiryData [in]

Pointer to SCSI inquiry data for the device.


### -param ModeCapabilitiesPage [in]

Pointer to a MODE_CAPABILITIES_PAGE structure that contains low-level information about the device. The format of this structure is defined by the QIC 157 standard and is subject to change. The pointer is <b>NULL</b> if the tape device does not support a mode capabilities page. 


## -returns



<i>TAPE_VERIFY_INQUIRY_ROUTINE</i> returns <b>TRUE</b> if the miniclass driver supports the device.




## -remarks



<i>TAPE_VERIFY_INQUIRY_ROUTINE</i> examines the <i>InquiryData</i>, particularly the <b>VendorId</b> and <b>ProductId</b> members, to determine whether the tape miniclass driver supports the tape device. <i>TAPE_VERIFY_INQUIRY_ROUTINE</i> uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff567617">TapeClassCompareMemory</a> to compare ID strings against values the tape miniclass driver supports.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567975">TAPE_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567617">TapeClassCompareMemory</a>
 

 

