---
UID: NF:wdfdmaenabler.WdfDmaEnablerSetMaximumScatterGatherElements
title: WdfDmaEnablerSetMaximumScatterGatherElements function (wdfdmaenabler.h)
description: The WdfDmaEnablerSetMaximumScatterGatherElements method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object.
old-location: wdf\wdfdmaenablersetmaximumscattergatherelements.htm
tech.root: wdf
ms.assetid: fdfcb8bc-bc42-4c34-ae19-b40401bea41e
ms.date: 02/26/2018
keywords: ["WdfDmaEnablerSetMaximumScatterGatherElements function"]
ms.keywords: DFDmaObjectRef_d9f2c46d-5981-4997-96b6-5a9db0dbfd8d.xml, WdfDmaEnablerSetMaximumScatterGatherElements, WdfDmaEnablerSetMaximumScatterGatherElements method, kmdf.wdfdmaenablersetmaximumscattergatherelements, wdf.wdfdmaenablersetmaximumscattergatherelements, wdfdmaenabler/WdfDmaEnablerSetMaximumScatterGatherElements
f1_keywords:
 - "wdfdmaenabler/WdfDmaEnablerSetMaximumScatterGatherElements"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaEnablerSetMaximumScatterGatherElements
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaEnablerSetMaximumScatterGatherElements function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaEnablerSetMaximumScatterGatherElements</b> method sets the maximum number of scatter/gather elements that a device supports, for a specified DMA enabler object. 


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>. 


### -param MaximumFragments [in]

The maximum number of scatter/gather elements that the driver and device can support.   


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



If your driver calls <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, it must do so within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a> callback function.

If your driver does not call <b>WdfDmaEnablerSetMaximumScatterGatherElements</b>, the framework uses a default value of WDF_DMA_ENABLER_UNLIMITED_FRAGMENTS, which means that there is no limit to the number of scatter/gather elements.

For more information about this method, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enabling-dma-transactions">Enabling DMA Transactions</a>.


#### Examples

The following code example sets the maximum number of scatter/gather elements for a specified DMA enabler object.

```cpp
WdfDmaEnablerSetMaximumScatterGatherElements(
                                             DmaEnabler, 
                                             NIC_MAX_PHYS_BUF_COUNT
                                             );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablergetmaximumscattergatherelements">WdfDmaEnablerGetMaximumScatterGatherElements</a>
 

 

