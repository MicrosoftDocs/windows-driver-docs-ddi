---
UID: NF:wdfdmaenabler.WdfDmaEnablerSetMaximumScatterGatherElements
title: WdfDmaEnablerSetMaximumScatterGatherElements function
author: windows-driver-content
description: The WdfDmaEnablerSetMaximumScatterGatherElements method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object.
old-location: wdf\wdfdmaenablersetmaximumscattergatherelements.htm
tech.root: wdf
ms.assetid: fdfcb8bc-bc42-4c34-ae19-b40401bea41e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_d9f2c46d-5981-4997-96b6-5a9db0dbfd8d.xml, WdfDmaEnablerSetMaximumScatterGatherElements, WdfDmaEnablerSetMaximumScatterGatherElements method, kmdf.wdfdmaenablersetmaximumscattergatherelements, wdf.wdfdmaenablersetmaximumscattergatherelements, wdfdmaenabler/WdfDmaEnablerSetMaximumScatterGatherElements
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaEnablerSetMaximumScatterGatherElements
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaEnablerSetMaximumScatterGatherElements function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerSetMaximumScatterGatherElements</b> method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object. 


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>. 


### -param MaximumFragments [in]

The maximum number of scatter/gather elements that the driver and device can support.   


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If your driver calls <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, it must do so within the <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> or <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function.

If your driver does not call <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, the framework uses a default value of WDF_DMA_ENABLER_UNLIMITED_FRAGMENTS, which means that there is no limit to the number of scatter/gather elements.

For more information about this method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a>.


#### Examples

The following code example sets the maximum number of scatter/gather elements for a specified DMA enabler object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDmaEnablerSetMaximumScatterGatherElements(
                                             DmaEnabler, 
                                             NIC_MAX_PHYS_BUF_COUNT
                                             );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547005">WdfDmaEnablerGetMaximumScatterGatherElements</a>
 

 

