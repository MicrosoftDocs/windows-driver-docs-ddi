---
UID: NS:ntddser._SERIAL_QUEUE_SIZE
title: "_SERIAL_QUEUE_SIZE"
author: windows-driver-content
description: The SERIAL_QUEUE_SIZE structure is used to resize the input buffer that the serial controller driver uses for serial receive operations.
old-location: serports\serial_queue_size.htm
old-project: serports
ms.assetid: 5EEE0B7D-2857-42D1-A387-9D38DAC2E368
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERIAL_QUEUE_SIZE, PSERIAL_QUEUE_SIZE, PSERIAL_QUEUE_SIZE structure pointer [Serial Ports], SERIAL_QUEUE_SIZE, SERIAL_QUEUE_SIZE structure [Serial Ports], _SERIAL_QUEUE_SIZE, ntddser/PSERIAL_QUEUE_SIZE, ntddser/SERIAL_QUEUE_SIZE, serports.serial_queue_size"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddser.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddser.h
api_name:
-	SERIAL_QUEUE_SIZE
product: Windows
targetos: Windows
req.typenames: SERIAL_QUEUE_SIZE, *PSERIAL_QUEUE_SIZE
---

# _SERIAL_QUEUE_SIZE structure


## -description


The <b>SERIAL_QUEUE_SIZE</b> structure is used to resize the input buffer that the serial controller driver uses for serial receive operations.


## -syntax


````
typedef struct _SERIAL_QUEUE_SIZE {
  ULONG InSize;
  ULONG OutSize;
} SERIAL_QUEUE_SIZE, *PSERIAL_QUEUE_SIZE;
````


## -struct-fields




### -field InSize

Number of bytes requested for the input buffer. For more information, see Remarks.


### -field OutSize

Not used. Set to zero.


## -remarks



This structure is used by <a href="..\ntddser\ni-ntddser-ioctl_serial_set_queue_size.md">IOCTL_SERIAL_SET_QUEUE_SIZE</a> requests to specify the size requested for the new input buffer. This buffer is used internally by the serial controller driver to hold data received from the serial controller until the data can be copied to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request packet. If the requested buffer size is greater than the current receive buffer size, a new receive buffer is created. Otherwise, the receive buffer is not changed.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_queue_size.md">IOCTL_SERIAL_SET_QUEUE_SIZE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIAL_QUEUE_SIZE structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

