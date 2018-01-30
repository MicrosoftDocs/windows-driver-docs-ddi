---
UID: NS:wdfdmaenabler._WDF_DMA_SYSTEM_PROFILE_CONFIG
title: "_WDF_DMA_SYSTEM_PROFILE_CONFIG"
author: windows-driver-content
description: The WDF_DMA_SYSTEM_PROFILE_CONFIG structure describes the hardware-specific settings related to a system-mode DMA enabler.
old-location: wdf\wdf_dma_system_profile_config.htm
old-project: wdf
ms.assetid: 80131AB6-4A2B-4D99-9289-CE9FE26E0695
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_DMA_SYSTEM_PROFILE_CONFIG, PWDF_DMA_SYSTEM_PROFILE_CONFIG structure pointer, wdf.wdf_dma_system_profile_config, kmdf.wdf_dma_system_profile_config, _WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG, wdfdmaenabler/PWDF_DMA_SYSTEM_PROFILE_CONFIG, wdfdmaenabler/WDF_DMA_SYSTEM_PROFILE_CONFIG, PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG structure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
-	wdfdmaenabler.h
apiname:
-	WDF_DMA_SYSTEM_PROFILE_CONFIG
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# _WDF_DMA_SYSTEM_PROFILE_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_SYSTEM_PROFILE_CONFIG</b> structure describes the hardware-specific settings related to a system-mode DMA enabler.


## -syntax


````
typedef struct _WDF_DMA_SYSTEM_PROFILE_CONFIG {
  ULONG                           Size;
  BOOLEAN                         DemandMode;
  BOOLEAN                         LoopedTransfer;
  DMA_WIDTH                       DmaWidth;
  PHYSICAL_ADDRESS                DeviceAddress;
  PCM_PARTIAL_RESOURCE_DESCRIPTOR DmaDescriptor;
} WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG;
````


## -struct-fields




### -field Size

The size of this structure in bytes.


### -field DemandMode

Specifies that the transfer is controlled by the device's DMA  
      request line specified in the <b>DmaDescriptor</b> member of this structure. See more information in Remarks.


### -field LoopedTransfer

Specifies that the DMA adapter should loop around the specified transfer if the length is greater than the size of the buffer.


### -field DmaWidth

The width of the register specified by <b>DeviceAddress</b>. Possible values are Width8Bits, Width16Bits, Width32Bits, and Width64Bits.


### -field DeviceAddress

The translated address to or from which the DMA controller transfers. The driver can specify an offset from this base address on each transaction by calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionsetdeviceaddressoffset.md">WdfDmaTransactionSetDeviceAddressOffset</a>.


### -field DmaDescriptor

The translated resource descriptor for the DMA channel assigned 
      the device during <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>. This provides the DMA request line for the adapter.


## -remarks


The driver provides this structure to <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile.md">WdfDmaEnablerConfigureSystemProfile</a> after creating a system-profile DMA enabler.

Typically, drivers set <b>DemandMode</b> to TRUE.   The driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> callback function then programs the device to assert its DMA request line and initiate the transfer.  In this case, the transfer might begin while <i>EvtProgramDma</i> is still running.

The driver must ensure that the device's DMA request line is not asserted before the driver's <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> callback function begins execution. Otherwise, it is possible for the DMA transfer to begin before the framework calls <i>EvtProgramDma</i>.


If <b>DemandMode</b> is set to FALSE, the DMA transfer may begin before the framework calls the driver’s <a href="https://msdn.microsoft.com/c01b94b2-aabf-47dd-952a-06e481579614">EvtProgramDma</a> function. 



## -see-also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile.md">WdfDmaEnablerConfigureSystemProfile</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdf_dma_system_profile_config_init.md">WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DMA_SYSTEM_PROFILE_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

