---
UID: NS:ntddtape._TAPE_WMI_OPERATIONS
title: "_TAPE_WMI_OPERATIONS"
author: windows-driver-content
description: The tape miniclass driver passes this structure to its TapeMiniWMIControl routine to indicate which WMI operation must be performed by the device.
old-location: storage\tape_wmi_operations.htm
old-project: storage
ms.assetid: 430d982e-4740-46ad-8391-aba5813a833a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PTAPE_WMI_OPERATIONS, PTAPE_WMI_OPERATIONS, PTAPE_WMI_OPERATIONS structure pointer [Storage Devices], TAPE_WMI_OPERATIONS, TAPE_WMI_OPERATIONS structure [Storage Devices], _TAPE_WMI_OPERATIONS, ntddtape/PTAPE_WMI_OPERATIONS, ntddtape/TAPE_WMI_OPERATIONS, storage.tape_wmi_operations, structs-tape_93f1d9af-45b2-4121-9b4c-70ed7eaf1782.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddtape.h
apiname:
-	TAPE_WMI_OPERATIONS
product: Windows
targetos: Windows
req.typenames: TAPE_WMI_OPERATIONS, *PTAPE_WMI_OPERATIONS
---

# _TAPE_WMI_OPERATIONS structure


## -description


The tape miniclass driver passes this structure to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff567957">TapeMiniWMIControl</a> routine to indicate which WMI operation must be performed by the device. 


## -syntax


````
typedef struct _TAPE_WMI_OPERATIONS {
  ULONG Method;
  ULONG DataBufferSize;
  PVOID DataBuffer;
} TAPE_WMI_OPERATIONS, *PTAPE_WMI_OPERATIONS;
````


## -struct-fields




### -field Method

Indicates the operation to be performed by the tape device. The operations allowed are as follows:





#### TAPE_CHECK_FOR_DRIVE_PROBLEM

If the tape drive supports commands to return specific device errors, such as tape alerts, the minidriver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff567957">TapeMiniWMIControl</a> routine should execute the TAPE_QUERY_DEVICE_ERROR_DATA method Otherwise, it should execute the TAPE_QUERY_IO_ERROR_DATA method.





#### TAPE_QUERY_DEVICE_ERROR_DATA

Returns specific device errors, such as tape alerts. Not all tape drives support this method.





#### TAPE_QUERY_IO_ERROR_DATA

Returns general I/O error data, such as read/write errors, based on the I/O error count. All tape drives support this method.


### -field DataBufferSize

Indicates the size in bytes of the buffer in which the tape minidriver returns the results of the operation. 


### -field DataBuffer

Pointer to a buffer in which the tape minidriver returns the results of the operation. The first <b>sizeof</b>(ULONG) bytes of <b>DataBuffer</b> contain a value of type <a href="..\ntddtape\ne-ntddtape-_tape_drive_problem_type.md">TAPE_DRIVE_PROBLEM_TYPE</a>, followed by <b>DataBufferSize</b> - <b>sizeof</b>(ULONG) bytes of tape data. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567957">TapeMiniWMIControl</a>



<a href="..\ntddtape\ne-ntddtape-_tape_drive_problem_type.md">TAPE_DRIVE_PROBLEM_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_WMI_OPERATIONS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

