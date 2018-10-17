---
UID: NS:parallel._PARALLEL_1284_COMMAND
title: "_PARALLEL_1284_COMMAND"
author: windows-driver-content
description: The PARALLEL_1284_COMMAND structure specifies information that a client uses to select and deselect an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device.
old-location: parports\parallel_1284_command.htm
tech.root: parports
ms.assetid: 5b46253c-c111-4675-898e-78b81ecbddb8
ms.date: 2/15/2018
ms.keywords: "*PPARALLEL_1284_COMMAND, PARALLEL_1284_COMMAND, PARALLEL_1284_COMMAND structure [Parallel Ports], PPARALLEL_1284_COMMAND, PPARALLEL_1284_COMMAND structure pointer [Parallel Ports], _PARALLEL_1284_COMMAND, cisspd_082268fb-79fd-46df-85a7-89dd56098ed0.xml, parallel/PARALLEL_1284_COMMAND, parallel/PPARALLEL_1284_COMMAND, parports.parallel_1284_command"
ms.topic: struct
req.header: parallel.h
req.include-header: Parallel.h
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
-	parallel.h
api_name:
-	PARALLEL_1284_COMMAND
product:
- Windows
targetos: Windows
req.typenames: PARALLEL_1284_COMMAND, *PPARALLEL_1284_COMMAND
---

# _PARALLEL_1284_COMMAND structure


## -description


The PARALLEL_1284_COMMAND structure specifies information that a client uses to select and deselect an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device.


## -syntax


```
typedef struct _PARALLEL_1284_COMMAND {
  UCHAR ID;
  UCHAR Port;
  ULONG CommandFlags;
} PARALLEL_1284_COMMAND, *PPARALLEL_1284_COMMAND;
```


## -struct-fields




### -field ID

Specifies the IEEE 1284.3 device ID.


### -field Port

Reserved (set to zero).


### -field CommandFlags

Specifies a bitwise OR of zero or more of the following flags:





#### PAR_END_OF_CHAIN_DEVICE

Specifies an end-of-chain device.



#### PAR_HAVE_PORT_KEEP_PORT

Specifies that the client has the parallel port allocated, and makes a request to keep the port allocated.


## -remarks



The system-supplied function driver for parallel ports supports the simultaneous connection of zero to two IEEE 1284.3 daisy-chain devices and an IEEE 1284 end-of-chain device. In Windows XP, the parallel port function driver supports the simultaneous connection of zero to four IEEE 1284.3 daisy-chain devices and an IEEE 1284 end-of-chain device. The end-of-chain device must be an IEEE 1284 device, but does not have to be an IEEE 1284.3 device.

For more information, see <a href="https://msdn.microsoft.com/1a3ac1b1-9180-4b71-8740-70c6fbe9a885">Selecting and Deselecting an IEEE 1284 Device Attached to a ParallelPort</a>.




## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a>



<a href="..\parallel\nc-parallel-pparallel_deselect_routine.md">PPARALLEL_DESELECT_ROUTINE</a>



<a href="..\parallel\nc-parallel-pparallel_try_select_routine.md">PPARALLEL_TRY_SELECT_ROUTINE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_deselect_device.md">IOCTL_INTERNAL_DESELECT_DEVICE</a>



 

 


