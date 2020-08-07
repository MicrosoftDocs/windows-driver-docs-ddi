---
UID: NS:minitape._TAPE_WMI_OPERATIONS
title: _TAPE_WMI_OPERATIONS (minitape.h)
description: The tape miniclass driver passes this structure to its TapeMiniWMIControl routine to indicate which WMI operation must be performed by the device.
old-location: storage\tape_wmi_operations.htm
tech.root: storage
ms.assetid: 430d982e-4740-46ad-8391-aba5813a833a
ms.date: 03/29/2018
keywords: ["TAPE_WMI_OPERATIONS structure"]
ms.keywords: "*PTAPE_WMI_OPERATIONS, PTAPE_WMI_OPERATIONS, PTAPE_WMI_OPERATIONS structure pointer [Storage Devices], TAPE_WMI_OPERATIONS, TAPE_WMI_OPERATIONS structure [Storage Devices], _TAPE_WMI_OPERATIONS, ntddtape/PTAPE_WMI_OPERATIONS, ntddtape/TAPE_WMI_OPERATIONS, storage.tape_wmi_operations, structs-tape_93f1d9af-45b2-4121-9b4c-70ed7eaf1782.xml"
f1_keywords:
 - "minitape/TAPE_WMI_OPERATIONS"
 - "TAPE_WMI_OPERATIONS"
req.header: minitape.h
req.include-header: Ntddchgr.h, Minitape.h
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
- ntddtape.h
api_name:
- TAPE_WMI_OPERATIONS
targetos: Windows
req.typenames: TAPE_WMI_OPERATIONS, *PTAPE_WMI_OPERATIONS
---

# _TAPE_WMI_OPERATIONS structure


## -description


The tape miniclass driver passes this structure to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniWMIControl</a> routine to indicate which WMI operation must be performed by the device. 


## -struct-fields




### -field Method

Indicates the operation to be performed by the tape device. The operations allowed are as follows:





#### TAPE_CHECK_FOR_DRIVE_PROBLEM

If the tape drive supports commands to return specific device errors, such as tape alerts, the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniWMIControl</a> routine should execute the TAPE_QUERY_DEVICE_ERROR_DATA method Otherwise, it should execute the TAPE_QUERY_IO_ERROR_DATA method.





#### TAPE_QUERY_DEVICE_ERROR_DATA

Returns specific device errors, such as tape alerts. Not all tape drives support this method.





#### TAPE_QUERY_IO_ERROR_DATA

Returns general I/O error data, such as read/write errors, based on the I/O error count. All tape drives support this method.


### -field DataBufferSize

Indicates the size in bytes of the buffer in which the tape minidriver returns the results of the operation. 


### -field DataBuffer

Pointer to a buffer in which the tape minidriver returns the results of the operation. The first <b>sizeof</b>(ULONG) bytes of <b>DataBuffer</b> contain a value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ne-ntddtape-_tape_drive_problem_type">TAPE_DRIVE_PROBLEM_TYPE</a>, followed by <b>DataBufferSize</b> - <b>sizeof</b>(ULONG) bytes of tape data. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddtape/ne-ntddtape-_tape_drive_problem_type">TAPE_DRIVE_PROBLEM_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/nc-minitape-tape_process_command_routine">TapeMiniWMIControl</a>
 

 

