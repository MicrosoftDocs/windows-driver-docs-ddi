---
UID: NF:wdfdmaenabler.WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
title: WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function
author: windows-driver-content
description: The WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function initializes a driver's WDF_DMA_SYSTEM_PROFILE_CONFIG structure.
old-location: wdf\wdf_dma_system_profile_config_init.htm
old-project: wdf
ms.assetid: C3E9B4D6-A1BB-425E-A131-D93C3219D28B
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_dma_system_profile_config_init, WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT, wdf.wdf_dma_system_profile_config_init, wdfdmaenabler/WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT, WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.lib: NtosKrnl.exe
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
-	WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: WDF_DMA_PROFILE
req.product: Windows 10 or later.
---

# WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_system_profile_config.md">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure.


## -syntax


````
__inline
void WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT(
  _Out_ PWDF_DMA_SYSTEM_PROFILE_CONFIG  Config,
  _In_  PHYSICAL_ADDRESS                Address,
  _In_  DMA_WIDTH                       DmaWidth,
  _In_  PCM_PARTIAL_RESOURCE_DESCRIPTOR DmaDescriptor
);
````


## -parameters




### -param DmaConfig

TBD


### -param Address [in]

The translated address of the register to target for DMA. For more information, see Remarks.


### -param DmaWidth [in]

The width of the register specified by <b>Address</b>.


### -param DmaDescriptor [in]

The translated resource descriptor for the DMA channel assigned 
      the device during <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>.


#### - Config [out]

A pointer to a driver-allocated <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_system_profile_config.md">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure.


## -returns


This function does not return a value.



## -remarks


Typically, a driver calls <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> from within its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. A driver must call the <b>WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</b> function before calling <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile.md">WdfDmaEnablerConfigureSystemProfile</a>.

Depending on the System on a Chip (SoC) design, the <i>Address</i> parameter might have a different meaning. For example if DMA uses dedicated transfer ports on the device, <i>Address</i> might indicate the port to which DMA writes occur.

 For more information about creating a system-mode DMA enabler, see <a href="https://msdn.microsoft.com/CCC77C15-69CA-44CB-8DEB-29F3EAEA44F6">Supporting System-Mode DMA</a>.



## -see-also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablerconfiguresystemprofile.md">WdfDmaEnablerConfigureSystemProfile</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_system_profile_config.md">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

