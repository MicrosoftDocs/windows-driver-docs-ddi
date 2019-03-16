---
UID: NC:wdm.PCONFIGURE_ADAPTER_CHANNEL
title: PCONFIGURE_ADAPTER_CHANNEL (wdm.h)
description: The ConfigureAdapterChannel routine invokes a custom function that is implemented by the DMA controller represented by an adapter object.
old-location: kernel\configureadapterchannel.htm
tech.root: kernel
ms.assetid: 964B305F-5B9E-4705-89BA-DBAE43464FB1
ms.date: 04/30/2018
ms.keywords: ConfigureAdapterChannel, ConfigureAdapterChannel callback function [Kernel-Mode Driver Architecture], PCONFIGURE_ADAPTER_CHANNEL, PCONFIGURE_ADAPTER_CHANNEL callback, kernel.configureadapterchannel, wdm/ConfigureAdapterChannel
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- ConfigureAdapterChannel
product:
- Windows
targetos: Windows
req.typenames: 
---

# PCONFIGURE_ADAPTER_CHANNEL callback function


## -description


The <b>ConfigureAdapterChannel</b> routine invokes a custom function that is implemented by the DMA controller represented by an adapter object.


## -parameters




### -param DmaAdapter [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param FunctionNumber [in]

The number of the custom function to select. For more information, see the Remarks section.


### -param Context [in]

A pointer to the configuration parameters for the custom function that is specified by <i>FunctionNumber</i>. The function is implemented by the DMA controller and can be accessed by a device driver through the adapter object. The DMA controller and the device driver must agree on the meaning of these configuration parameters. The data that <i>Context</i> points to is opaque to the operating system.


## -returns



<b>ConfigureAdapterChannel</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_NOT_IMPLEMENTED</dt>
</dl>
</td>
<td width="60%">
The  DMA extension does not implement the function specified by <i>FunctionNumber</i>.

</td>
</tr>
</table>
 




## -remarks



<b>ConfigureAdapterChannel</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>ConfigureAdapterChannel</b> only for system DMA adapters. Do not use this routine for a bus-master adapter.

A particular system DMA controller might have special hardware features that device drivers can access through a set of one or more custom functions. A controller might implement more than one custom function, in which case each function is identified by a different function number. These functions abstract the DMA hardware features so that the same functions can be supported on different hardware platforms.

Typically, a custom function sets state information in the DMA controller to configure hardware features for use  in subsequent DMA transfers.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
 

 

