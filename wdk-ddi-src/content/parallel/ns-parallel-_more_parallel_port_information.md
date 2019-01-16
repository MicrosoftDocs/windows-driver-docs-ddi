---
UID: NS:parallel._MORE_PARALLEL_PORT_INFORMATION
title: "_MORE_PARALLEL_PORT_INFORMATION"
description: The MORE_PARALLEL_PORT_INFORMATION structure specifies information about the system interface that supports the operation of a parallel port.
old-location: parports\more_parallel_port_information.htm
tech.root: parports
ms.assetid: b21bfbce-5436-4865-b291-2e55abc4aad1
ms.date: 02/15/2018
ms.keywords: "*PMORE_PARALLEL_PORT_INFORMATION, MORE_PARALLEL_PORT_INFORMATION, MORE_PARALLEL_PORT_INFORMATION structure [Parallel Ports], PMORE_PARALLEL_PORT_INFORMATION, PMORE_PARALLEL_PORT_INFORMATION structure pointer [Parallel Ports], _MORE_PARALLEL_PORT_INFORMATION, cisspd_0a671b2f-443c-4373-aeb0-8bf59c1d836b.xml, parallel/MORE_PARALLEL_PORT_INFORMATION, parallel/PMORE_PARALLEL_PORT_INFORMATION, parports.more_parallel_port_information"
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
-	MORE_PARALLEL_PORT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: MORE_PARALLEL_PORT_INFORMATION, *PMORE_PARALLEL_PORT_INFORMATION
---

# _MORE_PARALLEL_PORT_INFORMATION structure


## -description


The MORE_PARALLEL_PORT_INFORMATION structure specifies information about the system interface that supports the operation of a parallel port.


## -syntax


```cpp
typedef struct _MORE_PARALLEL_PORT_INFORMATION {
  INTERFACE_TYPE  InterfaceType;
  ULONG           BusNumber;
  ULONG           InterruptLevel;
  ULONG           InterruptVector;
  KAFFINITY       InterruptAffinity;
  KINTERRUPT_MODE InterruptMode;
} MORE_PARALLEL_PORT_INFORMATION, *PMORE_PARALLEL_PORT_INFORMATION;
```


## -struct-fields




### -field InterfaceType

Specifies the I/O bus interface type that is associated with a parallel port. See <i>wdm.h </i>or <i>ntddk.h</i> for the definition of INTERFACE_TYPE.


### -field BusNumber

Specifies the bus number for the interface.


### -field InterruptLevel

Specifies the interrupt level for the parallel port.


### -field InterruptVector

Specifies the interrupt vector for the parallel port.


### -field InterruptAffinity

Specifies a [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) interrupt affinity value.


### -field InterruptMode

Specifies the interrupt mode. See <i>wdm.h </i>or <i>ntddk.h</i> for the declaration of KINTERRUPT_MODE.


## -remarks



An <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request from the Plug and Play manager passes a translated resource list that contains the information in a MORE_PARALLEL_PORT_INFORMATION structure. The system-supplied function driver for parallel ports saves the information in the device extension of the parallel port functional device object <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FDO</a>, and returns the information in response to an <a href="..\parallel\ni-parallel-ioctl_internal_get_more_parallel_port_info.md">IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</a> request.

For more information, see <a href="https://msdn.microsoft.com/d8ae2296-05b6-419a-93cc-00fcb12d41fe">Obtaining Information About a ParallelPort</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_more_parallel_port_info.md">IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a>



 

 


